# Compatibility and migration to the new server architecture

`Pandora Server` gathers the specialised servers into a single multithreaded
application: each one walks its own task queue (modules to process, agents to
scan, alerts to evaluate) with its own number of threads. This annex describes
how remote monitoring is shared out today and what is left of the previous
generation of instances specialised by type of check. The number of processes
in the system is not deduced from that split.

## Why fewer servers

The previous generation had more specialised instances: ICMP, SNMP, WMI, remote
plugins and remote inventory, among others. The wiki describes a high memory
footprint even before processing modules; it does not state that each subtype
was an independent operating system process.

The change groups several types of check into the same server, with more threads
inside. The network consumer can handle WMI and ICMP when `networkhpserver` is
disabled, with no need for a specialised instance per type. Each check keeps its
own timeout: grouping servers does not mean levelling their timeouts.

## Historical inventory of servers

The wiki lists **21 names from the previous generation**. It is a historical
inventory, not the list of servers the current configuration starts, nor a
forecast of the ones that will exist in other versions:

Data Server · SNMP Console · Syslog Server · Export Server ·
Sync Server · Discovery Server · WEB Server · Network Server ·
WMI Server · Plugins Server · Inventory Server · ICMP Server · SNMP Server ·
Event Server · Log Server · SIEM Server · NetFlow Server (including sFlow) ·
NCM Server · Policy Manager Server · WUX Server · MADE Server.

In that list, **SNMP Server** meant SNMP module checks; **SNMP Console**
received traps. The old names do not by themselves amount to specialised
instances in the current start-up.

## What each server does today

Of the whole family of servers that existed, only three share out remote
monitoring today (agents with no EndPoint, or EndPoints also checked from
outside):

| Server | Token | What it runs |
|---|---|---|
| Network (`Network Server`) | `networkserver` | TCP, remote commands (SSH and Windows remote), WMI, prediction modules and web modules; also ordinary ICMP and SNMP if `networkhpserver` is explicitly disabled |
| High-performance network (`Network HP Server`) | `networkhpserver` | ICMP in bulk with `fping` and SNMP in bulk with `pandorafsnmp` (v1, v2c and v3) |
| Heavy (`Heavy Server`) | `heavyserver` | Remote server plugins, remote inventory, network device configuration management ([NCM](../parte-3/3.6-gestion-de-configuracion-de-equipos-de-red-ncm.md)) and export of data to another Pandora FMS |

The split of ICMP and SNMP between the first two is not a choice the
administrator makes module by module: with the Network High Performance Server
running (it comes that way from the factory), the Network Server gives up ICMP
and SNMP and keeps the rest; if `networkhpserver` is explicitly disabled, the
Network Server takes charge of both again, query by query, with the system tools
instead of the bulk processing. There is only one exception: an SNMP module that
builds up more errors than the retry allows (`braa_retries`) falls to the
Network Server, even if the high-performance one is still running. If the
high-performance server does not start for lack of `fping` or `braa`, its
constructor does not disable `networkhpserver`: an automatic switch of ICMP and
SNMP must not be taken for granted. The details of the split are in
[Network monitoring](../parte-2/2.6-monitorizacion-de-redes.md).

Two servers from the previous version's list disappeared without leaving a
replacement of their own: the prediction server and the web server. Their
functions were not taken over by a new server, but by the Network Server itself,
which identifies the module type before running it and calls the prediction
routine or the web check one as appropriate, without going through a different
specialised instance.

Besides these three, the wiki describes servers tied to the master: the policy
manager on a node, and migration and autoprovisioning on a Command Center. The
policy manager is not a server of its own: it runs from the console itself, not
as an independent server process. Migration and autoprovisioning in the Command
Center do rely on a server switch of their own (see the `provisioningserver`
token in the [full
reference](../parte-9/9.3-referencia-completa-de-configuracion-del-servidor.md#2-server-activation-and-number-of-threads)).
The synchronisation server is disabled from the factory; to start it requires
`syncserver` enabled and `sync_address` set. Its constructor does not require it
to be master.

## Servers enabled by default

The template enables five servers and leaves the eleven switches listed below
disabled. The actual start-up also depends on the requirements of each
component. These are **template** values, not the internal values the parser
uses when an option is missing, nor an exhaustive inventory of every function in
the product (see the [full
reference](../parte-9/9.3-referencia-completa-de-configuracion-del-servidor.md#2-server-activation-and-number-of-threads)
for each token):

| Enabled in the template | Disabled in the template |
|---|---|
| Data (`dataserver`) | SNMP console (`snmpconsole`) |
| Network (`networkserver`) | Events (`eventserver`) |
| High-performance network (`networkhpserver`) | Log (`logserver`) |
| Heavy (`heavyserver`) | WUX (`wuxserver`) |
| Discovery (`discoveryserver`) | Syslog (`syslogserver`) |
| — | RMM (`rmmserver`) |
| — | Alerts (`alertserver`) |
| — | NetFlow (`netflowserver`) |
| — | MADE (`madeserver`) |
| — | SIEM (`siemserver`) |
| — | SIEM events (`siemevents`) |

The wiki's disabled list includes **Mainframe Server**, but there is no
equivalent switch among the tokens of this template or among the options that
`Config.pm` parses in the checkout examined. No default value is attributed to
it for that reason, nor is it inferred that it does not exist in other
components. The wiki described **Export Server** as disabled by default in the
previous split; `heavyserver 1` does not allow deducing the current state of the
export.

## Retired tokens and their replacement

Installation from the server packages examined places the usual configuration
at `/etc/pandora/pandora_server.conf`. The executable accepts the path of the
file as an argument, so that location is not mandatory in every installation. To
change activation or threads, edit the file that **your** service uses.

The legacy switches are still read in `pandora_server.conf`, but they do not
instantiate the old servers in the current start-up path. The old thread tokens
are also parsed, but they **do not adjust the threads** of the servers that
perform those tasks today: the new thread token given in each row has to be
configured.

| Legacy token (activation / threads) | Current function | Replacement for activation / threads |
|---|---|---|
| `predictionserver` / `prediction_threads` | Prediction | `networkserver` / `network_threads` |
| `webserver` / `web_threads` | Web | `networkserver` / `network_threads` |
| `wmiserver` / `wmi_threads` | WMI | `networkserver` / `network_threads` |
| `icmpserver` / `icmp_threads` | ICMP | `networkhpserver` / `networkhpserver_threads`; with HP disabled, `networkserver` / `network_threads` |
| `snmpserver` / `snmp_threads` | SNMP | `networkhpserver` / `networkhpserver_threads`; with HP disabled or when `braa_retries` is exceeded, `networkserver` / `network_threads` |
| `pluginserver` / `plugin_threads` | Remote plugins | `heavyserver` / `heavyserver_threads` |
| `inventoryserver` / `inventory_threads` | Remote inventory | `heavyserver` / `heavyserver_threads` |
| `exportserver` / `export_threads` | Export | `heavyserver` / `heavyserver_threads` |
| `ncmserver` / `ncmserver_threads` | NCM | `heavyserver` / `heavyserver_threads` |

`snmpserver` also keeps a specific read to check the activity of `snmptrapd`; it
does not enable SNMP module processing.

`reconserver` and `recon_threads` are a different case, not a simple
equivalence: a network reconnaissance server separate from Discovery never
existed. `reconserver` is today a second power switch for the Discovery Server
itself, an alternative to `discoveryserver` (it is enough for one of the two to
be active), and `recon_threads` still has an effect: the number of threads
Discovery uses is the higher of `discovery_threads` and `recon_threads`, not one
of the two exclusively. It is better not to touch it blindly thinking that it is
a leftover with no effect.

## Checks with short intervals

The usual check interval is 300 seconds (5 minutes). The module editor of the
Web console allows intervals of 15 seconds for ICMP availability and latency and
for numeric and incremental numeric SNMP; the editor rejects values below 15
seconds and corrects them with a warning. The same validation sets 300 seconds
for asynchronous types 21, 22 and 23, and 60 seconds for the other checked
types. It exempts Data Server modules before applying those minimums: it is not
a universal prohibition for every module, nor does it prove an equivalent
validation in the server.

The 300-second threshold also affects two other behaviours:

- **No unknown status is generated.** The periodic check that marks a module as
  unknown when it has gone too long without data requires an interval of 300
  seconds or more; with a shorter interval, that module does not move to unknown
  through that inactivity check.
- **Data precision changes:** `process_data` formats numeric data with five
  decimals when `module_interval` is 300 seconds or less, and with one when it
  exceeds 300 seconds. The wiki describes the reverse order.

## Compaction and deletion of short-interval data

With an enabled and working connection to the [historical
database](../parte-6/6.5-base-de-datos-de-historico.md), maintenance calls
`pandora_historydb_smallint` with a window of **7 days** for modules with
`module_interval` greater than zero and less than 300 seconds. The hook selects
those modules and calls the transfer to the historical database per module. The
purge and the general transfer run before, so those seven days do not guarantee
a universal week of retention, nor the transfer when there is no connection to
the historical database. It is not a window that can be configured from
[Performance](../parte-9/9.2-referencia-completa-de-configuracion-de-la-consola.md#3-performance).

The transfer of numeric data to the historical database may apply a
[compaction](../parte-6/6.7-optimizacion-de-la-base-de-datos.md) by time
intervals; text data does not enter that branch. It is disabled from the factory
(`days_compact=0`); `step_compact` is `1` sample per hour from the factory, not
the five stated in the wiki. The Web console allows configuring it between 1 and
12; the routine also limits values outside that range. Compaction groups the
numeric samples by module and interval: it calculates the mean or, for `_proc`
types, keeps zero if any zero appears. It is not the same as promising an exact
number of samples retained per hour in every case. The option lives in
`Settings → System Settings → Performance`, next to the rest of the purges.
