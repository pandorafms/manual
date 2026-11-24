# Actualización de versiones de PHP

PHP es de esas dependencias que solo se recuerdan cuando ya no queda soporte.
La consola web de Pandora FMS se apoya en el PHP del sistema operativo, y una
versión sin mantenimiento sigue arrancando igual de contenta mientras acumula
vulnerabilidades sin parche. Este anexo reúne la actualización por
distribución: Rocky Linux, AlmaLinux y RHEL en versiones 8, 9 y 10 por un lado;
Ubuntu Server 22.04 por otro.

Los comandos van tal cual, sin reescrituras ni atajos. La prosa de alrededor
solo explica qué hace cada bloque y qué conviene comprobar; el comando no
negocia.

## Prerrequisitos

Antes de tocar repositorios conviene saber de dónde se parte y tener marcha
atrás.

| Requisito | Detalle |
|---|---|
| Terminal con usuario `root` o equivalente | Los comandos gestionan módulos de DNF, repositorios de APT y el servicio `php-fpm`; hacen falta privilegios de administrador. |
| Versión de PHP de partida | Ejecutar `php -v` y comprobar que está instalada la versión 7.x. |
| Copia de seguridad | Se recomienda hacer una copia de seguridad del servidor antes de resetear módulos o purgar paquetes. |

## Rocky Linux / AlmaLinux / RHEL 8, 9 y 10

!!! note "Comandos válidos para EL8, EL9 y EL10"
    Los comandos de esta sección (módulos de Remi e instalación) son idénticos
    en Rocky Linux, AlmaLinux y RHEL 8, 9 y 10. EL8 es soporte legacy; EL9 y
    EL10 son las versiones actuales. En EL10, `dnf module` avisa de que la
    modularidad está obsoleta, pero el comando sigue funcionando: es un aviso
    informativo, no un fallo.

Las tres distribuciones comparten procedimiento y sus comandos de módulo son
idénticos en las versiones 8, 9 y 10: lo único que cambia es el módulo de PHP
que se habilita. El primer paso resetea el módulo para que DNF no arrastre la
versión anterior; solo después se habilita el repositorio de Remi con la versión
elegida.

### Actualización a PHP 8.0

Configurar los repositorios:

```bash
dnf module reset php -y
dnf -y module enable php:remi-8.0
```

Instalar PHP:

```bash
dnf install -y \
php php-mcrypt php-cli php-gd \
php-curl php-session php-mysqlnd \
php-ldap php-zip php-zlib php-fileinfo \
php-gettext php-snmp php-mbstring \
php-pecl-zip php-xmlrpc \
php-xml php-yaml
```

Reiniciar **php-fpm**: `systemctl restart php-fpm`.

Verificar la versión instalada: `php -v`.

### Actualización a PHP 8.2

El procedimiento de 8.2 condensa configuración, instalación y reinicio en un
único bloque. Se reproduce tal cual:

```bash
dnf module reset php -y
dnf -y module enable php:remi-8.2

dnf install -y \
php php-mcrypt php-cli php-gd \
php-curl php-session php-mysqlnd \
php-ldap php-zip php-zlib php-fileinfo \
php-gettext php-snmp php-mbstring \
php-pecl-zip php-xmlrpc \
php-xml php-yaml

systemctl restart php-fpm
```

Verificar la versión instalada: `php -v`.

### Actualización a PHP 8.4

Igual que la anterior, con el módulo `php:remi-8.4`:

```bash
dnf module reset php -y
dnf -y module enable php:remi-8.4

dnf install -y \
php php-mcrypt php-cli php-gd \
php-curl php-session php-mysqlnd \
php-ldap php-zip php-zlib php-fileinfo \
php-gettext php-snmp php-mbstring \
php-pecl-zip php-xmlrpc \
php-xml php-yaml

systemctl restart php-fpm
```

Verificar la versión instalada: `php -v`.

## Ubuntu Server 22.04

En Ubuntu el camino es otro. Primero se purga el PHP antiguo sin ceremonia,
después se añade el repositorio PPA de Ondrej y, por último, se ajusta
`/etc/php.ini` para que la consola trabaje con los límites que necesita: tiempo
de entrada, tiempo de ejecución, tamaño de subida, memoria, tamaño de POST y
funciones deshabilitadas. El script de la wiki está pensado para ejecutarse de
una vez y aquí se reproduce íntegro. Lo único que cambia entre una versión y
otra es la variable `PHPVER`.

### Actualización a PHP 8.2

```bash
dpkg -l | grep php | tee packages.txt
# Remove old PHP
# When upgrading from older PHP version:
a2disconf php8.1-fpm 2> /dev/null
a2disconf php8.0-fpm 2> /dev/null
dpkg -l | grep php | awk '{print $2}' | xargs apt -y purge


## Define new php
export DEBIAN_FRONTEND=noninteractive
export NEEDRESTART_SUSPEND=1
export PHPVER="8.2"
add-apt-repository ppa:ondrej/php
apt update
apt install -y php$PHPVER php$PHPVER-fpm php$PHPVER-common \
                    php$PHPVER-cli libapache2-mod-fcgid apache2 \
                    php$PHPVER-bz2 php$PHPVER-mbstring php$PHPVER-intl  php$PHPVER-mcrypt \
                    php$PHPVER-gd  php$PHPVER-curl  php$PHPVER-mysql php$PHPVER-ldap \
                    php$PHPVER-fileinfo php$PHPVER-gettext php$PHPVER-snmp php$PHPVER-mbstring \
                    php$PHPVER-zip php$PHPVER-xmlrpc php$PHPVER-xml php$PHPVER-yaml

a2enmod proxy_fcgi setenvif
a2enconf php$PHPVER-fpm

## Prepare php config
rm -f /etc/php.ini
ln -s /etc/php/$PHPVER/fpm/php.ini /etc/
sed --follow-symlinks -i -e "s/^max_input_time.*/max_input_time = -1/g" /etc/php.ini
sed --follow-symlinks -i -e "s/^max_execution_time.*/max_execution_time = 0/g" /etc/php.ini
sed --follow-symlinks -i -e "s/^upload_max_filesize.*/upload_max_filesize = 800M/g" /etc/php.ini
sed --follow-symlinks -i -e "s/^memory_limit.*/memory_limit = 800M/g" /etc/php.ini
sed --follow-symlinks -i -e "s/.*post_max_size =.*/post_max_size = 800M/" /etc/php.ini
sed --follow-symlinks -i -e "s/^disable_functions/;disable_functions/" /etc/php.ini

systemctl enable php$PHPVER-fpm --now
systemctl restart php$PHPVER-fpm
systemctl restart apache2
```

Verificar la versión instalada: `php -v`.

### Actualización a PHP 8.4

Mismo script con `PHPVER="8.4"`:

```bash
dpkg -l | grep php | tee packages.txt
# Remove old PHP
# When upgrading from older PHP version:
a2disconf php8.1-fpm 2> /dev/null
a2disconf php8.0-fpm 2> /dev/null
dpkg -l | grep php | awk '{print $2}' | xargs apt -y purge


## Define new php
export DEBIAN_FRONTEND=noninteractive
export NEEDRESTART_SUSPEND=1
export PHPVER="8.4"
add-apt-repository ppa:ondrej/php
apt update
apt install -y php$PHPVER php$PHPVER-fpm php$PHPVER-common \
                    php$PHPVER-cli libapache2-mod-fcgid apache2 \
                    php$PHPVER-bz2 php$PHPVER-mbstring php$PHPVER-intl  php$PHPVER-mcrypt \
                    php$PHPVER-gd  php$PHPVER-curl  php$PHPVER-mysql php$PHPVER-ldap \
                    php$PHPVER-fileinfo php$PHPVER-gettext php$PHPVER-snmp php$PHPVER-mbstring \
                    php$PHPVER-zip php$PHPVER-xmlrpc php$PHPVER-xml php$PHPVER-yaml

a2enmod proxy_fcgi setenvif
a2enconf php$PHPVER-fpm

## Prepare php config
rm -f /etc/php.ini
ln -s /etc/php/$PHPVER/fpm/php.ini /etc/
sed --follow-symlinks -i -e "s/^max_input_time.*/max_input_time = -1/g" /etc/php.ini
sed --follow-symlinks -i -e "s/^max_execution_time.*/max_execution_time = 0/g" /etc/php.ini
sed --follow-symlinks -i -e "s/^upload_max_filesize.*/upload_max_filesize = 800M/g" /etc/php.ini
sed --follow-symlinks -i -e "s/^memory_limit.*/memory_limit = 800M/g" /etc/php.ini
sed --follow-symlinks -i -e "s/.*post_max_size =.*/post_max_size = 800M/" /etc/php.ini
sed --follow-symlinks -i -e "s/^disable_functions/;disable_functions/" /etc/php.ini

systemctl enable php$PHPVER-fpm --now
systemctl restart php$PHPVER-fpm
systemctl restart apache2
```

Verificar la versión instalada: `php -v`.
