# Pandora FMS — Product documentation

Pandora FMS is a monitoring platform. It watches servers, networks,
applications and services, and raises an alert when something leaves the
normal range before the end user notices. It uses **EndPoints** installed on
the machine, remote checks that do not touch the target, **Discovery**
to find on its own what is on the network, and an event and alert engine that
decides who to bother and when. Dashboards, reports and maps sit on top of
that data, so the information serves the person reading it, not only the
person collecting it.

This documentation covers the product: what to install, how to configure it
and what each piece does. It is not a network architecture manual or a
monitoring guide; it is the Pandora FMS reference.

The documentation is written chapter by chapter from the same outline in both
languages. This English edition translates the approved Spanish text; missing
sections appear as "Pending draft" in both languages.

## Where to start

If you are installing Pandora FMS for the first time, start with
[Part 01 — Installation](parte-1/1.1-instalacion.md): it covers the server,
the console, the EndPoint and the satellite server, with their prerequisites.
If you already run an environment and you are after a specific token or an
option's exact detail,
[Part 09](parte-9/9.1-referencia-completa-de-configuracion-del-endpoint.md) is
the full technical reference. The appendices (Part 11) cover one-off
procedures and the glossary of terms.

## Documentation map

| Part | Content |
|---|---|
| [01. Quick start](parte-1/1.1-instalacion.md) | Installation, architecture, version and support policy, upgrades and licensing |
| [02. Monitoring with Pandora FMS](parte-2/2.1-monitorizacion-con-endpoints.md) | EndPoints, credentials, Discovery, Host and devices, console tasks, networks, NetFlow, policies and monitoring by domain (applications, containers, UX, Cloud, IoT, APIs, logs) |
| [03. IT asset management and automation](parte-3/3.1-inventario.md) | Inventory, remote control, software distribution, patch management, NCM, IPAM, ITSM |
| [04. User and permission management](parte-4/4.1-grupos-perfiles-y-tags.md) | Groups, profiles, tags, external authentication, Enterprise ACL |
| [05. Getting value from monitoring](parte-5/5.1-dashboards.md) | Dashboards, reports, events, alerts, maps, capacity planning |
| [06. Scalability and complex environments](parte-6/6.1-arquitecturas-distribuidas.md) | Distributed architectures, satellites, Command Center, historical database, high availability |
| [07. Security and monitoring](parte-7/7.1-arquitectura-de-seguridad-de-pandora.md) | SIEM, SOAR, vulnerabilities, hardening, FIM, compliance |
| [08. Pandora AI](parte-8/8.1-introduccion-e-instalacion.md) | Introduction, installation, chat usage, scheduled tasks, security and audit |
| [09. Other advanced aspects of Pandora FMS](parte-9/9.1-referencia-completa-de-configuracion-del-endpoint.md) | Full configuration reference, plugins, REST API, troubleshooting |
| [10. Database](parte-10/10.1-esquema-de-la-base-de-datos.md) | Database schema: map by areas, main tables, codes, history and full table reference |
| [11. Technical appendices](anexos/a1-actualizacion-de-versiones-de-php.md) | One-off procedures and glossary of terms |
| [12. Frequently asked questions (FAQ)](parte-12/12.1-que-es-este-faq.md) | Recurring questions from the community and support, reviewed and brought up to date, ordered by topic |

### Frequently asked questions (FAQ)

Part 12 collects the most frequent questions, already checked against the code
and updated. Nine sections by topic, plus the landing page:

- [12.1 What is this FAQ](parte-12/12.1-que-es-este-faq.md) — what you will
  find here and the section index.
- [12.2 Server and database](parte-12/12.2-servidor-y-base-de-datos.md) — the
  server that does not start or falls over, and a slow or damaged database.
- [12.3 Agents and systems](parte-12/12.3-agentes-y-sistemas.md) — the agent
  that does not show up, Tentacle, the XML queues and what is specific to
  Windows and Linux.
- [12.4 Web console and licences](parte-12/12.4-consola-web-y-licencias.md) —
  access, security settings and the licence (renewing it).
- [12.5 Modules and network](parte-12/12.5-modulos-y-red.md) — ICMP, WMI, web
  checks, MIBs, traps and port 162.
- [12.6 Alerts and events](parte-12/12.6-alertas-y-eventos.md) — alerts that
  do not fire, alerts that fire too often and the notification email.
- [12.7 Reports, logs and email](parte-12/12.7-informes-logs-y-correo.md) —
  PDFs that do not come out, collections, the log viewer and email that does
  not arrive.
- [12.8 Large environments](parte-12/12.8-entornos-grandes.md) — Command
  Center, several nodes, event replication and high availability.
- [12.9 Automation and plugins](parte-12/12.9-automatizacion-y-plugins.md) —
  CLI, API, macros and plugins.
- [12.10 Bulk operations](parte-12/12.10-operaciones-masivas.md) — deploying
  agents, bulk configurations and clean-ups.

!!! note "Documentation in progress"
    Not all chapters are written yet. The missing ones will be completed over
    time; if you reach one without content, come back later.

> This documentation covers only the **product**. The monitoring book is now
> managed in a separate repository.
