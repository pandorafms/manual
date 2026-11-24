# Configuración de fprobe para Netflow

## Cuándo usar una sonda fprobe

Si el equipo de red ya exporta NetFlow, configure en él el destino del colector.
Si no puede exportarlo, `fprobe` permite capturar paquetes en una interfaz de
Linux y enviar registros de flujo al colector de Pandora FMS. La sonda no
convierte una interfaz sin tráfico en una ventana a toda la red: si se quiere
observar el tráfico de un switch, hay que hacer que llegue a esa interfaz,
por ejemplo, mediante un puerto espejo. Y el espejo debe llevar el tráfico
que se quiere medir, no el que quedaba libre para la prueba.

Este anexo describe la sonda NetFlow, no el servicio de consultas de Pandora
FMS. Para activar y configurar el colector, consulte [Monitorización de
tráfico con Netflow](../parte-2/2.8-monitorizacion-de-trafico-con-netflow.md),
apartado «Activar y configurar Netflow y sFlow en la consola».

## Requisitos y datos previos

Antes de instalar, anote la interfaz real de captura, la dirección del
colector y **el puerto UDP configurado en él**. No presuponga que el nombre
de la interfaz o el puerto del ejemplo coinciden con los de su instalación.

| Requisito | Detalle |
|---|---|
| Equipo para la sonda | Linux con una interfaz que reciba el tráfico deseado y permisos para instalar el paquete y capturar paquetes. El procedimiento corresponde a Ubuntu 22.04, donde se ha comprobado. |
| Paquete `fprobe` | Herramienta externa a Pandora FMS, disponible en los repositorios de Ubuntu 22.04 (versión 1.1-8 en la prueba). Se instala con `apt install fprobe`. |
| Interfaz de captura | Identifique su nombre con `ip -br link` en la máquina de la sonda y confirme que recibe el tráfico buscado. La sugerencia `eth0` de la instalación descrita en la wiki no identifica necesariamente su interfaz. |
| Colector NetFlow | `nfcapd` instalado y Netflow activado en el servidor de Pandora FMS. Verifique en la consola web el puerto de escucha y la ruta de datos configurados; el puerto inicial de NetFlow es `9995/udp`, pero puede cambiarse. |
| Conectividad | La sonda debe poder enviar UDP a la IP y puerto del colector. Permita ese tráfico en los cortafuegos y verifique que el colector escucha; el estado de la sonda no demuestra por sí solo que lleguen datagramas. |

## Instalar y configurar la sonda

En el equipo Ubuntu 22 elegido para la sonda, compruebe primero qué interfaz
recibe los paquetes. No use el nombre que aparezca en un ejemplo ajeno:

```bash
ip -br link
sudo apt install fprobe
```

La instalación descrita en la [wiki de desarrollo de Pandora
FMS](https://pandorafms.com/manual/!development/es/documentation/pandorafms/monitoring/18_netflow#ks2_4_2_1)
pregunta por la interfaz de captura y por el destino del colector. Indique
`<INTERFAZ_DE_CAPTURA>` (el nombre comprobado antes) y
`<IP_DEL_COLECTOR>:<PUERTO_NETFLOW>`; este último debe coincidir con el
puerto UDP configurado para `nfcapd` en la consola web. Por ejemplo, si el
colector escucha en el puerto inicial, el formato es
`<IP_DEL_COLECTOR>:9995`, no una dirección que deba copiarse literalmente.
Las respuestas se guardan en `/etc/default/fprobe`, que puede editar
si se equivoca:

```bash
INTERFACE="<INTERFAZ_DE_CAPTURA>"
FLOW_COLLECTOR="<IP_DEL_COLECTOR>:<PUERTO_NETFLOW>"
OTHER_ARGS="-fip"
```

Tras cambiar el fichero, reinicie el servicio con
`sudo systemctl restart fprobe`. Los parámetros `-d` (inactividad, 60 s
por defecto) y `-e` (flujo activo, 300 s) se pueden añadir a `OTHER_ARGS`
si necesita que los flujos se exporten antes.

## Arrancar y comprobar la recepción

En la sonda, compruebe por separado que el servicio se ejecuta:

```bash
sudo systemctl status fprobe
```

Si la unidad está detenida, revise primero su configuración y los mensajes
del servicio; tras corregirlos, arránquela con `sudo systemctl start fprobe`
y vuelva a comprobar su estado. Solo si desea que arranque con el sistema
y aún no está habilitada, ejecute `sudo systemctl enable fprobe`. El paquete de
Ubuntu 22.04 trae un script de init clásico (`/etc/init.d/fprobe`), que
`systemd` gestiona con `systemctl`; ese script no admite `service fprobe
status`, así que use `systemctl` o compruebe el proceso con `pgrep -a fprobe`.

Genere tráfico que **pase por la interfaz de captura**. En el servidor del
colector, compruebe que `nfcapd` está escuchando en el puerto configurado
y que aparecen ficheros `nfcapd.*` recientes en la ruta de datos de Netflow
configurada en Pandora FMS. Una vez haya ficheros de captura, consulte
su contenido en ese mismo servidor:

```bash
nfdump -R <RUTA_DE_DATOS_NETFLOW>
```

Sustituya el marcador por la ruta real del colector, no por la ruta de la
sonda. Si la ruta general de red es `/var/spool/pandora/data_in/` y el
subdirectorio es `netflow`, la ruta resultante es
`/var/spool/pandora/data_in/netflow`. La presencia de un servicio activo
en la sonda no equivale a ficheros nuevos; unos ficheros nuevos sin registros
del tráfico esperado tampoco prueban que el puerto espejo observe lo que
usted pretendía. `nfdump` debe mostrar registros del periodo con tráfico
conocido antes de dar por terminada la comprobación. Con los valores por
defecto, un flujo se exporta cuando lleva 60 segundos inactivo: espere uno o
dos minutos tras generar el tráfico antes de concluir que no llega nada.

## Si no llegan flujos

Revise el tramo donde se interrumpe la cadena, en este orden:

1. ¿Recibe la interfaz elegida el tráfico que quiere medir? Contraste el
   nombre seleccionado con `ip -br link` y compruebe el puerto espejo o el
   trayecto real de los paquetes. Un servicio activo no puede capturar
   tráfico que no pase por esa interfaz.
2. ¿Apunta la sonda a la IP y el puerto UDP de `nfcapd` configurados en la
   consola web? Si se cambió el puerto respecto a `9995`, cambie también el
   destino de la sonda y revise el cortafuegos entre ambos equipos.
3. ¿Está Netflow activado y escucha `nfcapd`? El servidor de Pandora FMS
   arranca el colector al iniciarse; tras activar Netflow o cambiar su
   puerto, reinicie el servidor de Pandora FMS para aplicar el cambio al
   colector. Compruebe después la escucha y los registros del servidor.
4. ¿Aparecen ficheros recientes en la ruta de datos configurada? Si existen
   pero `nfdump -R <RUTA_DE_DATOS_NETFLOW>` no muestra el tráfico esperado,
   vuelva a comprobar la interfaz y el periodo consultado. Use la ruta del
   colector; la sonda envía flujos, no guarda allí los ficheros de Pandora
   FMS.

La comprobación termina en los registros recibidos, no en un «activo» de
`systemctl`. Es una diferencia pequeña hasta que hay que explicar por qué
el gráfico sigue vacío.
