# Configuring fprobe for Netflow

## When to use an fprobe probe

If the network equipment already exports NetFlow, configure the collector
destination on it. If it cannot export it, `fprobe` captures packets on a
Linux interface and sends flow records to the Pandora FMS collector. The probe
does not turn an interface with no traffic into a window onto the whole
network: to observe the traffic of a switch, it has to reach that interface,
for example through a mirror port. And the mirror must carry the traffic you
want to measure, not the traffic that happened to be free for the test.

This annex describes the NetFlow probe, not the Pandora FMS query service. To
enable and configure the collector, see [Traffic monitoring with
Netflow](../parte-2/2.8-monitorizacion-de-trafico-con-netflow.md), section
"Enabling and configuring Netflow and sFlow in the console".

## Requirements and prior data

Before installing, write down the real capture interface, the collector
address and **the UDP port configured on it**. Do not assume that the
interface name or the port in the example match those of your installation.

| Requirement | Detail |
|---|---|
| Probe machine | Linux with an interface that receives the desired traffic and permission to install the package and capture packets. The procedure corresponds to Ubuntu 22.04, where it has been tested. |
| `fprobe` package | Tool external to Pandora FMS, available in the Ubuntu 22.04 repositories (version 1.1-8 in the test). It is installed with `apt install fprobe`. |
| Capture interface | Identify its name with `ip -br link` on the probe machine and confirm that it receives the traffic you are after. The `eth0` suggestion in the installation described in the wiki does not necessarily identify your interface. |
| NetFlow collector | `nfcapd` installed and Netflow enabled on the Pandora FMS server. Check in the web console the listening port and the data path configured; the initial NetFlow port is `9995/udp`, but it can be changed. |
| Connectivity | The probe must be able to send UDP to the collector IP and port. Allow that traffic in the firewalls and verify that the collector is listening; the probe status alone does not prove that datagrams arrive. |

## Installing and configuring the probe

On the Ubuntu 22 machine chosen for the probe, first check which interface
receives the packets. Do not use the name that appears in someone else's
example:

```bash
ip -br link
sudo apt install fprobe
```

The installation described in the [Pandora FMS development
wiki](https://pandorafms.com/manual/!development/es/documentation/pandorafms/monitoring/18_netflow#ks2_4_2_1)
asks for the capture interface and the collector destination. Enter
`<CAPTURE_INTERFACE>` (the name you checked earlier) and
`<COLLECTOR_IP>:<NETFLOW_PORT>`; the latter must match the UDP port
configured for `nfcapd` in the web console. For example, if the collector
listens on the initial port, the format is `<COLLECTOR_IP>:9995`, not an
address to be copied literally. The answers are saved in `/etc/default/fprobe`, which you can edit if you
made a mistake:

```bash
INTERFACE="<CAPTURE_INTERFACE>"
FLOW_COLLECTOR="<COLLECTOR_IP>:<NETFLOW_PORT>"
OTHER_ARGS="-fip"
```

After changing the file, restart the service with
`sudo systemctl restart fprobe`. The `-d` (idle, 60 s by default) and `-e`
(active flow, 300 s) parameters can be added to `OTHER_ARGS` if you need
flows to be exported sooner.

## Starting and checking reception

On the probe, check separately that the service is running:

```bash
sudo systemctl status fprobe
```

If the unit is stopped, first review its configuration and the service
messages; after fixing them, start it with `sudo systemctl start fprobe` and
check its status again. Only if you want it to start with the system and it
is not yet enabled, run `sudo systemctl enable fprobe`. The Ubuntu 22.04
package ships a classic init script (`/etc/init.d/fprobe`), which `systemd`
manages through `systemctl`; that script does not support `service fprobe
status`, so use `systemctl` or check the process with `pgrep -a fprobe`.

Generate traffic that **goes through the capture interface**. On the
collector server, check that `nfcapd` is listening on the configured port and
that recent `nfcapd.*` files appear in the Netflow data path configured in
Pandora FMS. Once there are capture files, view their contents on that same
server:

```bash
nfdump -R <NETFLOW_DATA_PATH>
```

Replace the placeholder with the real path on the collector, not the probe.
If the general network path is `/var/spool/pandora/data_in/` and the
subdirectory is `netflow`, the resulting path is
`/var/spool/pandora/data_in/netflow`. An active service on the probe is not
the same as new files; new files without records of the expected traffic do
not prove either that the mirror port observes what you intended. `nfdump`
must show records from a period with known traffic before you consider the
check finished. With the default values, a flow is exported once it has been
idle for 60 seconds: wait a minute or two after generating traffic before
concluding that nothing arrives.

## If no flows arrive

Review the point where the chain breaks, in this order:

1. Does the chosen interface receive the traffic you want to measure? Compare
   the selected name with `ip -br link` and check the mirror port or the real
   path of the packets. An active service cannot capture traffic that does
   not go through that interface.
2. Does the probe point to the IP and UDP port of `nfcapd` configured in the
   web console? If the port was changed from `9995`, also change the probe
   destination and review the firewall between both machines.
3. Is Netflow enabled and is `nfcapd` listening? The Pandora FMS server
   starts the collector when it starts; after enabling Netflow or changing
   its port, restart the Pandora FMS server to apply the change to the
   collector. Then check the listening port and the server records.
4. Do recent files appear in the configured data path? If they exist but
   `nfdump -R <NETFLOW_DATA_PATH>` does not show the expected traffic, check
   the interface and the queried period again. Use the collector path; the
   probe sends flows, it does not store the Pandora FMS files there.

The check ends in the records received, not in an "active" from `systemctl`.
It is a small difference until you have to explain why the graph is still
empty.
