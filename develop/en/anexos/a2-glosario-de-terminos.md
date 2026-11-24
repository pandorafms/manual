# Glossary of terms

This glossary gathers the vocabulary used throughout the Pandora FMS
documentation: the concepts of the platform, the pieces of its architecture and
the versioning and licensing terms that appear in the rest of the site. It is not
meant to be read from cover to cover, but consulted. Each entry defines the term
in two or three sentences and, when the topic has a chapter of its own, points to
it.

## A

### Basic and advanced access

Two permission levels that can be granted to a user, to a module component and to
an alert. With **basic access** only the components and alerts of that level can
be used. With **advanced access**, those of any level. Advanced components are
more configurable: their name can be changed, they define the actions of their
alerts and they show fields the basic ones do not have, such as units or the
macros of a plugin.

### Action

Task carried out when an **alert** is triggered. Each action has its own settings
fields and the same alert can trigger several at once. Do not confuse it with the
**alert command**, which is the execution run by the server.

### ACL

From *Access Control List*. They determine user permissions. In Pandora FMS they
are defined by assigning a **profile** to a user over a **group**: the profile
says which operations are allowed and the group says on which agents.

### Manual update

The second way to bring an installation up to date, without going through **Warp
Update**: the same packages, applied by hand in the terminal as `root` and in an
order that is not negotiable (**console, database schema and server**). It gives
full control over the process and is the only way when the console cannot
download the packages. See [Updates](../parte-1/1.4-actualizaciones.md).

### Service level agreement (SLA)

An agreement negotiated between a customer and a service provider. In Pandora FMS
an SLA breach is reported when a module leaves the values considered normal. The
calculation looks at the data stored in the database, not at module status
changes. **Unknown** periods and **scheduled downtimes** are considered valid, as
are periods in warning status.

### Agent

Organisational entity in Pandora FMS. It usually represents a machine, a system
or a host, it holds the **modules** that monitor it and it belongs to a single
primary group. It has a unique name and, optionally, an alias, which can be
repeated. It can be related to other agents (parent-child). It is not the same as
an **EndPoint**: the agent is the logical container in the console, the EndPoint
is the program that collects data on the machine.

### Alert

Automatic notice about the status or the value of a module. It has two possible
states, triggered or not triggered, and it runs **actions**, such as sending an
email or launching an **alert command**. Its triggering conditions are defined by
the **alert template**.

### Module creation wizard

Wizard that creates modules of different types across several instances at once.
It uses module components and alert templates, and it does not tell instances
apart: it mixes agents and modules as if they came from the same source. It
belongs to the **Command Center**.

### AuthKey

Licence activation key. It is sent by Pandora FMS, or by its distributor, by
email or in a PDF. It is a number between 12 and 15 digits long that **can only
be used once**, and it generates the licence of the installation. See
[Licensing](../parte-1/1.5-licenciamiento.md).

## B

### Database

A set of data from the same context, stored systematically for later use. Pandora
FMS works with MySQL, MariaDB or Percona and accesses them through SQL. In
practice two are used: the real-time database and the historical one, to which
data is moved once it no longer needs to be queried by the second.

## C

### WMI check

Remote check against an MS Windows machine through WMI and with credentials. It
is the way to pull data from a Windows machine without installing an
**EndPoint** on it.

### SNMP checks

Checks that use the SNMP protocol. They query the OIDs exposed by the vendor
(*polling*) and listen to the *traps* the device sends on its own.

### TCP checks

Remote checks that query devices and computers through their open ports, with
challenge and response to verify that the port is answering.

### Command

Instruction executed on an operating system, requested by a user or by an
application. On the system console it is the usual way to administer the server.

### Alert command

System-level execution launched by the server when an **alert** is triggered. It
accepts external commands and custom scripts.

### Comment out or uncomment a parameter

Turning a parameter into a comment, with the special character at the start of
its line, so that the program ignores it. It is **uncommented** when that
character is removed and the parameter is read again.

### Command Center

Management layer on top of several Pandora FMS installations, which it calls
**nodes**. From a single interface they are seen together, their configuration is
synchronised and they are all operated at once. Each node keeps its own server
and its own database: the Command Center does not replace them, it coordinates them.
It is the current name of the former **metaconsole**. See
[Introduction and architecture](../parte-1/1.2-introduccion-y-arquitectura.md).

### Component

Template used to create a **module**. It can be local (run by the EndPoint on the
machine) or network-based, and among the network ones there are plugin, WMI, TCP,
SNMP and ICMP.

### Web console

Pandora FMS interface in the browser. It is the one used to configure, operate
and query the platform. In menus, the first mention in each section is written
"Web console" to avoid confusing it with the system console.

## D

### DAEMON

From *Disk And Execution Monitor*. A program with no graphical interface that
runs at operating system level with little or no user interaction.

### Dependency

A set of files, usually compiled to machine language, with common functions that
can be used by one or several applications on an operating system.

### Downgrade

Going back to the previous version of a server. It is used when an update
(*upgrade*) brings a problem that cannot wait to be fixed.

## E

### EndPoint

Program installed on a machine to collect local information. It keeps running,
takes data every **interval** and sends it to the server as XML files, through
Tentacle or through API 2.0. It is the piece that provides the data only visible
from inside the machine. It is not the same as an **agent**: the agent is the
console container.

### *nix environments

Short for Unix and Linux environments.

### Module status

The four statuses a module can be in. **NORMAL** is the value within its
thresholds. **WARNING** and **CRITICAL** indicate error conditions of different
severity and have independent thresholds. **UNKNOWN** is the status of a module
that has not received data for more than twice its interval.

### Event

Any incident that occurs on the monitored systems. An event shows anything from a
module status change to an alert triggered or recovered, or a system reboot.

## F

### False positive and false negative

A **false positive** is a check that returns an error that has not happened. A
**false negative** is a check that returns no error when one has happened. **Flip
Flop protection** exists to cushion both.

### Feature Release (FR)

Feature version, the one that brings the new features of the product. An FR
receives patches **only in specific situations**, the ones recognised by the
official support policy. It is the counterpart of the **LTS version**. See
[Version and support policy](../parte-1/1.3-versiones-y-estabilidad.md).

### Data file (data XML)

XML file generated by **EndPoints**. It contains the information of their modules
and, in addition, the data of the EndPoint itself: version, operating system and
so on.

## H

### Hibernate or hibernation

Saving to a fixed storage device everything held in RAM, data and running
programs, by an operating system.

## I

### Instance

Pandora FMS installation set up so that the **Command Center** can access it and,
optionally, so that it replicates its events to the Command Center. In the Command
Center world it is called a **node**.

### Inverse interval

Option that defines non-contiguous ranges in **thresholds**. In text string
modules, the threshold is defined as a substring.

## K

### Kernel

Software that communicates the hardware with the rest of the software on a
computer and is the essence of an operating system.

## L

### Perpetual licence

Licence model of the on-premise version. It is acquired once and the support and
maintenance are renewed every year, in order to keep receiving patches and new
versions. The other on-premise model is the **subscription**. See
[Licensing](../parte-1/1.5-licenciamiento.md).

## M

### Merging (code)

Merging of source code, for example to incorporate a new feature. It also applies
to other similar processes, such as merging two databases from different servers
into a third one.

### Debug mode

Detailed information about the processes and parameters of an application, step
by step, to make it easier to fix code exceptions (errors).

### Module

Atomic unit of information in Pandora FMS. It stores numeric or alphanumeric
values and **a single metric** each (CPU, RAM, traffic...). It lives inside an
**agent** and always attached to one only; an agent can hold many modules. Its
reading is interpreted through **thresholds**, which give the **module status**.

### Asynchronous monitoring

The monitoring of a module that returns data based on changes or events, which
may or may not happen.

### Synchronous monitoring

The monitoring of a module that returns data at regular intervals, for example a
temperature reading every five minutes.

### Mosaic

Simultaneous appearance of different documents or parts of them, usually
minimised and on the same plane. It is used in the GIS console.

## N

### Node

Each of the Pandora FMS installations managed by a **Command Center**. It keeps
its own server and its own database. The Command Center licence is counted by
active nodes, and redundancy replicas do not add up.

## O

### OpenSSH

A set of applications that allow encrypted communications over a network using
the SSH protocol.

## P

### Pandora Web Robot Daemon

**PWRD**. It provides the tools to automate web browsing sessions and monitor
them later with WUX.

### Package

A program or a set of programs packaged in a format ready to be installed on a
given operating system and version.

### Patch

A fix on an already published version. A patch brings security and critical
fixes, and does not back-port to the version it fixes improvements that only
exist in newer versions. On the LTS version they are numbered on top of the base
one: 800 receives 800.1, 800.2 and so on. See
[Version and support policy](../parte-1/1.3-versiones-y-estabilidad.md).

### Profile

A set of permissions over the possible operations in Pandora FMS: viewing an
agent, modifying it, assigning alerts to it and the rest. It is assigned to a
user and always over a given group.

### Ping

Network diagnostic utility that checks latency and connectivity between the local
computer and a remote one, at IP protocol level. It uses ICMP request (*Echo
Request*) and reply (*Echo Reply*) packets.

### Alert template

Defines the triggering conditions of an **alert**: the module value or status
that triggers it, how many times it can be triggered within an interval and in
which time range.

### SNMP polling

Regular SNMP query from Pandora FMS to the monitored devices.

### Flip Flop protection

Mechanism that prevents a module from changing status on the first swing of its
value. The *flip flop* phenomenon is a value that frequently alternates between
bad and good. The protection is set with the **FF threshold**, the number of
consecutive times the condition must occur for the change to happen, plus the FF
interval. It cushions false positives and negatives.

## R

### Log rotation

Automated system administration process in which log files are compressed,
archived, renamed or deleted. New log data is sent to a new file, usually in the
same location.

## S

### Server

The `Pandora Server`. It processes the information collected by the other pieces,
runs the alerts, applies the policies and stores the data in the database. Since
version 784 it groups several services that used to be separate instances into
fewer processes, and each of them can be enabled or disabled as needed.

### Remote server

A server reached over the network, as opposed to the local server.

### Satellite server

Pandora FMS installation that monitors a remote network without depending on the
connection to the main server. It asks the server every few seconds (30 by
default) whether there are changes, it starts the connection itself (no port has
to be exposed) and it supports a reverse SSH tunnel since version 785. See
[Introduction and architecture](../parte-1/1.2-introduccion-y-arquitectura.md).

### Shell or command line

Interface that allows commands to be entered on a machine through the keyboard.

### SIEM

From *Security Information and Event Management*. System that collects, filters,
normalises, correlates and presents security events. What Pandora SIEM adds is
that collection is already done. The logs that feed it are the same ones the
platform already collects. The security event engine builds on that previous
work instead of setting up a second system apart.

### Native software

Software, or data formats, designed to run or be processed on a specific
operating system.

### Superadmin

Pandora FMS superuser, just as `root` is in Linux. When a full server is
installed, an `admin` user is created, which is the first superadmin, and it is
not the only one: there are users with the **PM access bit**, practically the
same except that they cannot create alert commands or appoint other superadmins.
Some functions can only be reached by a superadmin.

### Subscription

Licence model of the on-premise version in which payment is made every year, with
support and maintenance included as long as the contract lasts. The software and
the features are the same as with the **perpetual licence**, so the choice is
about cash flow, not about the product. See
[Licensing](../parte-1/1.5-licenciamiento.md).

### SVN / Subversion / Code repository

Version control system that keeps a repository with the different versions of the
files that make up a project throughout its life.

### Sync Server

Piece that turns the problem around when the remote network cannot start
communication towards the server. The main server takes the initiative and goes
to fetch the data from a Tentacle server deployed in the isolated network, which
acts as a temporary store: information accumulates there until the main server
downloads it, and whatever is downloaded disappears from the store. See
[Introduction and architecture](../parte-1/1.2-introduccion-y-arquitectura.md).

## T

### Tarball

Archive with one or several programs packaged in TAR format. Unlike a **package**,
it carries no information about how to install it and it is not specific to any
operating system.

### Tentacle

Data transfer protocol used by **EndPoints** and the **satellite server** to send
data to the Pandora FMS server. It is cross-platform and uses port 41121 by
default, assigned by IANA.

## U

### Threshold

Minimum or maximum value of a module from which a **status** change occurs.

### Alert threshold

Time interval during which the restrictions defined in the **alert template**
apply.

### root user

In *nix environments, the user dedicated to administering the operating system,
with special privileges to install, configure and maintain the software. Other
users can inherit those privileges if they belong to the `root` user group.

## V

### LTS version

Long-term support version. It is supported for **two years**, extendable by
another two with a long-term support contract. It receives security and critical
bug patches, not features from newer versions, and it coexists with **Feature
Releases**, which bring the new features. See
[Version and support policy](../parte-1/1.3-versiones-y-estabilidad.md).

## W

### Warp Update

Update system from the console itself. Its wizards download, apply and verify the
update, and there is also an offline mode for isolated environments. It is the
recommended way as opposed to the **manual update**. See
[Updates](../parte-1/1.4-actualizaciones.md).

### Watchdog

Feature that checks whether a system is running and, if it is down, restarts it.

### Widget

Interface element that provides a single point of interaction for a type of data.
It shows a layout of the information that the user can modify, such as a window
or a text box. Combined in an application, they hold the data processed by it and
the interactions available on that data.
