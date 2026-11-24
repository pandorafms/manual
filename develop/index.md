# Pandora FMS — Documentación de producto

Pandora FMS es una plataforma de monitorización: vigila servidores, redes,
aplicaciones y servicios, y avisa cuando algo se sale de lo normal antes de
que lo note el usuario final. Lo hace con **EndPoints** instalados dentro de
la máquina, con comprobaciones remotas que no tocan el destino, con
**Discovery** para encontrar por sí solo lo que hay en la red y con un motor de eventos y
alertas que decide a quién molestar y cuándo. Encima de esos datos se montan
dashboards, informes y mapas para que la información sirva a quien la mira,
no solo a quien la recoge.

Esta documentación cubre el producto: qué instalar, cómo configurarlo y qué
hace cada pieza. No es un manual de arquitectura de red ni una guía general
de monitorización; es la referencia de Pandora FMS.

## Por dónde empezar

Si vas a instalar Pandora FMS por primera vez, empieza por la
[Parte 01 — Instalación](parte-1/1.1-instalacion.md): cubre servidor, consola,
EndPoint y satélite, con sus requisitos previos. Si ya tienes un entorno en
marcha y buscas un token concreto o el detalle exacto de una opción, la
[Parte 09](parte-9/9.1-referencia-completa-de-configuracion-del-endpoint.md)
es la referencia técnica completa. Los anexos (Parte 11) recogen
procedimientos puntuales y el glosario de términos.

## Mapa de la documentación

| Parte | Contenido |
|---|---|
| [01. Arranque rápido](parte-1/1.1-instalacion.md) | Instalación, arquitectura, política de versiones y soporte, actualizaciones y licenciamiento |
| [02. Monitorización con Pandora FMS](parte-2/2.1-monitorizacion-con-endpoints.md) | EndPoints, credenciales, Discovery, Host y dispositivos, tareas de consola, redes, netflow, políticas y monitorización por dominio (aplicaciones, contenedores, UX, Cloud, IoT, APIs, logs) |
| [03. Gestión de activos y automatización IT](parte-3/3.1-inventario.md) | Inventario, control remoto, distribución de software, parcheado, NCM, IPAM, ITSM |
| [04. Gestión de usuarios y permisos](parte-4/4.1-grupos-perfiles-y-tags.md) | Grupos, perfiles, tags, autenticación externa, ACL Enterprise |
| [05. Dando valor a la monitorización](parte-5/5.1-dashboards.md) | Dashboards, informes, eventos, alertas, mapas, capacity planning |
| [06. Escalabilidad y entornos complejos](parte-6/6.1-arquitecturas-distribuidas.md) | Arquitecturas distribuidas, satélites, Command Center, base de datos de histórico, alta disponibilidad |
| [07. Seguridad y monitorización](parte-7/7.1-arquitectura-de-seguridad-de-pandora.md) | SIEM, SOAR, vulnerabilidades, hardening, FIM, compliance |
| [08. Pandora AI](parte-8/8.1-introduccion-e-instalacion.md) | Introducción, instalación, uso del chat, tareas programadas, seguridad y auditoría |
| [09. Otros aspectos avanzados](parte-9/9.1-referencia-completa-de-configuracion-del-endpoint.md) | Referencia completa de configuración, plugins, API REST, troubleshooting |
| [10. Base de datos](parte-10/10.1-esquema-de-la-base-de-datos.md) | Esquema de la base de datos: mapa por áreas, tablas principales, códigos, histórico y referencia completa de tablas |
| [11. Anexos técnicos](anexos/a1-actualizacion-de-versiones-de-php.md) | Procedimientos puntuales y glosario de términos |
| [12. Preguntas frecuentes (FAQ)](parte-12/12.1-que-es-este-faq.md) | Dudas repetidas de la comunidad y del soporte, revisadas y puestas al día, ordenadas por tema |

### Preguntas frecuentes (FAQ)

La Parte 12 recoge las dudas que más se repiten, ya contrastadas con el código y
puestas al día. Nueve secciones por tema, más la portada:

- [12.1 Qué es este FAQ](parte-12/12.1-que-es-este-faq.md) — qué encontrarás aquí y el índice de las secciones.
- [12.2 Servidor y base de datos](parte-12/12.2-servidor-y-base-de-datos.md) — el servidor que no arranca o se cae, y la base de datos lenta o dañada.
- [12.3 Agentes y sistemas](parte-12/12.3-agentes-y-sistemas.md) — el agente que no aparece, Tentacle, las colas de XML y lo propio de Windows y Linux.
- [12.4 Consola web y licencias](parte-12/12.4-consola-web-y-licencias.md) — acceso, ajustes de seguridad y la licencia (renovarla).
- [12.5 Módulos y red](parte-12/12.5-modulos-y-red.md) — ICMP, WMI, chequeos web, MIBs, traps y el puerto 162.
- [12.6 Alertas y eventos](parte-12/12.6-alertas-y-eventos.md) — alertas que no saltan, las que saltan de más y el correo de aviso.
- [12.7 Informes, logs y correo](parte-12/12.7-informes-logs-y-correo.md) — PDF que no salen, colecciones, visor de logs y correo que no llega.
- [12.8 Entornos grandes](parte-12/12.8-entornos-grandes.md) — Command Center, varios nodos, réplica de eventos y alta disponibilidad.
- [12.9 Automatización y plugins](parte-12/12.9-automatizacion-y-plugins.md) — CLI, API, macros y plugins.
- [12.10 Operaciones masivas](parte-12/12.10-operaciones-masivas.md) — desplegar agentes, configuraciones masivas y limpiezas.

!!! note "Documentación en curso"
    No todos los capítulos están redactados todavía. Los que faltan se irán
    completando; si llegas a uno sin contenido, vuelve más adelante.
