# Mise à jour des versions de PHP

PHP est une de ces dépendances dont on ne se souvient qu'une fois le support
terminé. La console web de Pandora FMS s'appuie sur le PHP du système
d'exploitation, et une version sans maintenance continue de démarrer sans
broncher pendant qu'elle accumule des vulnérabilités sans correctif. Cette
annexe rassemble la mise à jour par distribution : Rocky Linux, AlmaLinux et
RHEL en versions 8, 9 et 10 d'un côté ; Ubuntu Server 22.04 de l'autre.

Les commandes sont données telles quelles, sans réécriture ni raccourci. La
prose autour explique seulement ce que fait chaque bloc et ce qu'il convient de
vérifier ; la commande ne se négocie pas.

## Prérequis

Avant de toucher aux dépôts, il convient de savoir d'où l'on part et de disposer
d'un retour arrière.

| Exigence | Détail |
|---|---|
| Terminal avec l'utilisateur `root` ou équivalent | Les commandes gèrent des modules de DNF, des dépôts d'APT et le service `php-fpm` ; des privilèges d'administrateur sont nécessaires. |
| Version de PHP de départ | Exécuter `php -v` et vérifier que la version 7.x est installée. |
| Sauvegarde | Il est recommandé de faire une sauvegarde du serveur avant de réinitialiser des modules ou de purger des paquets. |

## Rocky Linux / AlmaLinux / RHEL 8, 9 et 10

!!! note "Commandes valables pour EL8, EL9 et EL10"
    Les commandes de cette section (modules de Remi et installation) sont
    identiques sous Rocky Linux, AlmaLinux et RHEL 8, 9 et 10. EL8 relève du
    support historique ; EL9 et EL10 sont les versions actuelles. Sous EL10,
    `dnf module` signale que la modularité est obsolète, mais la commande
    fonctionne toujours : c'est un avertissement informatif, pas un échec.

Les trois distributions partagent la procédure et leurs commandes de module sont
identiques dans les versions 8, 9 et 10 : seul change le module de PHP activé.
La première étape réinitialise le module pour que DNF n'entraîne pas la version
précédente ; ensuite seulement le dépôt de Remi est activé avec la version
choisie.

### Mise à jour vers PHP 8.0

Configurer les dépôts :

```bash
dnf module reset php -y
dnf -y module enable php:remi-8.0
```

Installer PHP :

```bash
dnf install -y \
php php-mcrypt php-cli php-gd \
php-curl php-session php-mysqlnd \
php-ldap php-zip php-zlib php-fileinfo \
php-gettext php-snmp php-mbstring \
php-pecl-zip php-xmlrpc \
php-xml php-yaml
```

Redémarrer **php-fpm** : `systemctl restart php-fpm`.

Vérifier la version installée : `php -v`.

### Mise à jour vers PHP 8.2

La procédure pour 8.2 condense configuration, installation et redémarrage dans
un seul bloc. Elle est reproduite telle quelle :

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

Vérifier la version installée : `php -v`.

### Mise à jour vers PHP 8.4

Comme la précédente, avec le module `php:remi-8.4` :

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

Vérifier la version installée : `php -v`.

## Ubuntu Server 22.04

Sous Ubuntu, le chemin est différent. D'abord l'ancien PHP est purgé sans
cérémonie, ensuite le dépôt PPA d'Ondrej est ajouté et, enfin, `/etc/php.ini`
est ajusté pour que la console travaille avec les limites dont elle a besoin :
temps d'entrée, temps d'exécution, taille d'envoi, mémoire, taille de POST et
fonctions désactivées. Le script du wiki est prévu pour être exécuté d'un seul
coup et il est reproduit intégralement ici. La seule chose qui change d'une
version à l'autre est la variable `PHPVER`.

### Mise à jour vers PHP 8.2

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

Vérifier la version installée : `php -v`.

### Mise à jour vers PHP 8.4

Même script avec `PHPVER="8.4"` :

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

Vérifier la version installée : `php -v`.
