# Documentation guide for AI agents

## How to use this guide

| Step | Action | Where |
| --- | --- | --- |
| 1 | Resolve `latest`: read `versions.json` and take the `version` whose `aliases` list contains `latest` | `https://raw.githubusercontent.com/pandorafms/manual/main/versions.json` |
| 2 | Read the index of the edition in the user's language | `https://raw.githubusercontent.com/pandorafms/manual/main/<version>/llms.txt` |
| 3 | Open the chosen chapter (`.md` path from the index) | `https://raw.githubusercontent.com/pandorafms/manual/main/<version>/<path>.md` |
| 4 | Cite chapter and section by title | — |

| Language | Index | Edition root |
| --- | --- | --- |
| es | `<version>/llms.txt` | `<version>/` |
| en | `<version>/en/llms.txt` | `<version>/en/` |
| fr | `<version>/fr/llms.txt` | `<version>/fr/` |

## Site layout

| Item | Detail |
| --- | --- |
| Languages | es (version root), en (`en/`), fr (`fr/`) |
| Versions | `develop` (daily), `N` (closed, immutable), aliases `latest` and `lts` |
| Raw Markdown | Next to each page: `<path>.md` besides `<path>/index.html` |
| Same chapter in another language | Same relative path under `en/` or `fr/` |
| Where it is served today | `https://raw.githubusercontent.com/pandorafms/manual/main/` (GitHub); `https://pandorafms.com/docs/manual/latest/` when the server allows it |

| Part | Path |
| --- | --- |
| Part 01. Quick start | `parte-1/` |
| Part 02. Monitoring with Pandora FMS | `parte-2/` |
| Part 03. IT asset management and automation | `parte-3/` |
| Part 04. User and permission management | `parte-4/` |
| Part 05. Getting value from monitoring | `parte-5/` |
| Part 06. Scalability and complex environments | `parte-6/` |
| Part 07. Security and monitoring | `parte-7/` |
| Part 08. Pandora AI | `parte-8/` |
| Part 09. Other advanced aspects of Pandora FMS | `parte-9/` |
| Part 10. Database | `parte-10/` |
| Part 11. Technical appendices | `anexos/` |
| Part 12. Frequently asked questions (FAQ) | `parte-12/` |

## Chapter map

### Part 01. Quick start

| No. | Chapter | Path |
| --- | --- | --- |
| 1.1 | Installation | `parte-1/1.1-instalacion.md` |
| 1.2 | Introduction and architecture | `parte-1/1.2-introduccion-y-arquitectura.md` |
| 1.3 | Version and support policy | `parte-1/1.3-versiones-y-estabilidad.md` |
| 1.4 | Updates | `parte-1/1.4-actualizaciones.md` |
| 1.5 | Licensing | `parte-1/1.5-licenciamiento.md` |

### Part 02. Monitoring with Pandora FMS

| No. | Chapter | Path |
| --- | --- | --- |
| 2.1 | Monitoring with EndPoints | `parte-2/2.1-monitorizacion-con-endpoints.md` |
| 2.2 | Credential manager | `parte-2/2.2-gestor-de-credenciales.md` |
| 2.3 | Automatic monitoring and discovery with Discovery | `parte-2/2.3-monitorizacion-y-descubrimiento-automatico-con-discovery.md` |
| 2.4 | Network discovery with Host & Devices | `parte-2/2.4-descubrimiento-de-redes-con-host-y-dispositivos.md` |
| 2.5 | Console tasks | `parte-2/2.5-tareas-de-consola.md` |
| 2.6 | Network monitoring | `parte-2/2.6-monitorizacion-de-redes.md` |
| 2.7 | SNMP trap monitoring | `parte-2/2.7-monitorizacion-de-traps-snmp.md` |
| 2.8 | Netflow traffic monitoring | `parte-2/2.8-monitorizacion-de-trafico-con-netflow.md` |
| 2.9 | Collections | `parte-2/2.9-colecciones.md` |
| 2.10 | Monitoring policies | `parte-2/2.10-politicas-de-monitorizacion.md` |
| 2.11 | Bulk operations | `parte-2/2.11-operaciones-masivas.md` |
| 2.12 | Application monitoring | `parte-2/2.12-monitorizacion-de-aplicaciones.md` |
| 2.13 | Container and orchestrator monitoring | `parte-2/2.13-monitorizacion-de-contenedores-y-orquestadores.md` |
| 2.14 | User experience (UX) monitoring | `parte-2/2.14-monitorizacion-de-experiencia-de-usuario-ux.md` |
| 2.15 | Cloud environment monitoring | `parte-2/2.15-monitorizacion-entornos-cloud.md` |
| 2.16 | Virtualized environment monitoring | `parte-2/2.16-monitorizacion-entornos-virtualizados.md` |
| 2.17 | IoT monitoring | `parte-2/2.17-monitorizacion-iot.md` |
| 2.18 | API monitoring | `parte-2/2.18-monitorizacion-de-apis.md` |
| 2.19 | Log collection and monitoring | `parte-2/2.19-recoleccion-y-monitorizacion-de-logs.md` |
| 2.20 | Common module configuration | `parte-2/2.20-configuracion-comun-de-los-modulos.md` |
| 2.21 | Common agent configuration | `parte-2/2.21-configuracion-comun-de-los-agentes.md` |

### Part 03. IT asset management and automation

| No. | Chapter | Path |
| --- | --- | --- |
| 3.1 | Inventory | `parte-3/3.1-inventario.md` |
| 3.2 | Remote control with RC | `parte-3/3.2-control-remoto-con-rc.md` |
| 3.8 | Planned downtime | `parte-3/3.8-paradas-planificadas.md` |

### Part 04. User and permission management

| No. | Chapter | Path |
| --- | --- | --- |
| 4.1 | Groups, users, profiles and tags | `parte-4/4.1-grupos-perfiles-y-tags.md` |
| 4.2 | External authentication and centralized access | `parte-4/4.2-autenticacion-externa-y-centralizacion-de-accesos.md` |
| 4.3 | Advanced security and visibility (advanced ACL) | `parte-4/4.3-seguridad-y-visibilidad-avanzada-enterprise-acl.md` |
| 4.4 | Naming and tagging best practices | `parte-4/4.4-buenas-practicas-de-etiquetado-naming-tags.md` |

### Part 05. Getting value from monitoring

| No. | Chapter | Path |
| --- | --- | --- |
| 5.4 | Centralized event console | `parte-5/5.4-consola-de-eventos-centralizada.md` |
| 5.5 | Alerts and notifications | `parte-5/5.5-alertas-y-notificaciones.md` |
| 5.8 | Incident management / ITSM | `parte-5/5.8-gestion-de-incidencias-itsm.md` |
| 5.11 | GIS maps | `parte-5/5.11-mapas-gis.md` |
| 5.12 | Mobile app | `parte-5/5.12-aplicacion-movil.md` |

### Part 06. Scalability and complex environments

| No. | Chapter | Path |
| --- | --- | --- |
| 6.1 | Distributed architectures | `parte-6/6.1-arquitecturas-distribuidas.md` |
| 6.2 | Satellite servers | `parte-6/6.2-servidores-satelite.md` |
| 6.3 | Command Center | `parte-6/6.3-command-center.md` |
| 6.4 | Automatic agent distribution and installation | `parte-6/6.4-distribucion-e-instalacion-automatica-de-agentes.md` |
| 6.5 | Historical database | `parte-6/6.5-base-de-datos-de-historico.md` |
| 6.7 | Database optimization | `parte-6/6.7-optimizacion-de-la-base-de-datos.md` |
| 6.8 | Backup and restore | `parte-6/6.8-backup-y-restore.md` |

### Part 07. Security and monitoring

| No. | Chapter | Path |
| --- | --- | --- |
| 7.2 | SIEM | `parte-7/7.2-siem.md` |
| 7.3 | SOAR | `parte-7/7.3-soar.md` |
| 7.4 | Vulnerability analysis | `parte-7/7.4-analisis-de-vulnerabilidades.md` |
| 7.5 | Hardening | `parte-7/7.5-hardening.md` |
| 7.6 | FIM | `parte-7/7.6-fim.md` |
| 7.7 | Security monitoring | `parte-7/7.7-monitorizacion-de-seguridad.md` |
| 7.10 | Compliance: NIS2, ISO 27001 and ENS | `parte-7/7.10-compliance-nis2-iso-27001-y-ens.md` |
| 7.11 | Secure configuration | `parte-7/7.11-configuracion-segura.md` |

### Part 08. Pandora AI

| No. | Chapter | Path |
| --- | --- | --- |
| 8.1 | Introduction and installation | `parte-8/8.1-introduccion-e-instalacion.md` |
| 8.2 | Using the chat | `parte-8/8.2-uso-del-chat.md` |
| 8.3 | Task automation | `parte-8/8.3-automatizacion-de-tareas.md` |
| 8.4 | Security | `parte-8/8.4-seguridad.md` |
| 8.5 | Audit | `parte-8/8.5-auditoria.md` |

### Part 09. Other advanced aspects of Pandora FMS

| No. | Chapter | Path |
| --- | --- | --- |
| 9.1 | Full EndPoint configuration reference | `parte-9/9.1-referencia-completa-de-configuracion-del-endpoint.md` |
| 9.2 | Full console configuration reference | `parte-9/9.2-referencia-completa-de-configuracion-de-la-consola.md` |
| 9.3 | Full server configuration reference | `parte-9/9.3-referencia-completa-de-configuracion-del-servidor.md` |
| 9.4 | Full Tentacle reference (server and client) | `parte-9/9.4-referencia-completa-de-tentacle.md` |
| 9.5 | Database encryption | `parte-9/9.5-cifrado-de-la-base-de-datos.md` |
| 9.6 | Cluster monitoring | `parte-9/9.6-monitorizacion-de-clusters.md` |

### Part 10. Database

| No. | Chapter | Path |
| --- | --- | --- |
| 10.1 | Database schema | `parte-10/10.1-esquema-de-la-base-de-datos.md` |
| 10.2 | Table reference | `parte-10/10.2-referencia-de-tablas.md` |

### Part 11. Technical appendices

| No. | Chapter | Path |
| --- | --- | --- |
| A1 | Upgrading PHP versions | `anexos/a1-actualizacion-de-versiones-de-php.md` |
| A2 | Glossary of terms | `anexos/a2-glosario-de-terminos.md` |
| A3 | Compatibility and migration to the new server architecture | `anexos/a3-compatibilidad-y-migracion-a-la-nueva-arquitectura-de-servidores.md` |
| A4 | Extending the SNMP and WMI wizards with custom components | `anexos/a4-ampliar-los-asistentes-snmp-y-wmi-con-componentes-propios.md` |
| A5 | Configuring fprobe for Netflow | `anexos/a5-configuracion-de-fprobe-para-netflow.md` |
| A6 | Upgrading from LTS 777 to 800 | `anexos/a6-actualizacion-de-la-lts-777-a-la-800.md` |
| A7 | Documentation guide for AI agents | `anexos/a7-guia-de-la-documentacion-para-agentes-de-ia.md` |

### Part 12. Frequently asked questions (FAQ)

| No. | Chapter | Path |
| --- | --- | --- |
| 12.1 | What is this FAQ | `parte-12/12.1-que-es-este-faq.md` |
| 12.2 | Server and database | `parte-12/12.2-servidor-y-base-de-datos.md` |
| 12.3 | Agents and systems | `parte-12/12.3-agentes-y-sistemas.md` |
| 12.4 | Web console and licences | `parte-12/12.4-consola-web-y-licencias.md` |
| 12.5 | Modules and network | `parte-12/12.5-modulos-y-red.md` |
| 12.6 | Alerts and events | `parte-12/12.6-alertas-y-eventos.md` |
| 12.7 | Reports, logs and email | `parte-12/12.7-informes-logs-y-correo.md` |
| 12.8 | Large environments | `parte-12/12.8-entornos-grandes.md` |
| 12.9 | Automation and plugins | `parte-12/12.9-automatizacion-y-plugins.md` |
| 12.10 | Bulk operations | `parte-12/12.10-operaciones-masivas.md` |

## If you look for X, go to Y

| If you look for | Go to |
| --- | --- |
| Install Pandora FMS | [1.1 Installation](../parte-1/1.1-instalacion.md) |
| Upgrade to a newer version | [1.4 Updates](../parte-1/1.4-actualizaciones.md) |
| LTS versions, stability and support | [1.3 Version and support policy](../parte-1/1.3-versiones-y-estabilidad.md) |
| Licenses and license limits | [1.5 Licensing](../parte-1/1.5-licenciamiento.md) |
| Monitor a server with an EndPoint | [2.1 Monitoring with EndPoints](../parte-2/2.1-monitorizacion-con-endpoints.md) |
| Discover network devices automatically | [2.4 Network discovery with Host & Devices](../parte-2/2.4-descubrimiento-de-redes-con-host-y-dispositivos.md) |
| Monitor network devices over SNMP | [2.6 Network monitoring](../parte-2/2.6-monitorizacion-de-redes.md) |
| Receive SNMP traps | [2.7 SNMP trap monitoring](../parte-2/2.7-monitorizacion-de-traps-snmp.md) |
| Collect and monitor logs | [2.19 Log collection and monitoring](../parte-2/2.19-recoleccion-y-monitorizacion-de-logs.md) |
| Configure a module (interval, thresholds) | [2.20 Common module configuration](../parte-2/2.20-configuracion-comun-de-los-modulos.md) |
| Apply the same configuration to many agents | [2.10 Monitoring policies](../parte-2/2.10-politicas-de-monitorizacion.md) |
| Create alerts and notifications | [5.5 Alerts and notifications](../parte-5/5.5-alertas-y-notificaciones.md) |
| View and manage events | [5.4 Centralized event console](../parte-5/5.4-consola-de-eventos-centralizada.md) |
| Users, groups and permissions | [4.1 Groups, users, profiles and tags](../parte-4/4.1-grupos-perfiles-y-tags.md) |
| Sign in with LDAP, Active Directory or SAML | [4.2 External authentication and centralized access](../parte-4/4.2-autenticacion-externa-y-centralizacion-de-accesos.md) |
| Spread Pandora FMS across several servers | [6.1 Distributed architectures](../parte-6/6.1-arquitecturas-distribuidas.md) |
| Manage several installations from a single console | [6.3 Command Center](../parte-6/6.3-command-center.md) |
| Optimize or clean up the database | [6.7 Database optimization](../parte-6/6.7-optimizacion-de-la-base-de-datos.md) |
| Backup and restore | [6.8 Backup and restore](../parte-6/6.8-backup-y-restore.md) |
| Collect and correlate security events (SIEM) | [7.2 SIEM](../parte-7/7.2-siem.md) |
| Use the Pandora AI chat | [8.2 Using the chat](../parte-8/8.2-uso-del-chat.md) |
| EndPoint configuration file parameters | [9.1 Full EndPoint configuration reference](../parte-9/9.1-referencia-completa-de-configuracion-del-endpoint.md) |
| Console configuration parameters | [9.2 Full console configuration reference](../parte-9/9.2-referencia-completa-de-configuracion-de-la-consola.md) |
| Server configuration parameters | [9.3 Full server configuration reference](../parte-9/9.3-referencia-completa-de-configuracion-del-servidor.md) |
| Database structure | [10.1 Database schema](../parte-10/10.1-esquema-de-la-base-de-datos.md) |
| Frequently asked questions and common problems | [12.1 What is this FAQ](../parte-12/12.1-que-es-este-faq.md) |
| Meaning of a term (including former names) | [A2 Glossary of terms](../anexos/a2-glosario-de-terminos.md) |
| Move from LTS 777 to 800 | [A6 Upgrading from LTS 777 to 800](../anexos/a6-actualizacion-de-la-lts-777-a-la-800.md) |

## Conventions the agent must follow

| Rule | Detail |
| --- | --- |
| Terminology | Always use the canonical term from the table below; former names and synonyms are in the glossary ([A2](a2-glosario-de-terminos.md)) |
| Code identifiers | Never translated or renamed: tables, tokens, files and keys are quoted as they are |
| Integrations (plugins) | Link to `https://pandorafms.com/docs/integrations/latest/<language>/`; do not cite the repository |
| Screenshots | Console in English in all three editions |
| Answer language | The user's; open the edition in that language |

| Canonical term |
| --- |
| RMM |
| paquete .disco |
| fine tuning |
| Versión LTS |
| EndPoint |
| Pandora ONE |
| Pandora NMS |
| Pandora RMM |
| Pandora SIEM |
| Pandora RC |
| Pandora ITSM |
| Command Center |
| cifrado |
| script |
| kernel panic |
| Pandora AI |
| el asistente |
| pandora-cli |

## How to search

| Step | Action |
| --- | --- |
| 1 | Look the question up in «If you look for X, go to Y» |
| 2 | If it is not there, search by title in the edition index (`llms.txt`) |
| 3 | If that is not enough, search `search/search_index.<language>.json` of the version |
| 4 | Open the chapter and find the section by its title |
| 5 | If the answer is not there, say so; do not invent it |

## What the documentation does not cover

### Chapters still to be written (do not read them: they have no content)

| No. | Chapter |
| --- | --- |
| 3.3 | Automatic software distribution |
| 3.4 | Remote script and command execution |
| 3.5 | System patching |
| 3.6 | Network configuration management (NCM) |
| 3.7 | IP address management (IPAM) |
| 3.9 | Asset integration with ITSM |
| 5.1 | Dashboards |
| 5.2 | Reports |
| 5.3 | Business and service monitoring |
| 5.6 | Visual consoles |
| 5.7 | Network topology maps |
| 5.9 | Predictive analysis and capacity planning |
| 6.6 | Self-provisioning mechanisms |
| 6.9 | High availability (HA) |
| 7.1 | Pandora security architecture |
| 7.8 | Internal audit |
| 7.9 | Dynamic IoC integrations (MISP) and custom rule creation |
| 9.7 | Creating discovery plugins |
| 9.8 | Creating local plugins |
| 9.9 | Creating remote plugins |
| 9.10 | Creating console extensions |
| 9.12 | Advanced automatic discovery (IPMI, etc.) |
| 9.13 | Troubleshooting with Pandora |
| 9.14 | Volume analysis and high-capacity design |
