# Guía de la documentación para agentes de IA

## Cómo usar esta guía

| Paso | Acción | Dónde |
| --- | --- | --- |
| 1 | Resolver `latest`: leer `versions.json` y tomar la `version` cuya lista `aliases` contiene `latest` | `https://raw.githubusercontent.com/pandorafms/manual/main/versions.json` |
| 2 | Leer el índice de la edición en el idioma del usuario | `https://raw.githubusercontent.com/pandorafms/manual/main/<version>/llms.txt` |
| 3 | Abrir el capítulo elegido (ruta `.md` del índice) | `https://raw.githubusercontent.com/pandorafms/manual/main/<version>/<ruta>.md` |
| 4 | Citar capítulo y apartado por su título | — |

| Idioma | Índice | Raíz de la edición |
| --- | --- | --- |
| es | `<version>/llms.txt` | `<version>/` |
| en | `<version>/en/llms.txt` | `<version>/en/` |
| fr | `<version>/fr/llms.txt` | `<version>/fr/` |

## Organización del sitio

| Elemento | Detalle |
| --- | --- |
| Idiomas | es (raíz de la versión), en (`en/`), fr (`fr/`) |
| Versiones | `develop` (diaria), `N` (cerrada, inmutable), alias `latest` y `lts` |
| Markdown crudo | Junto a cada página: `<ruta>.md` además de `<ruta>/index.html` |
| Mismo capítulo en otro idioma | Misma ruta relativa bajo `en/` o `fr/` |
| Dónde se sirve hoy | `https://raw.githubusercontent.com/pandorafms/manual/main/` (GitHub); `https://pandorafms.com/docs/manual/latest/` cuando el servidor lo permita |

| Parte | Ruta |
| --- | --- |
| Parte 01. Arranque rápido | `parte-1/` |
| Parte 02. Monitorización con Pandora FMS | `parte-2/` |
| Parte 03. Gestión de activos y automatización IT | `parte-3/` |
| Parte 04. Gestión de usuarios y permisos | `parte-4/` |
| Parte 05. Dando valor a la monitorización | `parte-5/` |
| Parte 06. Escalabilidad y entornos complejos | `parte-6/` |
| Parte 07. Seguridad y monitorización | `parte-7/` |
| Parte 08. Pandora AI | `parte-8/` |
| Parte 09. Otros aspectos avanzados de Pandora FMS | `parte-9/` |
| Parte 10. Base de datos | `parte-10/` |
| Parte 11. Anexos técnicos | `anexos/` |
| Parte 12. Preguntas frecuentes (FAQ) | `parte-12/` |
| Parte 13. API v2 | `parte-13/` |

## Mapa de capítulos

### Parte 01. Arranque rápido

| N.º | Capítulo | Ruta |
| --- | --- | --- |
| 1.1 | Instalación | `parte-1/1.1-instalacion.md` |
| 1.2 | Introducción y arquitectura | `parte-1/1.2-introduccion-y-arquitectura.md` |
| 1.3 | Política de versiones y soporte | `parte-1/1.3-versiones-y-estabilidad.md` |
| 1.4 | Actualizaciones | `parte-1/1.4-actualizaciones.md` |
| 1.5 | Licenciamiento | `parte-1/1.5-licenciamiento.md` |

### Parte 02. Monitorización con Pandora FMS

| N.º | Capítulo | Ruta |
| --- | --- | --- |
| 2.1 | Monitorización con EndPoints | `parte-2/2.1-monitorizacion-con-endpoints.md` |
| 2.2 | Gestor de credenciales | `parte-2/2.2-gestor-de-credenciales.md` |
| 2.3 | Monitorización y descubrimiento automático con Discovery | `parte-2/2.3-monitorizacion-y-descubrimiento-automatico-con-discovery.md` |
| 2.4 | Descubrimiento de redes con Host y dispositivos | `parte-2/2.4-descubrimiento-de-redes-con-host-y-dispositivos.md` |
| 2.5 | Tareas de consola | `parte-2/2.5-tareas-de-consola.md` |
| 2.6 | Monitorización de redes | `parte-2/2.6-monitorizacion-de-redes.md` |
| 2.7 | Monitorización de traps SNMP | `parte-2/2.7-monitorizacion-de-traps-snmp.md` |
| 2.8 | Monitorización de tráfico con Netflow | `parte-2/2.8-monitorizacion-de-trafico-con-netflow.md` |
| 2.9 | Colecciones | `parte-2/2.9-colecciones.md` |
| 2.10 | Políticas de monitorización | `parte-2/2.10-politicas-de-monitorizacion.md` |
| 2.11 | Operaciones masivas | `parte-2/2.11-operaciones-masivas.md` |
| 2.12 | Monitorización de aplicaciones | `parte-2/2.12-monitorizacion-de-aplicaciones.md` |
| 2.13 | Monitorización de contenedores y orquestadores | `parte-2/2.13-monitorizacion-de-contenedores-y-orquestadores.md` |
| 2.14 | Monitorización de experiencia de usuario (UX) | `parte-2/2.14-monitorizacion-de-experiencia-de-usuario-ux.md` |
| 2.15 | Monitorización de entornos Cloud | `parte-2/2.15-monitorizacion-entornos-cloud.md` |
| 2.16 | Monitorización de entornos virtualizados | `parte-2/2.16-monitorizacion-entornos-virtualizados.md` |
| 2.17 | Monitorización IoT | `parte-2/2.17-monitorizacion-iot.md` |
| 2.18 | Monitorización de APIs | `parte-2/2.18-monitorizacion-de-apis.md` |
| 2.19 | Recolección y monitorización de logs | `parte-2/2.19-recoleccion-y-monitorizacion-de-logs.md` |
| 2.20 | Configuración común de los módulos | `parte-2/2.20-configuracion-comun-de-los-modulos.md` |
| 2.21 | Configuración común de los agentes | `parte-2/2.21-configuracion-comun-de-los-agentes.md` |

### Parte 03. Gestión de activos y automatización IT

| N.º | Capítulo | Ruta |
| --- | --- | --- |
| 3.1 | Inventario | `parte-3/3.1-inventario.md` |
| 3.2 | Control remoto con RC | `parte-3/3.2-control-remoto-con-rc.md` |
| 3.8 | Paradas planificadas | `parte-3/3.8-paradas-planificadas.md` |

### Parte 04. Gestión de usuarios y permisos

| N.º | Capítulo | Ruta |
| --- | --- | --- |
| 4.1 | Grupos, usuarios, perfiles y tags | `parte-4/4.1-grupos-perfiles-y-tags.md` |
| 4.2 | Autenticación externa y centralización de accesos | `parte-4/4.2-autenticacion-externa-y-centralizacion-de-accesos.md` |
| 4.3 | Seguridad y visibilidad avanzada (ACL avanzada) | `parte-4/4.3-seguridad-y-visibilidad-avanzada-enterprise-acl.md` |
| 4.4 | Buenas prácticas de nombres y etiquetas | `parte-4/4.4-buenas-practicas-de-etiquetado-naming-tags.md` |

### Parte 05. Dando valor a la monitorización

| N.º | Capítulo | Ruta |
| --- | --- | --- |
| 5.4 | Consola de eventos centralizada | `parte-5/5.4-consola-de-eventos-centralizada.md` |
| 5.5 | Alertas y notificaciones | `parte-5/5.5-alertas-y-notificaciones.md` |
| 5.8 | Gestión de incidencias / ITSM | `parte-5/5.8-gestion-de-incidencias-itsm.md` |
| 5.11 | Mapas GIS | `parte-5/5.11-mapas-gis.md` |
| 5.12 | Aplicación móvil | `parte-5/5.12-aplicacion-movil.md` |

### Parte 06. Escalabilidad y entornos complejos

| N.º | Capítulo | Ruta |
| --- | --- | --- |
| 6.1 | Arquitecturas Distribuidas | `parte-6/6.1-arquitecturas-distribuidas.md` |
| 6.2 | Servidores satélite | `parte-6/6.2-servidores-satelite.md` |
| 6.3 | Command Center | `parte-6/6.3-command-center.md` |
| 6.4 | Distribución e instalación automática de agentes | `parte-6/6.4-distribucion-e-instalacion-automatica-de-agentes.md` |
| 6.5 | Base de datos de histórico | `parte-6/6.5-base-de-datos-de-historico.md` |
| 6.7 | Optimización de la Base de Datos | `parte-6/6.7-optimizacion-de-la-base-de-datos.md` |
| 6.8 | Backup y restore | `parte-6/6.8-backup-y-restore.md` |

### Parte 07. Seguridad y monitorización

| N.º | Capítulo | Ruta |
| --- | --- | --- |
| 7.2 | SIEM | `parte-7/7.2-siem.md` |
| 7.3 | SOAR | `parte-7/7.3-soar.md` |
| 7.4 | Análisis de vulnerabilidades | `parte-7/7.4-analisis-de-vulnerabilidades.md` |
| 7.5 | Hardening | `parte-7/7.5-hardening.md` |
| 7.6 | FIM | `parte-7/7.6-fim.md` |
| 7.7 | Monitorización de seguridad | `parte-7/7.7-monitorizacion-de-seguridad.md` |
| 7.10 | Compliance: NIS2, ISO 27001 y ENS | `parte-7/7.10-compliance-nis2-iso-27001-y-ens.md` |
| 7.11 | Configuración segura | `parte-7/7.11-configuracion-segura.md` |

### Parte 08. Pandora AI

| N.º | Capítulo | Ruta |
| --- | --- | --- |
| 8.1 | Introducción e instalación | `parte-8/8.1-introduccion-e-instalacion.md` |
| 8.2 | Uso del chat | `parte-8/8.2-uso-del-chat.md` |
| 8.3 | Automatización de tareas | `parte-8/8.3-automatizacion-de-tareas.md` |
| 8.4 | Seguridad | `parte-8/8.4-seguridad.md` |
| 8.5 | Auditoría | `parte-8/8.5-auditoria.md` |

### Parte 09. Otros aspectos avanzados de Pandora FMS

| N.º | Capítulo | Ruta |
| --- | --- | --- |
| 9.1 | Referencia completa de configuración del EndPoint | `parte-9/9.1-referencia-completa-de-configuracion-del-endpoint.md` |
| 9.2 | Referencia completa de configuración de la consola | `parte-9/9.2-referencia-completa-de-configuracion-de-la-consola.md` |
| 9.3 | Referencia completa de configuración del servidor | `parte-9/9.3-referencia-completa-de-configuracion-del-servidor.md` |
| 9.4 | Referencia completa de Tentacle (servidor y cliente) | `parte-9/9.4-referencia-completa-de-tentacle.md` |
| 9.5 | Cifrado de la base de datos | `parte-9/9.5-cifrado-de-la-base-de-datos.md` |
| 9.6 | Monitorización de clusters | `parte-9/9.6-monitorizacion-de-clusters.md` |
| 9.7 | Creación de plugins de discovery | `parte-9/9.7-creacion-de-plugins-de-discovery.md` |

### Parte 10. Base de datos

| N.º | Capítulo | Ruta |
| --- | --- | --- |
| 10.1 | Esquema de la base de datos | `parte-10/10.1-esquema-de-la-base-de-datos.md` |
| 10.2 | Referencia de tablas | `parte-10/10.2-referencia-de-tablas.md` |

### Parte 11. Anexos técnicos

| N.º | Capítulo | Ruta |
| --- | --- | --- |
| A1 | Actualización de versiones de PHP | `anexos/a1-actualizacion-de-versiones-de-php.md` |
| A2 | Glosario de términos | `anexos/a2-glosario-de-terminos.md` |
| A3 | Compatibilidad y migración a la nueva arquitectura de servidores | `anexos/a3-compatibilidad-y-migracion-a-la-nueva-arquitectura-de-servidores.md` |
| A4 | Ampliar los asistentes SNMP y WMI con componentes propios | `anexos/a4-ampliar-los-asistentes-snmp-y-wmi-con-componentes-propios.md` |
| A5 | Configuración de fprobe para Netflow | `anexos/a5-configuracion-de-fprobe-para-netflow.md` |
| A6 | Actualización de la LTS 777 a la 800 | `anexos/a6-actualizacion-de-la-lts-777-a-la-800.md` |
| A7 | Guía de la documentación para agentes de IA | `anexos/a7-guia-de-la-documentacion-para-agentes-de-ia.md` |

### Parte 12. Preguntas frecuentes (FAQ)

| N.º | Capítulo | Ruta |
| --- | --- | --- |
| 12.1 | Qué es este FAQ | `parte-12/12.1-que-es-este-faq.md` |
| 12.2 | Servidor y base de datos | `parte-12/12.2-servidor-y-base-de-datos.md` |
| 12.3 | Agentes y sistemas | `parte-12/12.3-agentes-y-sistemas.md` |
| 12.4 | Consola web y licencias | `parte-12/12.4-consola-web-y-licencias.md` |
| 12.5 | Módulos y red | `parte-12/12.5-modulos-y-red.md` |
| 12.6 | Alertas y eventos | `parte-12/12.6-alertas-y-eventos.md` |
| 12.7 | Informes, logs y correo | `parte-12/12.7-informes-logs-y-correo.md` |
| 12.8 | Entornos grandes | `parte-12/12.8-entornos-grandes.md` |
| 12.9 | Automatización y plugins | `parte-12/12.9-automatizacion-y-plugins.md` |
| 12.10 | Operaciones masivas | `parte-12/12.10-operaciones-masivas.md` |

### Parte 13. API v2

| N.º | Capítulo | Ruta |
| --- | --- | --- |
| 13.1 | Primeros pasos y autenticación | `parte-13/13.1-primeros-pasos-y-autenticacion.md` |
| 13.2 | Convenciones de la API: paginación, filtros y errores | `parte-13/13.2-convenciones-de-la-api.md` |
| 13.3 | Ejemplos de uso | `parte-13/13.3-ejemplos-de-uso.md` |
| 13.4 | API v2 endpoint reference | `parte-13/13.4-referencia-de-endpoints/index.md` |
| 13.4.1 | API v2 endpoints: Agents | `parte-13/13.4-referencia-de-endpoints/agents.md` |
| 13.4.2 | API v2 endpoints: Modules | `parte-13/13.4-referencia-de-endpoints/modules.md` |
| 13.4.3 | API v2 endpoints: Alerts | `parte-13/13.4-referencia-de-endpoints/alerts.md` |
| 13.4.4 | API v2 endpoints: Events | `parte-13/13.4-referencia-de-endpoints/events.md` |
| 13.4.5 | API v2 endpoints: Policies | `parte-13/13.4-referencia-de-endpoints/policies.md` |
| 13.4.6 | API v2 endpoints: Collections | `parte-13/13.4-referencia-de-endpoints/collections.md` |
| 13.4.7 | API v2 endpoints: Users and access | `parte-13/13.4-referencia-de-endpoints/users-and-access.md` |
| 13.4.8 | API v2 endpoints: Dashboards and notifications | `parte-13/13.4-referencia-de-endpoints/dashboards-and-notifications.md` |
| 13.4.9 | API v2 endpoints: Reports | `parte-13/13.4-referencia-de-endpoints/reports.md` |
| 13.4.10 | API v2 endpoints: Services and scheduled downtimes | `parte-13/13.4-referencia-de-endpoints/services-and-downtimes.md` |
| 13.4.11 | API v2 endpoints: Bulk operations and data | `parte-13/13.4-referencia-de-endpoints/bulk-operations-and-data.md` |
| 13.4.12 | API v2 endpoints: Security | `parte-13/13.4-referencia-de-endpoints/security.md` |
| 13.4.13 | API v2 endpoints: Pandora AI and ITSM | `parte-13/13.4-referencia-de-endpoints/ai-and-itsm.md` |
| 13.4.14 | API v2 endpoints: Network Configuration Manager | `parte-13/13.4-referencia-de-endpoints/ncm.md` |
| 13.4.15 | API v2 endpoints: RMM | `parte-13/13.4-referencia-de-endpoints/rmm.md` |

## Si buscas X, ve a Y

| Si buscas | Ve a |
| --- | --- |
| Instalar Pandora FMS | [1.1 Instalación](../parte-1/1.1-instalacion.md) |
| Actualizar a una versión nueva | [1.4 Actualizaciones](../parte-1/1.4-actualizaciones.md) |
| Versiones LTS, estabilidad y soporte | [1.3 Política de versiones y soporte](../parte-1/1.3-versiones-y-estabilidad.md) |
| Licencias y límites de la licencia | [1.5 Licenciamiento](../parte-1/1.5-licenciamiento.md) |
| Monitorizar un servidor con un EndPoint | [2.1 Monitorización con EndPoints](../parte-2/2.1-monitorizacion-con-endpoints.md) |
| Descubrir equipos de la red automáticamente | [2.4 Descubrimiento de redes con Host y dispositivos](../parte-2/2.4-descubrimiento-de-redes-con-host-y-dispositivos.md) |
| Monitorizar dispositivos de red por SNMP | [2.6 Monitorización de redes](../parte-2/2.6-monitorizacion-de-redes.md) |
| Recibir traps SNMP | [2.7 Monitorización de traps SNMP](../parte-2/2.7-monitorizacion-de-traps-snmp.md) |
| Recolectar y monitorizar logs | [2.19 Recolección y monitorización de logs](../parte-2/2.19-recoleccion-y-monitorizacion-de-logs.md) |
| Configurar un módulo (intervalo, umbrales) | [2.20 Configuración común de los módulos](../parte-2/2.20-configuracion-comun-de-los-modulos.md) |
| Aplicar la misma configuración a muchos agentes | [2.10 Políticas de monitorización](../parte-2/2.10-politicas-de-monitorizacion.md) |
| Crear alertas y notificaciones | [5.5 Alertas y notificaciones](../parte-5/5.5-alertas-y-notificaciones.md) |
| Ver y gestionar eventos | [5.4 Consola de eventos centralizada](../parte-5/5.4-consola-de-eventos-centralizada.md) |
| Usuarios, grupos y permisos | [4.1 Grupos, usuarios, perfiles y tags](../parte-4/4.1-grupos-perfiles-y-tags.md) |
| Iniciar sesión con LDAP, Active Directory o SAML | [4.2 Autenticación externa y centralización de accesos](../parte-4/4.2-autenticacion-externa-y-centralizacion-de-accesos.md) |
| Repartir Pandora FMS entre varios servidores | [6.1 Arquitecturas Distribuidas](../parte-6/6.1-arquitecturas-distribuidas.md) |
| Gestionar varias instalaciones desde una sola consola | [6.3 Command Center](../parte-6/6.3-command-center.md) |
| Optimizar o limpiar la base de datos | [6.7 Optimización de la Base de Datos](../parte-6/6.7-optimizacion-de-la-base-de-datos.md) |
| Copia de seguridad y restauración | [6.8 Backup y restore](../parte-6/6.8-backup-y-restore.md) |
| Recoger y correlar eventos de seguridad (SIEM) | [7.2 SIEM](../parte-7/7.2-siem.md) |
| Usar el chat de Pandora AI | [8.2 Uso del chat](../parte-8/8.2-uso-del-chat.md) |
| Parámetros del fichero de configuración del EndPoint | [9.1 Referencia completa de configuración del EndPoint](../parte-9/9.1-referencia-completa-de-configuracion-del-endpoint.md) |
| Parámetros de configuración de la consola | [9.2 Referencia completa de configuración de la consola](../parte-9/9.2-referencia-completa-de-configuracion-de-la-consola.md) |
| Parámetros de configuración del servidor | [9.3 Referencia completa de configuración del servidor](../parte-9/9.3-referencia-completa-de-configuracion-del-servidor.md) |
| Estructura de la base de datos | [10.1 Esquema de la base de datos](../parte-10/10.1-esquema-de-la-base-de-datos.md) |
| Preguntas frecuentes y problemas habituales | [12.1 Qué es este FAQ](../parte-12/12.1-que-es-este-faq.md) |
| Significado de un término (incluidos los nombres anteriores) | [A2 Glosario de términos](../anexos/a2-glosario-de-terminos.md) |
| Pasar de la LTS 777 a la 800 | [A6 Actualización de la LTS 777 a la 800](../anexos/a6-actualizacion-de-la-lts-777-a-la-800.md) |
| Llamar a la API v2 desde un script o un agente | [13.1 Primeros pasos y autenticación](../parte-13/13.1-primeros-pasos-y-autenticacion.md) |
| Paginar, filtrar y entender los errores de la API v2 | [13.2 Convenciones de la API: paginación, filtros y errores](../parte-13/13.2-convenciones-de-la-api.md) |
| Ejemplos de llamadas a la API v2 | [13.3 Ejemplos de uso](../parte-13/13.3-ejemplos-de-uso.md) |
| Buscar un endpoint de la API v2 (parámetros, campos y errores) | [13.4 API v2 endpoint reference](../parte-13/13.4-referencia-de-endpoints/index.md) |

## Convenciones que el agente debe respetar

| Regla | Detalle |
| --- | --- |
| Nomenclatura | Usar siempre la expresión canónica de la tabla siguiente; nombres anteriores y sinónimos, en el glosario ([A2](a2-glosario-de-terminos.md)) |
| Identificadores del código | No se traducen ni se renombran: tablas, tokens, ficheros y claves se citan tal cual |
| Integraciones (plugins) | Enlazar a `https://pandorafms.com/docs/integrations/latest/<idioma>/`; no citar el repositorio |
| Capturas | Interfaz en inglés en las tres ediciones |
| API v2 de una consola | El spec exacto de su versión está en `<consola>/api/v2/swagger.json` y su Swagger UI en `<consola>/api/documentation/`; la referencia del manual es la de la versión publicada |
| Idioma de la respuesta | El del usuario; abrir la edición de ese idioma |

| Expresión canónica |
| --- |
| RMM |
| paquete .disco |
| Ajuste fino |
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

## Cómo buscar

| Paso | Acción |
| --- | --- |
| 1 | Buscar la pregunta en «Si buscas X, ve a Y» |
| 2 | Si no está, buscar por título en el índice de la edición (`llms.txt`) |
| 3 | Si no basta, buscar en `search/search_index.<idioma>.json` de la versión |
| 4 | Abrir el capítulo y localizar el apartado por su título |
| 5 | Si la respuesta no aparece, decirlo; no inventarla |

## Qué no cubre la documentación

### Pendientes de redacción (no leerlos: no tienen contenido)

| N.º | Capítulo |
| --- | --- |
| 3.3 | Distribución automática de software |
| 3.4 | Ejecución remota de scripts y comandos |
| 3.5 | Parcheado de sistemas |
| 3.6 | Gestión de configuración de equipos de red (NCM) |
| 3.7 | Gestión de IP (IPAM) |
| 3.9 | Integración de activos con ITSM |
| 5.1 | Dashboards |
| 5.2 | Informes |
| 5.3 | Monitorización de negocio y servicios |
| 5.6 | Consolas Visuales |
| 5.7 | Mapas topológicos de red |
| 5.9 | Análisis predictivo y Capacity Planning |
| 6.6 | Mecanismos de autoprovisión |
| 6.9 | Alta Disponibilidad (HA) |
| 7.1 | Arquitectura de seguridad de Pandora |
| 7.8 | Auditoría interna |
| 7.9 | Integraciones dinámicas de IoC (MISP) y creación de reglas propias |
| 9.8 | Creación de plugins locales |
| 9.9 | Creación de plugins remotos |
| 9.10 | Creación de extensiones de consola |
| 9.12 | Descubrimiento automático avanzado (IPMI, etc.) |
| 9.13 | Troubleshooting con Pandora |
| 9.14 | Análisis de volumetría y diseños para alta capacidad |
