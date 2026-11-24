# Glosario de términos

Este glosario reúne el vocabulario que usa la documentación de Pandora FMS: los
conceptos de la plataforma, las piezas de su arquitectura y los términos de
versiones y licencias que aparecen en el resto del sitio. No se lee de principio
a fin, se consulta. Cada entrada define el término en dos o tres frases y, cuando
el tema tiene capítulo propio, apunta a él.

Los nombres de los estados de un módulo van en español, con el inglés entre
paréntesis, porque la consola usa los dos.

## A

### Acceso básico y acceso avanzado

Dos niveles de permiso que se pueden dar a un usuario, a un componente de módulo
y a una alerta. Con **acceso básico** solo se usan los componentes y las alertas
de ese nivel. Con **acceso avanzado** se usan los de cualquier nivel. Los
componentes avanzados se configuran más: se les cambia el nombre, definen las
acciones de sus alertas y muestran campos que los básicos no tienen, como las
unidades o las macros de un complemento (*plugin*).

### Acción

Ejecución que se lleva a cabo cuando se dispara una **alerta**. Cada acción tiene
sus propios campos de configuración y una misma alerta puede disparar varias a la
vez. No hay que confundirla con el **comando de alerta**, que es la ejecución que
corre el servidor.

### ACL

Del inglés *Access Control List*. Determinan los permisos de los usuarios. En
Pandora FMS se definen asignando a un usuario un **perfil** sobre un **grupo**: el
perfil dice qué operaciones puede hacer y el grupo sobre qué agentes.

### Actualización manual

Segunda forma de poner al día una instalación, sin pasar por **Warp Update**: los
mismos paquetes, aplicados a mano en la terminal con usuario `root` y en un orden
que no es negociable (**consola, esquema de la base de datos y servidor**). Da
control total del proceso y es el camino obligado cuando la consola no puede
descargar los paquetes. Ver
[Actualizaciones](../parte-1/1.4-actualizaciones.md).

### Acuerdo de nivel de servicio (SLA)

Acuerdo negociado entre un cliente y un proveedor de servicios. En Pandora FMS un
incumplimiento de SLA se reporta cuando un módulo sale de los valores
considerados normales. El cálculo mira los datos guardados en la base de datos,
no los cambios de estado del módulo. Los periodos **desconocidos** y las
**paradas planificadas** se consideran válidos, igual que los periodos en estado
de advertencia.

### Agente

Entidad organizativa de Pandora FMS. Suele representar una máquina, un sistema o
un *host*, contiene los **módulos** que lo vigilan y pertenece a un único grupo
primario. Tiene un nombre único y, de forma opcional, un alias, que sí puede
repetirse. Puede relacionarse con otros agentes («padre-hijo»). No es lo mismo
que el **EndPoint**: el agente es el contenedor lógico de la consola, el EndPoint
es el programa que recoge los datos en el equipo.

### Alerta

Aviso automático sobre el estado o el valor de un módulo. Tiene dos estados
posibles, disparada o no disparada, y ejecuta **acciones**, como enviar un correo
o lanzar un **comando de alerta**. Las condiciones de disparo las define la
**plantilla de alerta**.

### Asistente de creación de módulos

Asistente (*wizard*) que crea módulos de distintos tipos en varias instancias a
la vez. Usa los componentes de módulo y las plantillas de alerta, y no distingue
entre instancias: mezcla agentes y módulos como si vinieran de la misma fuente.
Es propio del **Command Center**.

### AuthKey

Clave de activación de la licencia. La envía Pandora FMS, o su distribuidor, por
correo electrónico o en un PDF. Es un número de entre 12 y 15 dígitos que **solo
sirve una vez** y con él se genera la licencia de la instalación. Ver
[Licenciamiento](../parte-1/1.5-licenciamiento.md).

## B

### Base de datos

Conjunto de datos del mismo contexto, almacenados de forma sistemática para su
uso posterior. Pandora FMS trabaja con MySQL, MariaDB o Percona y accede a ellos
por SQL. En la práctica se manejan dos: la de tiempo real y la de histórico, a la
que se mueven los datos cuando ya no hace falta consultarlos al segundo.

## C

### Chequeo WMI

Consulta remota a un equipo MS Windows a través de WMI y con credenciales. Es la
vía para sacar datos de un Windows sin instalarle un **EndPoint**.

### Chequeos SNMP

Chequeos que utilizan el protocolo SNMP. Con ellos se consultan los OID que
expone el fabricante (*polling*) y se escuchan los *traps* que el dispositivo
envía por su cuenta.

### Chequeos TCP

Chequeos remotos que consultan dispositivos y ordenadores por sus puertos
abiertos, con desafío y respuesta para comprobar que el puerto atiende.

### Comando

Instrucción que se ejecuta en un sistema operativo, por petición de un usuario o
de una aplicación. En la consola del sistema es la forma habitual de administrar
el servidor.

### Comando de alerta

Ejecución a nivel de sistema que lanza el servidor cuando se dispara una
**alerta**. Admite comandos externos y *scripts* propios.

### Comentar o descomentar un parámetro

Colocar un parámetro como comentario, con el carácter especial al principio de su
línea, para que el programa lo ignore. Se **descomenta** cuando se le quita ese
carácter y el parámetro vuelve a leerse.

### Command Center

Capa de gestión por encima de varias instalaciones de Pandora FMS, a las que
llama **nodos**. Desde una sola interfaz se ven juntas, se sincroniza su
configuración y se opera sobre todas. Cada nodo conserva su servidor y su base de
datos: el Command Center no los sustituye, los coordina. Es el nombre vigente de la
antigua **Metaconsola**. Ver
[Introducción y arquitectura](../parte-1/1.2-introduccion-y-arquitectura.md).

### Componente

Plantilla para crear un **módulo**. Puede ser local (lo ejecuta el EndPoint en la
máquina) o de red, y entre los de red hay complemento (*plugin*), WMI, TCP, SNMP
e ICMP.

### Consola web

Interfaz de Pandora FMS en el navegador. Es la que se usa para configurar,
operar y consultar la plataforma. En los menús, la primera mención de cada
sección se escribe «Consola web» para no confundirla con la consola del sistema.

## D

### DAEMON

Del inglés *Disk And Execution Monitor*. Programa sin interfaz gráfica que se
ejecuta a nivel de sistema operativo con poca o ninguna interacción por parte del
usuario.

### Dependencia

Conjunto de ficheros, normalmente compilados a lenguaje de máquina, con funciones
comunes que pueden usar una o varias aplicaciones del sistema operativo.

### Downgrade

Vuelta a la versión anterior de un servidor. Se usa cuando una actualización
(*upgrade*) trae un inconveniente que no se puede esperar a corregir.

## E

### EndPoint

Programa instalado en el equipo para recoger información local. Permanece en
ejecución, toma datos cada **intervalo** y los envía al servidor en ficheros XML,
por Tentacle o por la API 2.0. Es la pieza que aporta los datos que solo se ven
desde dentro de la máquina. No es lo mismo que el **agente**: el agente es el
contenedor de la consola.

### Entornos *nix

Abreviatura para referirse a entornos Unix y Linux.

### Estado del módulo

Los cuatro estados en que puede estar un módulo. **NORMAL** (*normal*) es el
valor dentro de sus umbrales. **ADVERTENCIA** (*warning*) y **CRÍTICO**
(*critical*) indican condiciones de error de distinta gravedad y tienen umbrales
independientes. **DESCONOCIDO** (*unknown*) es el estado de un módulo que no ha
recibido datos desde hace más del doble de su intervalo.

### Evento

Cualquier incidente que ocurre en los sistemas monitorizados. Un evento muestra
desde un cambio de estado de un módulo hasta una alerta disparada o recuperada, o
un reinicio del sistema.

## F

### Falso positivo y falso negativo

Un **falso positivo** es un chequeo que devuelve un error que no se ha producido.
Un **falso negativo** es un chequeo que no devuelve error cuando sí ha ocurrido.
La **protección Flip Flop** existe para amortiguar los dos.

### Feature Release (FR)

Versión de funcionalidad, la que trae las novedades del producto. Una FR recibe
parches **solo en situaciones específicas**, las que reconoce la política oficial
de soporte. Se contrapone a la **versión LTS**. Ver
[Política de versiones y soporte](../parte-1/1.3-versiones-y-estabilidad.md).

### Fichero de datos (XML de datos)

Archivo XML que generan los **EndPoint**. Contiene la información de sus módulos
y, además, los datos del propio EndPoint: versión, sistema operativo y demás.

## H

### Hibernar o hibernación

Guardar en un dispositivo fijo de almacenamiento todo lo que hay en memoria RAM,
datos y programas en ejecución, por parte de un sistema operativo.

## I

### Instancia

Instalación de Pandora FMS preparada para que el **Command Center** acceda a ella
y, de forma opcional, para replicar sus eventos en el Command Center. En el mundo
del Command Center se le llama **nodo**.

### Intervalo inverso

Opción que define rangos no contiguos en los **umbrales**. En los módulos de tipo
cadena de texto, el umbral se define como una subcadena.

## K

### Kernel

Software que comunica el hardware con el resto del software del equipo y
constituye la esencia de un sistema operativo.

## L

### Licencia perpetua

Modelo de licencia de la versión on-premise. Se adquiere una vez y cada año se
renueva el soporte y el mantenimiento, para seguir recibiendo parches y versiones
nuevas. El otro modelo on-premise es la **suscripción**. Ver
[Licenciamiento](../parte-1/1.5-licenciamiento.md).

## M

### Merging (código)

Fusionado de código fuente, por ejemplo para incorporar una característica nueva.
También se aplica a otros procesos similares, como fusionar dos bases de datos en
un tercer servidor.

### Modo de depuración

Información detallada de los procesos y los parámetros de una aplicación, paso a
paso, para localizar excepciones y errores de código.

### Módulo

Entidad atómica de información de Pandora FMS. Guarda valores numéricos o
alfanuméricos y **una sola métrica** cada uno (CPU, RAM, tráfico...). Vive dentro
de un **agente** y siempre asociado a uno solo; un agente puede tener muchos
módulos. Su lectura se interpreta por **umbrales**, que dan el **estado del
módulo**.

### Monitorización asíncrona

La de un módulo que devuelve datos en función de cambios o acontecimientos, que
pueden producirse o no.

### Monitorización síncrona

La de un módulo que devuelve datos a intervalos regulares, por ejemplo una
medición de temperatura cada cinco minutos.

### Mosaico

Aparición simultánea de distintos documentos o partes de ellos, normalmente
minimizados y en un mismo plano. Se usa en la consola GIS.

## N

### Nodo

Cada una de las instalaciones de Pandora FMS que gestiona un **Command Center**.
Conserva su propio servidor y su propia base de datos. La licencia del Command
Center se cuenta por nodos activos, y las réplicas por redundancia no suman.

## O

### OpenSSH

Conjunto de aplicaciones que permiten comunicaciones cifradas a través de una red
con el protocolo SSH.

## P

### Pandora Web Robot Daemon

**PWRD**. Proporciona las herramientas para automatizar sesiones de navegación
web y monitorizarlas después con WUX.

### Paquete

Programa o conjunto de programas empaquetados en un formato listo para instalar
en un sistema operativo y versión determinados.

### Paquete .disco

Paquete instalable de un asistente de Discovery (aplicaciones, nubes u otros
orígenes). Se instala desde el Marketplace o subiendo el fichero `.disco`, y
cada tarea creada con él lleva a cabo la monitorización que declara. Ver
[Ampliar Discovery](../parte-2/2.3-monitorizacion-y-descubrimiento-automatico-con-discovery.md#ampliar-discovery-paquetes-disco-y-marketplace).

### Parche

Corrección sobre una versión ya publicada. Un parche trae seguridad y arreglos
críticos, y no baja a la versión que corrige mejoras que solo existen en
versiones más nuevas. En la versión LTS se numeran sobre la base: la 800 recibe
800.1, 800.2 y así. Ver
[Política de versiones y soporte](../parte-1/1.3-versiones-y-estabilidad.md).

### Perfil

Conjunto de permisos sobre las operaciones posibles en Pandora FMS: ver un
agente, modificarlo, asignarle alertas y el resto. Se asigna a un usuario y
siempre sobre un grupo determinado.

### Ping

Utilidad de diagnóstico de redes que comprueba la latencia y la conectividad
entre el equipo local y otro remoto, a nivel de protocolo IP. Usa paquetes ICMP
de solicitud (*Echo Request*) y de respuesta (*Echo Reply*).

### Plantilla de alerta

Define las condiciones de disparo de una **alerta**: el valor o el estado del
módulo que la dispara, cuántas veces puede dispararse en un intervalo y en qué
franja horaria.

### Polling SNMP

Consulta regular por SNMP desde Pandora FMS a los dispositivos monitorizados.

### Protección Flip Flop

Mecanismo que evita que un módulo cambie de estado con la primera oscilación de
su valor. El fenómeno *flip flop* es el valor que alterna entre mal y bien de
forma frecuente. La protección se configura con el **umbral FF** (*FF
threshold*), el número de veces seguidas que debe darse la condición para que el
cambio se produzca, más el intervalo FF. Amortigua falsos positivos y negativos.

## R

### Rotación de registros

Del inglés *log rotation*. Proceso automatizado de administración de sistemas en
el que los archivos de registro se comprimen, se archivan, se renombran o se
eliminan. Los datos nuevos se dirigen a un archivo nuevo, normalmente en la misma
ubicación.

## S

### Servidor

El `Pandora Server`. Procesa la información que recogen las demás piezas, ejecuta
las alertas, aplica las políticas y guarda los datos en la base de datos. Desde
la versión 784 agrupa en menos procesos varios servicios que antes eran
instancias separadas, y cada uno se puede habilitar o deshabilitar según
necesidad.

### Servidor remoto

Servidor al que se llega por la red, por oposición al servidor local.

### Servidor satélite

Instalación de Pandora FMS que vigila una red remota sin depender de la conexión
con el servidor principal. Consulta al servidor cada pocos segundos (30 por
defecto) si hay cambios, inicia él la conexión (no hay que exponer puertos) y
admite túnel SSH inverso desde la versión 785. Ver
[Introducción y arquitectura](../parte-1/1.2-introduccion-y-arquitectura.md).

### Shell o línea de comandos

Interfaz que permite introducir comandos en una máquina con el teclado.

### SIEM

Del inglés *Security Information and Event Management*. Sistema que recoge,
filtra, normaliza, correlaciona y presenta eventos de seguridad. Lo que aporta
Pandora SIEM es que la recolección ya está hecha. Los logs que lo alimentan son
los mismos que ya recoge la plataforma. El motor de eventos de seguridad se
apoya en ese trabajo previo, en lugar de montar un segundo sistema aparte.

### Software nativo

El software, o los formatos de datos, diseñados para ejecutarse o procesarse en
un sistema operativo concreto.

### Superadmin

Superusuario de Pandora FMS, como `root` lo es en Linux. Al instalar un servidor
completo se crea un usuario `admin`, que es el primer superadmin, y no es el
único: hay usuarios con el **bit de acceso PM**, prácticamente iguales salvo que
no pueden crear comandos de alerta ni nombrar a otros superadmins. Hay funciones
a las que solo llega un superadmin.

### Suscripción

Modelo de licencia de la versión on-premise en el que se paga cada año, con el
soporte y el mantenimiento incluidos mientras dure el contrato. El software y las
funcionalidades son los mismos que con la **licencia perpetua**, así que la
elección es de tesorería, no de producto. Ver
[Licenciamiento](../parte-1/1.5-licenciamiento.md).

### SVN / Subversion / Repositorio de código

Sistema de control de versiones que guarda un repositorio con las distintas
versiones de los archivos de un proyecto a lo largo de su vida.

### Sync Server

Pieza que da la vuelta al problema cuando la red remota no puede iniciar
comunicación hacia el servidor. El servidor principal toma la iniciativa y va a
buscar los datos a un servidor Tentacle desplegado en la red aislada, que hace de
almacén temporal: allí se acumula la información hasta que el principal la
descarga, y lo descargado desaparece del almacén. Ver
[Introducción y arquitectura](../parte-1/1.2-introduccion-y-arquitectura.md).

## T

### Tarball

Archivo con un programa o varios empaquetados en formato TAR. A diferencia de un
**paquete**, no lleva información de cómo instalarlo y no es específico de un
sistema operativo.

### Tentacle

Protocolo de transferencia de datos que usan los **EndPoint** y el **servidor
satélite** para enviar datos al servidor de Pandora FMS. Es multiplataforma y usa
por defecto el puerto 41121, asignado por IANA.

## U

### Umbral

Valor mínimo o máximo de un módulo a partir del cual se produce un cambio de
**estado**.

### Umbral de alerta (Alert threshold)

Intervalo de tiempo en el que aplican las restricciones definidas en la
**plantilla de alerta**.

### Usuario root

En entornos *nix, el usuario dedicado a la administración del sistema operativo,
con privilegios especiales para instalar, configurar y mantener el software.
Otros usuarios pueden heredar esos privilegios si pertenecen al grupo `root`.

## V

### Versión LTS

Versión de soporte prolongado. Se soporta **dos años**, ampliables otros dos con
un contrato de soporte de larga duración. Recibe parches de seguridad y de fallos
críticos, no funcionalidades de versiones superiores, y convive con las
**Feature Release**, que traen las novedades. Ver
[Política de versiones y soporte](../parte-1/1.3-versiones-y-estabilidad.md).

## W

### Warp Update

Sistema de actualización desde la propia consola. Sus asistentes descargan,
aplican y verifican la actualización, y también hay un modo sin conexión para
entornos aislados. Es la vía recomendada frente a la **actualización manual**.
Ver [Actualizaciones](../parte-1/1.4-actualizaciones.md).

### Watchdog

Funcionalidad que comprueba si un sistema se está ejecutando y, si está caído, lo
reinicia.

### Widget

Elemento de interfaz que ofrece un punto de interacción para un tipo de datos.
Muestra una disposición de la información que el usuario puede modificar, como
una ventana o un cuadro de texto. Combinados en una aplicación, reúnen los datos
procesados y las interacciones disponibles sobre ellos.
