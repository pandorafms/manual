# Compatibilidad y migración a la nueva arquitectura de servidores

`Pandora Server` reúne servidores especializados en una aplicación multihilo:
cada uno recorre su propia cola de tareas (módulos que procesar, agentes
que escanear, alertas que evaluar) con su número de hilos. Este anexo describe cómo se
reparten hoy la monitorización remota y qué queda de la generación anterior
de instancias especializadas por tipo de comprobación. El número de procesos
del sistema no se deduce de ese reparto.

## Por qué menos servidores

La generación anterior distinguía más instancias especializadas: ICMP, SNMP,
WMI, plugins remotos e inventario remoto, entre otras. La wiki describe un
consumo de memoria alto incluso antes de procesar módulos; no establece que
cada subtipo equivaliese a un proceso independiente del sistema operativo.

El cambio agrupa varios tipos de comprobación en un mismo servidor, con más
hilos por dentro. El consumidor de red puede atender WMI e ICMP cuando
`networkhpserver` está desactivado, sin necesitar una instancia especializada
para cada tipo. Cada comprobación conserva su propio tiempo de espera: agrupar servidores no
significa igualar sus timeouts.

## Inventario histórico de servidores

La wiki enumera **21 denominaciones de la generación anterior**. Es un
inventario histórico, no la lista de servidores que arranca la configuración
actual ni una previsión de los que existirán en otras versiones:

Data Server · SNMP Console · Syslog Server · Export Server · Sync Server ·
Discovery Server · WEB Server · Network Server · WMI Server · Plugins Server ·
Inventory Server · ICMP Server · SNMP Server · Event Server · Log Server ·
SIEM Server · NetFlow Server (incluido sFlow) · NCM Server ·
Policy Manager Server · WUX Server · MADE Server.

En esta lista, **SNMP Server** designaba comprobaciones de módulos SNMP;
**SNMP Console** recibía traps. Los nombres antiguos no equivalen por sí
solos a instancias especializadas en el arranque actual.

## Qué hace cada servidor hoy

De toda la familia de servidores que existía, solo tres se reparten hoy la
monitorización remota (agentes sin EndPoint, o EndPoints comprobados también
desde fuera):

| Servidor | Token | Qué ejecuta |
|---|---|---|
| Red (`Network Server`) | `networkserver` | TCP, comandos remotos (SSH y Windows remoto), WMI, módulos de predicción y módulos web; también ICMP y SNMP ordinarios si `networkhpserver` está desactivado explícitamente |
| Red de alto rendimiento (`Network HP Server`) | `networkhpserver` | ICMP en lote con `fping` y SNMP en lote con `pandorafsnmp` (v1, v2c y v3) |
| Heavy (`Heavy Server`) | `heavyserver` | Plugins remotos de servidor, inventario remoto, gestión de configuración de equipos de red ([NCM](../parte-3/3.6-gestion-de-configuracion-de-equipos-de-red-ncm.md)) y exportación de datos a otro Pandora FMS |

El reparto de ICMP y SNMP entre los dos primeros no es una elección del
administrador módulo a módulo: con el servidor de red de alto rendimiento
activo (lo está de fábrica), el servidor de red renuncia a ICMP y SNMP y se
queda con el resto; si se desactiva `networkhpserver` explícitamente, el
servidor de red vuelve a hacerse cargo de ambos, consulta a consulta, con las
herramientas del sistema en vez del procesamiento en lote. Solo hay una
excepción: un módulo SNMP que
acumula más errores de los permitidos por reintento (`braa_retries`) cae al
servidor de red, aunque el de alto rendimiento siga activo. Si el servidor
de alto rendimiento no arranca por falta de `fping` o `braa`, su constructor
no desactiva `networkhpserver`: no se debe dar por hecha una conmutación
automática de ICMP y SNMP. El detalle del reparto está en
[Monitorización de redes](../parte-2/2.6-monitorizacion-de-redes.md).

Dos servidores de la lista anterior de la versión previa desaparecieron sin
dejar sustituto propio: el servidor de predicción y el servidor web. Sus
funciones no las asumió un servidor nuevo, sino el propio servidor de red,
que identifica el tipo de módulo antes de ejecutarlo y llama a la rutina de
predicción o a la de comprobación web según corresponda, sin pasar por una
instancia especializada distinta.

Además de estos tres, la wiki describe servidores asociados al maestro:
el gestor de políticas en un nodo, y migración y autoprovisión en un
Command Center. El gestor de políticas no es un servidor aparte: se ejecuta
desde la propia consola, no como un proceso de servidor independiente. La
migración y la autoprovisión en el Command Center sí dependen de un
interruptor de servidor propio (ver el token `provisioningserver` en la
[referencia completa](../parte-9/9.3-referencia-completa-de-configuracion-del-servidor.md#2-activacion-de-servidores-y-numero-de-hilos)).
El servidor de sincronización está desactivado de fábrica;
para arrancar exige `syncserver` activo y `sync_address` definido. Su
constructor no exige ser maestro.

## Servidores activados por defecto

La plantilla habilita cinco servidores y deja desactivados los once
interruptores indicados abajo. El arranque efectivo también depende de los
requisitos de cada componente. Son valores de **la plantilla**, no los valores
internos que usa el analizador cuando falta una opción ni un inventario
exhaustivo de todas las funciones del producto (ver la
[referencia completa](../parte-9/9.3-referencia-completa-de-configuracion-del-servidor.md#2-activacion-de-servidores-y-numero-de-hilos)
de cada token):

| Activados en la plantilla | Desactivados en la plantilla |
|---|---|
| Datos (`dataserver`) | Consola SNMP (`snmpconsole`) |
| Red (`networkserver`) | Eventos (`eventserver`) |
| Red de alto rendimiento (`networkhpserver`) | Log (`logserver`) |
| Heavy (`heavyserver`) | WUX (`wuxserver`) |
| Discovery (`discoveryserver`) | Syslog (`syslogserver`) |
| — | RMM (`rmmserver`) |
| — | Alertas (`alertserver`) |
| — | NetFlow (`netflowserver`) |
| — | MADE (`madeserver`) |
| — | SIEM (`siemserver`) |
| — | Eventos SIEM (`siemevents`) |

La lista de desactivados de la wiki incluye **Mainframe Server**, pero no
hay un interruptor equivalente entre los tokens de esta plantilla ni entre
las opciones que analiza `Config.pm` en el checkout examinado. No se le
atribuye por ello un valor predeterminado ni se infiere que no exista en
otros componentes. La wiki calificaba **Export Server** como desactivado
por defecto en el reparto anterior; `heavyserver 1` no permite deducir el
estado actual de la exportación.

## Tokens retirados y su sustituto

La instalación mediante los paquetes de servidor examinados sitúa la
configuración habitual en `/etc/pandora/pandora_server.conf`. El ejecutable
acepta la ruta del fichero como argumento, de modo que esa ubicación no es
obligatoria en todas las instalaciones. Para cambiar la activación o los
hilos, edite el fichero que utiliza **su** servicio.

Los interruptores heredados se siguen leyendo en `pandora_server.conf`, pero
no instancian los antiguos servidores en la ruta de arranque actual. Los
antiguos tokens de hilos también se analizan, pero **no ajustan los hilos**
de los servidores que realizan hoy esas tareas: hay que configurar el token
de hilos nuevo indicado en cada fila.

| Token heredado (activación / hilos) | Función actual | Sustituto de activación / hilos |
|---|---|---|
| `predictionserver` / `prediction_threads` | Predicción | `networkserver` / `network_threads` |
| `webserver` / `web_threads` | Web | `networkserver` / `network_threads` |
| `wmiserver` / `wmi_threads` | WMI | `networkserver` / `network_threads` |
| `icmpserver` / `icmp_threads` | ICMP | `networkhpserver` / `networkhpserver_threads`; con HP desactivado, `networkserver` / `network_threads` |
| `snmpserver` / `snmp_threads` | SNMP | `networkhpserver` / `networkhpserver_threads`; con HP desactivado o al superar `braa_retries`, `networkserver` / `network_threads` |
| `pluginserver` / `plugin_threads` | Plugins remotos | `heavyserver` / `heavyserver_threads` |
| `inventoryserver` / `inventory_threads` | Inventario remoto | `heavyserver` / `heavyserver_threads` |
| `exportserver` / `export_threads` | Exportación | `heavyserver` / `heavyserver_threads` |
| `ncmserver` / `ncmserver_threads` | NCM | `heavyserver` / `heavyserver_threads` |

`snmpserver` conserva además una lectura específica para comprobar la actividad
de `snmptrapd`; no activa el procesamiento de módulos SNMP.

`reconserver` y `recon_threads` son un caso distinto, y no una simple
equivalencia: nunca existió un servidor de reconocimiento de red separado
de Discovery. `reconserver` es hoy un segundo interruptor de encendido para
el propio Discovery Server, alternativo a `discoveryserver` (basta con que
uno de los dos esté activo), y `recon_threads` sigue teniendo efecto: el
número de hilos que usa Discovery es el mayor entre `discovery_threads` y
`recon_threads`, no uno de los dos en exclusiva. Conviene no tocarlo a
ciegas pensando que es un residuo sin efecto.

## Comprobaciones con intervalos cortos

El intervalo habitual de comprobación es de 300 segundos (5 minutos). En
el editor de módulos de la consola web se permiten intervalos de 15 segundos
para disponibilidad y latencia ICMP y para SNMP numérico y numérico incremental;
el editor rechaza valores inferiores a 15 segundos y los corrige con un aviso.
La misma validación fija 300 segundos para los tipos asíncronos 21, 22 y 23,
y 60 segundos para los demás tipos comprobados. Exceptúa los módulos de
Data Server antes de aplicar esos mínimos: no constituye una prohibición
universal para todos los módulos ni demuestra una validación equivalente
en el servidor.

El umbral de 300 segundos afecta también a otros dos comportamientos:

- **No se genera estado desconocido.** La comprobación periódica que marca
  un módulo como desconocido cuando lleva demasiado tiempo sin dato exige
  un intervalo de 300 segundos o más; con un intervalo menor, ese módulo
  no pasa a desconocido por esa comprobación de inactividad.
- **La precisión del dato cambia:** `process_data` formatea los datos
  numéricos con cinco decimales cuando `module_interval` es de 300 segundos
  o menos, y con uno cuando supera los 300 segundos. La wiki describe el
  orden inverso.

## Compactación y borrado de datos de intervalo corto

Con una conexión habilitada y operativa a la base de datos de
[histórico](../parte-6/6.5-base-de-datos-de-historico.md), el mantenimiento
llama a `pandora_historydb_smallint` con un plazo de **7 días** para módulos
con `module_interval` mayor que cero e inferior a 300 segundos. El hook
selecciona esos módulos y llama al traslado a histórico por módulo. Antes
se ejecutan la purga y el traslado general, por lo que esos siete días no
garantizan una semana universal de conservación ni el traslado si no hay
conexión a histórico. No es un plazo configurable desde
[Rendimiento](../parte-9/9.2-referencia-completa-de-configuracion-de-la-consola.md#3-rendimiento).

En el traslado de datos numéricos a histórico puede aplicarse una
[compactación](../parte-6/6.7-optimizacion-de-la-base-de-datos.md) por
intervalos temporales; los datos de texto no entran en esa rama. Está
desactivada de fábrica (`days_compact=0`); `step_compact` vale `1` muestra
por hora de fábrica, no las cinco indicadas en la wiki. La consola web
permite configurarlo entre 1 y 12; la rutina también limita los valores
fuera de ese rango. La compactación agrupa las muestras numéricas por
módulo e intervalo: calcula la media o, para tipos `_proc`, conserva cero
si aparece algún cero. No equivale a prometer un número exacto de muestras
retenidas por hora en todos los casos. La opción vive en
`Ajustes → Configuración del sistema → Rendimiento`, junto al resto de
purgas.
