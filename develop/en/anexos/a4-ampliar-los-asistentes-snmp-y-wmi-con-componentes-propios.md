# Extending the SNMP and WMI wizards with custom components

The SNMP and WMI wizards of the agent view (see [SNMP
wizard](../parte-2/2.6-monitorizacion-de-redes.md#snmp-wizard) and [Windows
without an agent:
WMI](../parte-2/2.6-monitorizacion-de-redes.md#windows-without-an-agent-wmi))
do not bring a fixed list of modules: they propose what they find in a
catalogue of **wizard components**. This annex explains how to extend that
catalogue with manufacturers and custom components, for both wizards.

## What wizard components are and when to create them

A wizard component is a template that describes what to query on the device
and how to turn it into a module. When the wizard explores a device, it does
not improvise: it walks this catalogue and offers the components that match
what it has found (the manufacturer, in SNMP), grouped in blocks according to
what they measure.

Creating a custom one is worth it in three cases: a manufacturer the wizard
does not recognise yet (the "PEN is not registered" error of [SNMP
wizard](../parte-2/2.6-monitorizacion-de-redes.md#snmp-wizard)), a proprietary
OID that should always be at hand without looking it up every time, or a piece
of data that does not come out of a single OID but of combining several. The
difference from an [ordinary network
component](../parte-2/2.6-monitorizacion-de-redes.md#network-components-do-not-start-from-scratch)
is the origin: that one is applied by hand, choosing it in the module editor;
a wizard component is proposed by the wizard after exploring the device, and a
single one can end up generating many modules at once, one per row it finds.

!!! example "When to create one and when not to"
    A switch the SNMP wizard already recognises, but which lacks a
    manufacturer's proprietary temperature sensor: no new component is
    needed, with [SNMP
    modules](../parte-2/2.6-monitorizacion-de-redes.md#snmp-modules) and the
    OID at hand it is enough for that one-off case. If, on the other hand, the
    same temperature probe is going to be repeated across dozens of devices
    from the same manufacturer, a wizard component saves creating it by hand
    on each one.

## Registering a manufacturer (PEN)

The SNMP wizard identifies the manufacturer of the device by its **PEN**
(*Private Enterprise Number*): a number that every manufacturer registers
with IANA and that occupies a fixed position inside the `sysObjectID` the
device declares. If Pandora FMS does not have that PEN registered, the wizard
stops with the "PEN is not registered" warning and proposes no component, even
if the device answers perfectly over SNMP.

Registering the PEN is the first step, in **Management → Configuration →
Templates → Private Enterprise Numbers**, with three fields: **PEN** (the
number the device declares), **Manufacturer** (the short name that later
identifies its components) and **Description**. Registering the PEN only gives
the manufacturer a name; it does not create a single module on its own, that
is done by the components of the next section. It requires console management
permission.

The installation brings 27 manufacturers already registered, but only some of
them bring wizard components as well: Cisco, HP, Juniper, F5, Fortinet and two
generic numbers for the devices that expose their information with
Net-SNMP/UCD, to which the generic components (**All**) that are offered to
any device are added. The rest of the manufacturers registered from the
factory (D-Link, MikroTik, Alcatel-Lucent, Ubiquiti, Allied Telesis, IBM,
Dell, Apple, Oracle, Hitachi, Synology, Fujitsu, among others) no longer make
the wizard stop, but they only receive those generic components until custom
components are created for them. A manufacturer that is not in the list has to
be registered by hand, as in the following example.

!!! example "Registering a UPS the wizard does not recognise"
    A UPS declares a PEN that is not in the factory catalogue. It is
    registered with its IANA number in **PEN**, `my-ups` in **Manufacturer**
    and a brief description. From then on the wizard no longer stops because
    of an unregistered PEN, although for the moment it proposes no module:
    that comes with the first component of the next section.

## Creating a wizard component

Wizard components are created in **Management → Configuration → Templates →
Remote components**, choosing the wizard component type. They share with an
ordinary network component the usual fields —enabled, **Add by default**
(whether it appears already checked when the wizard opens), name, data type,
component group (the block in which it appears grouped), unit and thresholds,
description— plus the **Module protocol** (SNMP or WMI) and the **Manufacturer
ID**: a specific manufacturer already registered, or **All**, which offers the
component for any device regardless of its PEN.

Two fields decide the rest of the form and what kind of module the component
is going to propose:

- **Scan Type**: **Fixed** creates a single module; **Dynamic** walks a table
  of the device and creates one module per row it finds, without knowing in
  advance how many there are going to be.
- **Execution type**: **Network** makes the server itself read the value
  directly, like a normal SNMP or WMI module; **Plugin** delegates the
  calculation to a server plugin or, if the wizard is launched from a
  satellite server, to a `module_exec` command.

| Scan | Execution | What it creates |
|---|---|---|
| Fixed | Network | A single module that reads an OID (or a WMI query) directly |
| Fixed | Plugin | A single module whose value is calculated by a plugin, from one or several OIDs or fields |
| Dynamic | Network | One module per row of a table, read directly |
| Dynamic | Plugin | One module per row of a table, calculated by a plugin |

Duplicating an existing component with the **Duplicate** action of its listing
is the quickest starting point for a similar new one; there is no import or
export of components between installations.

## SNMP components with a static OID

Fixed scan + network execution, the simplest combination: **Value OID** is the
final OID that is going to be read, just as in an SNMP module created by hand.
**Name OID** is optional and, if filled in, its value replaces the `_nameOID_`
macro in the module name.

!!! example "Battery charge of a UPS"
    With the `my-ups` manufacturer already registered, a fixed component
    called "Battery charge" with the proprietary charge OID in **Value OID**,
    warning and critical thresholds already filled in and the "Power"
    component group. As soon as the SNMP wizard is launched on an agent of
    that manufacturer, the component appears in its corresponding block, ready
    to be checked.

## SNMP components with a dynamic OID

Dynamic scan + network execution: **Value OID** and **Name OID** stop being
final OIDs and become two branches (*subtrees*) of the device. The wizard
walks both of them completely, crosses the results by index —the same index in
both branches corresponds to the same row— and proposes one module per index
found, with the name of that row replacing `_nameOID_` and the index itself
appended to the end of **Value OID**.

!!! example "One module per temperature sensor"
    A proprietary table exposes, for each temperature sensor of the device,
    its name in one branch and its value in another. A dynamic component with
    **Name OID** pointing to the branch of names and **Value OID** to the
    branch of values creates, after the exploration, one module per sensor
    found, each one with the real name of its sensor.

## SNMP components calculated by a plugin

For a piece of data that does not come out of reading a single OID, execution
switches to **Plugin**. The form then adds four things:

- **Macros OID**: one entry for each OID that takes part in the calculation,
  which is referenced in the rest of the form as `_oid_1_`, `_oid_2_`…
- **Value operation**: the formula that combines those values, written with
  the same `_oid_N_` macros. It only serves to show the value in the wizard
  preview; the module that is created does not use it.
- **Server plugin**: the plugin that does the calculation for real every time
  the module runs. The two factory ones share the same connection fields
  (`_address_`, `_port_`, `_version_`, `_community_` and the SNMPv3
  credentials), but they differ in what they ask next:
    - **Wizard SNMP module**, for numeric values: besides the connection, it
      asks for the **OID list** (`_oid_1_,_oid_2_`…) and the **Operation**: the
      formula that combines those values written as `_o1_`, `_o2_`… according
      to the position of each OID in the list.
    - **Wizard SNMP process**, to know whether a process is running: instead
      of a list of OIDs, it asks for a single **Process** field with the name
      of the process (case sensitive); the plugin checks by itself, against
      the SNMP process tree of the system, whether it appears as running.
- **Satellite execution**: the equivalent command for when the wizard is
  launched from a [satellite
  server](../parte-6/6.2-servidores-satelite.md), which uses the
  `wizard_snmp_module` and `wizard_snmp_process` plugins installed on the
  satellite.

Since the preview and the real execution use different fields, the formula in
**Value operation** and the one in **Operation** must say the same thing; if
not, the wizard proposes one value and the module ends up measuring another.

In dynamic scan, each `_oid_N_` stops being a final OID and becomes a branch
that is also walked by index, just as in the previous section; the wizard
calculates one value —and therefore one module— per row found.

!!! example "Usage percentage of a partition"
    Two OIDs of a storage table, used space and total space, are registered in
    **Macros OID** as `_oid_1_` and `_oid_2_`. **Value operation** is filled
    in with `(_oid_1_ * 100) / _oid_2_`, so that the preview already shows the
    percentage. In **Server plugin**, "Wizard SNMP module" is chosen, with
    `_oid_1_,_oid_2_` in the OID list and `(_o1_ * 100) / _o2_` in
    **Operation**; the connection fields are left with their macros. Each
    module created calculates the usage percentage on every run, with no post
    processing.

## WMI components

The WMI wizard uses the same component mechanism, with its own set of fields:
**WMI class** (the class that is going to be queried), **Query key field**
(which column of the response identifies each row) and **Query extra fields**
(the rest of the columns that are needed). Each column is available as a
`_FIELDNAME_` macro with the value of that row. As in SNMP, dynamic means one
module per row that the scan query returns.

The **Query filters** limit, on one hand, which rows the exploration returns
and, on the other, how the value of the module is calculated in network
execution:

- **Field value**: the number of the column of the response whose value
  becomes the value of the module (`0` is the key field itself; `1` onwards,
  each extra query field in its order).
- **Key string**: optional. If filled in, the value of the module stops being
  the raw data and becomes `1` or `0` depending on whether it matches this
  string. This filter is not applied when the wizard is launched from a
  [satellite server](../parte-6/6.2-servidores-satelite.md): the module
  generated on the satellite always returns the raw data of **Field value**,
  even if **Key string** has been filled in.

In plugin execution, instead of these two filters the following appear:

- **Value operation**: the formula that combines the fields of the row with
  the `_f1_`, `_f2_`… macros (one for each extra query field, in order).
- **Server plugin**: the plugin that does the calculation; the factory one is
  "Wizard WMI module", with the `_class_wmi_` macro for the queried class and
  the same `_f1_`, `_f2_`… family in its **Operation** field.
- **Satellite execution**: the equivalent command for when the wizard is
  launched from a satellite server, with the `wizard_wmi_module` plugin
  installed there.

!!! example "Free space of each local disk"
    A dynamic WMI component on the `Win32_LogicalDisk` class, with the query
    filter `DriveType = 3` (local disks only) and `_DeviceID_` in the module
    name: the wizard creates, on each Windows device, one free space module
    for each local disk it finds, with the drive letter in the name itself.

## Field reference

| Field | Protocol | What it is for |
|---|---|---|
| Add by default | Common | The component appears already checked when the wizard opens |
| Component group | Common | Block in which the component is grouped inside the wizard |
| Module protocol | Common | SNMP or WMI |
| Manufacturer ID | SNMP | Manufacturer (registered PEN) the component is offered to, or `All` for any |
| Scan Type | Common | `Fixed` (one module) or `Dynamic` (one module per row) |
| Execution type | Common | `Network` (direct read) or `Plugin` (delegated calculation) |
| Name OID | SNMP | OID (or branch, in dynamic) whose value replaces `_nameOID_` in the name |
| Value OID | SNMP, network | Final OID (or branch, in dynamic) that is read |
| Macros OID | SNMP, plugin | List of OIDs (or branches) that take part in the operation, as `_oid_N_` |
| Value operation | SNMP, plugin | Formula with `_oid_N_` that calculates the value shown in the preview; it is not used in the module created |
| Server plugin | SNMP, plugin | Plugin that calculates the value on each run of the module; its fields accept the macros of the following table |
| Satellite execution | SNMP, plugin | Equivalent command for when the wizard is launched from a satellite server |
| WMI class | WMI | Class that is queried |
| Query key field | WMI | Column of the response that identifies each row |
| Query extra fields | WMI | Rest of the columns of the response that are needed |
| Query filters (Scan / Execution) | WMI | Condition that limits the exploration and, separately, the execution of the module |
| Field value | WMI, network | Column number whose value becomes the value of the module (`0` = key field) |
| Key string | WMI, network | Optional string that turns the value into `1`/`0` depending on a match; it is ignored when running from a satellite server |
| Value operation | WMI, plugin | Formula with `_f1_`, `_f2_`… that calculates the value shown in the preview |
| Satellite execution | WMI, plugin | Equivalent command for when the wizard is launched from a satellite server, with the `wizard_wmi_module` plugin |

## Macro reference

| Macro | Replaced by | Where it applies |
|---|---|---|
| `_nameOID_` | Name obtained from `Name OID` | Module name, SNMP components |
| `_oid_N_` | In the preview, the value read; in the plugin fields and in the satellite execution, the OID at position N of `Macros OID` (with its index, in dynamic) | `Value operation`, `Server plugin` fields, `Satellite execution` |
| `_o1_`, `_o2_`… | Value of the OID at that position of the plugin's OID list | **Operation** field of the "Wizard SNMP module" plugin |
| `_FIELDNAME_` | Value of the `FIELDNAME` column of the current WMI row | WMI components |
| `_class_wmi_` | WMI class of the component | `Server plugin` fields and `Satellite execution`, plugin WMI components |
| `_field_wmi_N_` | Value of the query extra field number N | Plugin WMI components |
| `_f1_`, `_f2_`… | Value of the query extra field at that position | `Value operation` and **Operation** field of the "Wizard WMI module" plugin |
| `_address_`, `_port_` | Address and port the wizard was launched with | `Server plugin` fields and `Satellite execution` (SNMP and WMI) |
| `_version_`, `_community_` | SNMP version and community (v1/v2c) | `Server plugin` fields and `Satellite execution` (SNMP) |
| `_sec_level_`, `_auth_user_`, `_auth_method_`, `_auth_pass_`, `_priv_method_`, `_priv_pass_` | SNMPv3 credentials the wizard was launched with | `Server plugin` fields and `Satellite execution` (SNMP) |
| `_namespace_wmi_`, `_user_wmi_`, `_pass_wmi_` | WMI namespace and credentials the wizard was launched with | `Server plugin` fields and `Satellite execution` (WMI) |

Both wizards can also be launched on a [monitoring
policy](../parte-2/2.10-politicas-de-monitorizacion.md) instead of on a
specific agent, with an important difference in how these macros are filled
in: `_address_` is left as it is, as a literal macro, so that each agent that
receives the policy replaces it with its own address, just as in any other
[network
module](../parte-2/2.6-monitorizacion-de-redes.md#macros-in-the-module-fields);
the rest of the connection macros —version, community, SNMPv3 credentials,
namespace and WMI credentials— are equally replaced by what was written when
the wizard was launched, and stay fixed in the resulting policy module. With a
policy that is applied to agents with different communities or credentials, it
is advisable to review those values in each module after creating it.

Creating the plugin that runs a calculation of your own, instead of reusing
the factory ones, is explained in [9.9 · Creating remote
plugins](../parte-9/9.9-creacion-de-plugins-remotos.md).
