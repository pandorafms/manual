# Ampliar los asistentes SNMP y WMI con componentes propios

Los asistentes SNMP y WMI de la ficha del agente (ver
[Asistente SNMP](../parte-2/2.6-monitorizacion-de-redes.md#asistente-snmp) y
[Windows sin agente: WMI](../parte-2/2.6-monitorizacion-de-redes.md#windows-sin-agente-wmi))
no traen una lista fija de módulos: proponen lo que encuentran en un catálogo
de **componentes del asistente**. Este anexo explica cómo ampliar ese
catálogo con fabricantes y componentes propios, para los dos asistentes.

## Qué son los componentes del asistente y cuándo crearlos

Un componente del asistente es una plantilla que describe qué consultar en el
equipo y cómo convertirlo en un módulo. Cuando el asistente explora un
equipo, no improvisa: recorre este catálogo y ofrece los componentes que
encajan con lo que ha encontrado (el fabricante, en SNMP) agrupados en
bloques según lo que miden.

Merece la pena crear uno propio en tres casos: un fabricante que el
asistente no reconoce todavía (el error «PEN no está registrado» de
[Asistente SNMP](../parte-2/2.6-monitorizacion-de-redes.md#asistente-snmp)),
un OID propietario que se quiere tener siempre a mano sin buscarlo cada vez,
o un dato que no sale de un solo OID sino de combinar varios. La diferencia
con un [componente de red
normal](../parte-2/2.6-monitorizacion-de-redes.md#componentes-de-red-no-empezar-de-cero)
es el origen: aquel se aplica a mano, eligiéndolo en el editor de un módulo;
un componente del asistente lo propone el asistente después de explorar el
equipo, y uno solo puede acabar generando muchos módulos a la vez, uno por
cada fila que encuentre.

!!! example "Cuándo crear uno y cuándo no"
    Un switch que el asistente SNMP ya reconoce, pero al que le falta un
    sensor de temperatura propietario del fabricante: no hace falta ningún
    componente nuevo, con [Módulos
    SNMP](../parte-2/2.6-monitorizacion-de-redes.md#modulos-snmp) y el OID a
    mano es suficiente para ese caso puntual. Si en cambio la misma sonda de
    temperatura va a repetirse en decenas de equipos del mismo fabricante,
    un componente del asistente evita crearla a mano en cada uno.

## Registrar un fabricante (PEN)

El asistente SNMP identifica el fabricante del equipo por su **PEN**
(*Private Enterprise Number*): un número que cada fabricante registra ante
IANA y que ocupa una posición fija dentro del `sysObjectID` que declara el
equipo. Si Pandora FMS no tiene ese PEN dado de alta, el asistente se detiene
con el aviso «PEN no está registrado» y no propone ningún componente, aunque
el equipo responda perfectamente por SNMP.

Registrar el PEN es el primer paso, en **Gestión → Configuración →
Plantillas → Números privados de empresa** (*Private Enterprise Numbers*),
con tres campos: **PEN** (el número que declara el equipo), **Fabricante**
(el nombre corto que después identifica sus componentes) y **Descripción**.
Registrar el PEN solo pone nombre al fabricante; no crea ni un solo módulo
por sí solo, eso lo hacen los componentes del siguiente apartado. Requiere
permiso de gestión de la consola.

La instalación trae 27 fabricantes ya registrados, pero solo algunos traen
además componentes del asistente: Cisco, HP, Juniper, F5, Fortinet y dos
números genéricos para los equipos que exponen su información con
Net-SNMP/UCD, a los que se suman los componentes genéricos (**All**) que se
ofrecen a cualquier equipo. El resto de fabricantes registrados de fábrica
(D-Link, MikroTik, Alcatel-Lucent, Ubiquiti, Allied Telesis, IBM, Dell,
Apple, Oracle, Hitachi, Synology, Fujitsu, entre otros) ya no hacen que el
asistente se detenga, pero solo reciben esos componentes genéricos hasta que
se les creen componentes propios. Un fabricante que no esté en la lista hay
que darlo de alta a mano, como en el ejemplo siguiente.

!!! example "Dar de alta un SAI que el asistente no reconoce"
    Un SAI declara un PEN que no está en el catálogo de fábrica. Se registra
    con **PEN** su número IANA, **Fabricante** `mi-sai` y una descripción
    breve. A partir de ahí el asistente ya no se detiene por PEN no
    registrado, aunque de momento no proponga ningún módulo: eso llega con el
    primer componente del apartado siguiente.

## Crear un componente del asistente

Los componentes del asistente se crean en **Gestión → Configuración →
Plantillas → Componentes remotos**, eligiendo el tipo de componente
asistente. Comparten con un componente de red normal los campos habituales
—habilitado, **Añadir por defecto** (si aparece ya marcado al abrir el
asistente), nombre, tipo de dato, grupo del componente (el bloque en el que
aparece agrupado), unidad y umbrales, descripción— más el **Protocolo de
módulo** (SNMP o WMI) y el **ID del fabricante**: un fabricante concreto ya
registrado, o **All**, que ofrece el componente para cualquier equipo sin
importar su PEN.

Dos campos deciden el resto del formulario y qué clase de módulo va a
proponer el componente:

- **Scan type** (tipo de escaneo): **Fixed** (fijo) crea un único módulo;
  **Dynamic** (dinámico) recorre una tabla del equipo y crea un módulo por
  cada fila que encuentre, sin saber de antemano cuántas van a ser.
- **Execution type** (tipo de ejecución): **Network** (red) hace que el
  propio servidor lea el valor directamente, como un módulo SNMP o WMI
  normal; **Plugin** delega el cálculo en un plugin de servidor o, si el
  asistente se lanza desde un servidor satélite, en un comando `module_exec`.

| Escaneo | Ejecución | Qué crea |
|---|---|---|
| Fixed | Network | Un único módulo que lee un OID (o una consulta WMI) directamente |
| Fixed | Plugin | Un único módulo cuyo valor calcula un plugin, a partir de uno o varios OID o campos |
| Dynamic | Network | Un módulo por cada fila de una tabla, leído directamente |
| Dynamic | Plugin | Un módulo por cada fila de una tabla, calculado por un plugin |

Duplicar un componente existente con la acción **Duplicate** de su listado es
el punto de partida más rápido para uno nuevo parecido; no hay importación
ni exportación de componentes entre instalaciones.

## Componentes SNMP con OID estática

Combinación escaneo fijo + ejecución de red, la más simple: **OID del
valor** es el OID final que se va a leer, igual que en un módulo SNMP
creado a mano. **Nombre del OID** es opcional y, si se rellena, su valor
sustituye a la macro `_nameOID_` en el nombre del módulo.

!!! example "Carga de batería de un SAI"
    Con el fabricante `mi-sai` ya registrado, un componente fijo llamado
    «Carga de batería» con el OID propietario de carga en **OID del valor**,
    umbrales de advertencia y crítico ya rellenos y grupo del componente
    «Energía». En cuanto se lanza el asistente SNMP sobre un agente de ese
    fabricante, el componente aparece en su bloque correspondiente, listo
    para marcar.

## Componentes SNMP con OID dinámica

Combinación escaneo dinámico + ejecución de red: **OID del valor** y
**Nombre del OID** dejan de ser OID finales para pasar a ser dos ramas
(*subárboles*) del equipo. El asistente recorre las dos por completo,
cruza los resultados por índice —el mismo índice en ambas ramas corresponde
a la misma fila— y propone un módulo por cada índice encontrado, con el
nombre de esa fila sustituyendo a `_nameOID_` y el propio índice añadido al
final del **OID del valor**.

!!! example "Un módulo por sensor de temperatura"
    Una tabla propietaria expone, para cada sensor de temperatura del
    equipo, su nombre en una rama y su valor en otra. Un componente dinámico
    con **Nombre del OID** apuntando a la rama de nombres y **OID del
    valor** a la rama de valores crea, tras la exploración, un módulo por
    cada sensor encontrado, cada uno con el nombre real de su sensor.

## Componentes SNMP calculados con un plugin

Para un dato que no sale de leer un solo OID, la ejecución pasa a **Plugin**.
El formulario añade entonces cuatro cosas:

- **OID de macros**: una entrada por cada OID que participa en el cálculo,
  que se referencia en el resto del formulario como `_oid_1_`, `_oid_2_`…
- **Operación de valores**: la fórmula que combina esos valores, escrita
  con las mismas macros `_oid_N_`. Solo sirve para enseñar el valor en la
  vista previa del asistente; el módulo creado no la usa.
- **Plugin de servidor**: el plugin que hace el cálculo de verdad cada vez
  que se ejecuta el módulo. Los dos de fábrica comparten los mismos campos
  de conexión (`_address_`, `_port_`, `_version_`, `_community_` y las
  credenciales SNMPv3), pero difieren en lo que preguntan a continuación:
    - **Wizard SNMP module**, para valores numéricos: además de la conexión,
      pide la **lista de OID** (`_oid_1_,_oid_2_`…) y la **Operation**, la
      fórmula que combina esos valores escrita como `_o1_`, `_o2_`… según
      la posición de cada OID en la lista.
    - **Wizard SNMP process**, para saber si un proceso está en ejecución:
      en vez de una lista de OID, pide un único campo **Process** con el
      nombre del proceso (sensible a mayúsculas); el plugin comprueba por
      sí mismo, contra el árbol SNMP de procesos del sistema, si aparece
      en ejecución.
- **Ejecución de satélite**: el comando equivalente para cuando el asistente
  se lanza desde un [servidor
  satélite](../parte-6/6.2-servidores-satelite.md), que usa los plugins
  `wizard_snmp_module` y `wizard_snmp_process` instalados en el satélite.

Como la vista previa y la ejecución real usan campos distintos, la fórmula
de **Operación de valores** y la de **Operation** deben decir lo mismo; si
no, el asistente propone un valor y el módulo acaba midiendo otro.

En escaneo dinámico, cada `_oid_N_` deja de ser un OID final para ser una
rama que también se recorre por índice, igual que en el apartado anterior;
el asistente calcula un valor —y por tanto un módulo— por cada fila
encontrada.

!!! example "Porcentaje de uso de una partición"
    Dos OID de una tabla de almacenamiento, espacio usado y espacio total,
    se registran en **OID de macros** como `_oid_1_` y `_oid_2_`.
    **Operación de valores** se rellena con `(_oid_1_ * 100) / _oid_2_`,
    para que la vista previa ya enseñe el porcentaje. En **Plugin de
    servidor** se elige «Wizard SNMP module», con `_oid_1_,_oid_2_` en la
    lista de OID y `(_o1_ * 100) / _o2_` en **Operation**; los campos de
    conexión se dejan con sus macros. Cada módulo creado calcula el
    porcentaje de uso en cada ejecución, sin posprocesado.

## Componentes WMI

El asistente WMI usa el mismo mecanismo de componentes, con su propio juego
de campos: **Clase WMI** (la clase que se va a consultar), **Campo de clave
de consulta** (qué columna de la respuesta identifica cada fila) y **Campos
extra de consulta** (el resto de columnas que se necesitan). Cada columna
queda disponible como una macro `_NOMBRECAMPO_` con el valor de esa fila.
Igual que en SNMP, dinámico significa un módulo por cada fila que devuelva
la consulta de escaneo.

Los **Filtros de consulta** acotan, por un lado, qué filas trae la
exploración y, por otro, cómo se calcula el valor del módulo en ejecución
de red:

- **Field value**: el número de la columna de la respuesta cuyo valor pasa
  a ser el valor del módulo (`0` es el propio campo clave; `1` en adelante,
  cada campo extra de consulta por su orden).
- **Key string**: opcional. Si se rellena, el valor del módulo deja de ser
  el dato en crudo y pasa a ser `1` o `0` según si coincide con esta
  cadena. Este filtro no se aplica cuando el asistente se lanza desde un
  [servidor satélite](../parte-6/6.2-servidores-satelite.md): el módulo
  generado en el satélite siempre devuelve el dato en crudo de **Field
  value**, aunque se haya rellenado **Key string**.

En ejecución de plugin, en vez de estos dos filtros aparecen:

- **Value operation**: la fórmula que combina los campos de la fila con las
  macros `_f1_`, `_f2_`… (una por cada campo extra de consulta, por orden).
- **Server plugin**: el plugin que hace el cálculo; el de fábrica es
  «Wizard WMI module», con la macro `_class_wmi_` para la clase consultada
  y la misma familia `_f1_`, `_f2_`… en su campo **Operation**.
- **Satellite execution**: el comando equivalente para cuando el asistente
  se lanza desde un servidor satélite, con el plugin `wizard_wmi_module`
  instalado allí.

!!! example "Espacio libre de cada disco local"
    Componente WMI dinámico sobre la clase `Win32_LogicalDisk`, con filtro
    de consulta `DriveType = 3` (solo discos locales) y `_DeviceID_` en el
    nombre del módulo: el asistente crea, en cada equipo Windows, un módulo
    de espacio libre por cada disco local que encuentre, con la letra de
    unidad en el propio nombre.

## Referencia de campos

| Campo | Protocolo | Para qué sirve |
|---|---|---|
| Añadir por defecto | Común | El componente aparece ya marcado al abrir el asistente |
| Grupo del componente | Común | Bloque en el que se agrupa el componente dentro del asistente |
| Protocolo de módulo | Común | SNMP o WMI |
| ID del fabricante | SNMP | Fabricante (PEN registrado) al que se ofrece el componente, o `All` para cualquiera |
| Scan type | Común | `Fixed` (un módulo) o `Dynamic` (un módulo por fila) |
| Execution type | Común | `Network` (lectura directa) o `Plugin` (cálculo delegado) |
| Nombre del OID | SNMP | OID (o rama, en dinámico) cuyo valor sustituye a `_nameOID_` en el nombre |
| OID del valor | SNMP, red | OID final (o rama, en dinámico) que se lee |
| OID de macros | SNMP, plugin | Lista de OID (o ramas) que participan en la operación, como `_oid_N_` |
| Operación de valores | SNMP, plugin | Fórmula con `_oid_N_` que calcula el valor mostrado en la vista previa; no se usa en el módulo creado |
| Plugin de servidor | SNMP, plugin | Plugin que calcula el valor en cada ejecución del módulo; sus campos admiten las macros de la tabla siguiente |
| Ejecución de satélite | SNMP, plugin | Comando equivalente para cuando el asistente se lanza desde un servidor satélite |
| Clase WMI | WMI | Clase que se consulta |
| Campo de clave de consulta | WMI | Columna de la respuesta que identifica cada fila |
| Campos extra de consulta | WMI | Resto de columnas necesarias de la respuesta |
| Filtros de consulta (Scan / Execution) | WMI | Condición que acota la exploración y, por separado, la ejecución del módulo |
| Field value | WMI, red | Número de columna cuyo valor pasa a ser el valor del módulo (`0` = campo clave) |
| Key string | WMI, red | Cadena opcional que convierte el valor en `1`/`0` según coincidencia; se ignora al ejecutarse desde un servidor satélite |
| Value operation | WMI, plugin | Fórmula con `_f1_`, `_f2_`… que calcula el valor mostrado en la vista previa |
| Ejecución de satélite | WMI, plugin | Comando equivalente para cuando el asistente se lanza desde un servidor satélite, con el plugin `wizard_wmi_module` |

## Referencia de macros

| Macro | Se sustituye por | Dónde vale |
|---|---|---|
| `_nameOID_` | Nombre obtenido de `Nombre del OID` | Nombre del módulo, componentes SNMP |
| `_oid_N_` | En la vista previa, el valor leído; en los campos del plugin y en la ejecución de satélite, el OID de la posición N de `OID de macros` (con su índice, en dinámico) | `Operación de valores`, campos del `Plugin de servidor`, `Ejecución de satélite` |
| `_o1_`, `_o2_`… | Valor del OID en esa posición de la lista de OID del plugin | Campo **Operation** del plugin «Wizard SNMP module» |
| `_FIELDNAME_` | Valor de la columna `FIELDNAME` de la fila WMI actual | Componentes WMI |
| `_class_wmi_` | Clase WMI del componente | Campos del `Server plugin` y `Ejecución de satélite`, componentes WMI de plugin |
| `_field_wmi_N_` | Valor del campo extra de consulta número N | Componentes WMI de plugin |
| `_f1_`, `_f2_`… | Valor del campo extra de consulta en esa posición | `Value operation` y campo **Operation** del plugin «Wizard WMI module» |
| `_address_`, `_port_` | Dirección y puerto con los que se lanzó el asistente | Campos del `Plugin de servidor` y `Ejecución de satélite` (SNMP y WMI) |
| `_version_`, `_community_` | Versión SNMP y comunidad (v1/v2c) | Campos del `Plugin de servidor` y `Ejecución de satélite` (SNMP) |
| `_sec_level_`, `_auth_user_`, `_auth_method_`, `_auth_pass_`, `_priv_method_`, `_priv_pass_` | Credenciales SNMPv3 con las que se lanzó el asistente | Campos del `Plugin de servidor` y `Ejecución de satélite` (SNMP) |
| `_namespace_wmi_`, `_user_wmi_`, `_pass_wmi_` | Espacio de nombres y credenciales WMI con las que se lanzó el asistente | Campos del `Plugin de servidor` y `Ejecución de satélite` (WMI) |

Los dos asistentes también se pueden lanzar sobre una [política de
monitorización](../parte-2/2.10-politicas-de-monitorizacion.md) en vez de
sobre un agente concreto, con una diferencia importante en cómo se rellenan
estas macros: `_address_` se deja tal cual, como macro literal, para que cada
agente que reciba la política la sustituya por su propia dirección, igual que
en cualquier otro [módulo de
red](../parte-2/2.6-monitorizacion-de-redes.md#macros-en-los-campos-del-modulo);
el resto de macros de conexión —versión, comunidad, credenciales SNMPv3,
espacio de nombres y credenciales WMI— se sustituyen igualmente por lo que se
escribió al lanzar el asistente, y quedan fijas en el módulo de política
resultante. Con una política que se aplica a agentes con comunidades o
credenciales distintas, conviene revisar esos valores en cada módulo después
de crearlo.

Crear el plugin que ejecuta un cálculo propio, en vez de reutilizar los de
fábrica, se explica en [9.9 · Creación de plugins
remotos](../parte-9/9.9-creacion-de-plugins-remotos.md).
