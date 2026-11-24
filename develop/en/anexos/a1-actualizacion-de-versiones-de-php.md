# Upgrading PHP versions

PHP is one of those dependencies you only remember once support has run out. The
Pandora FMS web console relies on the PHP of the operating system, and an
unmaintained version keeps starting up just as happily while it piles up
unpatched vulnerabilities. This annex gathers the upgrade per distribution:
Rocky Linux, AlmaLinux and RHEL in versions 8, 9 and 10 on one side; Ubuntu
Server 22.04 on the other.

The commands are given as they are, with no rewrites and no shortcuts. The prose
around them only explains what each block does and what is worth checking; the
command does not negotiate.

## Prerequisites

Before touching repositories it is worth knowing where you start from and having
a way back.

| Requirement | Detail |
|---|---|
| Terminal with the `root` user or equivalent | The commands manage DNF modules, APT repositories and the `php-fpm` service; administrator privileges are required. |
| Starting PHP version | Run `php -v` and check that version 7.x is installed. |
| Backup | A backup of the server is recommended before resetting modules or purging packages. |

## Rocky Linux / AlmaLinux / RHEL 8, 9 and 10

!!! note "Commands valid for EL8, EL9 and EL10"
    The commands in this section (Remi modules and installation) are identical
    in Rocky Linux, AlmaLinux and RHEL 8, 9 and 10. EL8 is legacy support; EL9
    and EL10 are the current versions. On EL10, `dnf module` warns that
    modularity is obsolete, but the command still works: it is an informative
    warning, not a failure.

The three distributions share the procedure and their module commands are
identical in versions 8, 9 and 10: the only thing that changes is the PHP module
that is enabled. The first step resets the module so that DNF does not drag the
previous version along; only then is the Remi repository enabled with the chosen
version.

### Upgrade to PHP 8.0

Configure the repositories:

```bash
dnf module reset php -y
dnf -y module enable php:remi-8.0
```

Install PHP:

```bash
dnf install -y \
php php-mcrypt php-cli php-gd \
php-curl php-session php-mysqlnd \
php-ldap php-zip php-zlib php-fileinfo \
php-gettext php-snmp php-mbstring \
php-pecl-zip php-xmlrpc \
php-xml php-yaml
```

Restart **php-fpm**: `systemctl restart php-fpm`.

Check the installed version: `php -v`.

### Upgrade to PHP 8.2

The 8.2 procedure condenses configuration, installation and restart into a
single block. It is reproduced as it is:

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

Check the installed version: `php -v`.

### Upgrade to PHP 8.4

Same as the previous one, with the `php:remi-8.4` module:

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

Check the installed version: `php -v`.

## Ubuntu Server 22.04

On Ubuntu the path is different. First the old PHP is purged without ceremony,
then the Ondrej PPA repository is added and, finally, `/etc/php.ini` is adjusted
so that the console works with the limits it needs: input time, execution time,
upload size, memory, POST size and disabled functions. The script from the wiki
is meant to be run in one go and it is reproduced in full here. The only thing
that changes from one version to another is the `PHPVER` variable.

### Upgrade to PHP 8.2

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

Check the installed version: `php -v`.

### Upgrade to PHP 8.4

Same script with `PHPVER="8.4"`:

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

Check the installed version: `php -v`.
