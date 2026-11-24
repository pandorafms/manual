# Glossaire des termes

Ce glossaire réunit le vocabulaire qu'utilise la documentation de Pandora FMS :
les concepts de la plateforme, les pièces de son architecture et les termes de
versions et de licences qui apparaissent dans le reste du site. Il ne se lit pas
d'un bout à l'autre, il se consulte. Chaque entrée définit le terme en deux ou
trois phrases et, quand le sujet a son propre chapitre, y renvoie.

Les noms des états d'un module sont donnés en majuscules, avec l'anglais entre
parenthèses, car la console utilise les deux.

## A

### Accès de base et accès avancé

Deux niveaux d'autorisation qui peuvent être accordés à un utilisateur, à un
composant de module et à une alerte. Avec l'**accès de base**, on n'utilise que
les composants et les alertes de ce niveau. Avec l'**accès avancé**, ceux de
n'importe quel niveau. Les composants avancés se configurent davantage : on peut
changer leur nom, ils définissent les actions de leurs alertes et ils affichent
des champs que les composants de base n'ont pas, comme les unités ou les macros
d'un plugin.

### Action

Exécution qui a lieu lorsqu'une **alerte** se déclenche. Chaque action a ses
propres champs de configuration et une même alerte peut en déclencher plusieurs
à la fois. Il ne faut pas la confondre avec la **commande d'alerte**, qui est
l'exécution lancée par le serveur.

### ACL

De l'anglais *Access Control List*. Ils déterminent les autorisations des
utilisateurs. Dans Pandora FMS, ils se définissent en attribuant à un utilisateur
un **profil** sur un **groupe** : le profil indique quelles opérations sont
possibles et le groupe sur quels agents.

### Mise à jour manuelle

Seconde façon de mettre à jour une installation, sans passer par **Warp
Update** : les mêmes paquets, appliqués à la main dans le terminal avec
l'utilisateur `root` et dans un ordre qui ne se négocie pas (**console, schéma
de la base de données et serveur**). Elle donne le contrôle total du processus
et c'est la voie obligée quand la console ne peut pas télécharger les paquets.
Voir [Mises à jour](../parte-1/1.4-actualizaciones.md).

### Accord de niveau de service (SLA)

Accord négocié entre un client et un fournisseur de services. Dans Pandora FMS,
un manquement au SLA est signalé quand un module sort des valeurs considérées
comme normales. Le calcul regarde les données enregistrées dans la base de
données, pas les changements d'état du module. Les périodes **inconnues** et les
**arrêts planifiés** comptent comme valides, tout comme les périodes en état
d'avertissement.

### Agent

Entité organisationnelle de Pandora FMS. Elle représente généralement une
machine, un système ou un *hôte*, elle contient les **modules** qui la
surveillent et elle appartient à un seul groupe primaire. Elle a un nom unique
et, de façon facultative, un alias, qui, lui, peut se répéter. Elle peut être
reliée à d'autres agents (« parent-enfant »). Ce n'est pas la même chose que
l'**EndPoint** : l'agent est le conteneur logique de la console, l'EndPoint est
le programme qui collecte les données sur la machine.

### Alerte

Avis automatique sur l'état ou la valeur d'un module. Elle a deux états
possibles, déclenchée ou non déclenchée, et elle exécute des **actions**, comme
envoyer un courriel ou lancer une **commande d'alerte**. Les conditions de
déclenchement sont définies par le **modèle d'alerte**.

### Assistant de création de modules

Assistant (*wizard*) qui crée des modules de différents types dans plusieurs
instances à la fois. Il utilise les composants de module et les modèles
d'alerte, et il ne distingue pas entre les instances : il mélange agents et
modules comme s'ils venaient de la même source. Il est propre au **Command
Center**.

### AuthKey

Clé d'activation de la licence. Elle est envoyée par Pandora FMS, ou par son
distributeur, par courriel ou dans un PDF. C'est un numéro de 12 à 15 chiffres
qui **ne sert qu'une fois** et avec lequel on génère la licence de
l'installation. Voir [Licences](../parte-1/1.5-licenciamiento.md).

## B

### Base de données

Ensemble de données du même contexte, stockées de façon systématique pour un
usage ultérieur. Pandora FMS travaille avec MySQL, MariaDB ou Percona et y
accède par SQL. En pratique, on en gère deux : celle de temps réel et celle
d'historique, vers laquelle les données passent quand il n'est plus nécessaire
de les consulter à la seconde.

## C

### Vérification WMI

Interrogation distante d'une machine MS Windows via WMI et avec des identifiants.
C'est la voie pour extraire des données d'un Windows sans y installer un
**EndPoint**.

### Vérifications SNMP

Vérifications qui utilisent le protocole SNMP. Elles interrogent les OID exposés
par le fabricant (*polling*) et elles écoutent les *traps* que l'équipement
envoie de lui-même.

### Vérifications TCP

Vérifications distantes qui interrogent des équipements et des ordinateurs par
leurs ports ouverts, avec défi et réponse pour vérifier que le port répond.

### Commande

Instruction qui s'exécute dans un système d'exploitation, à la demande d'un
utilisateur ou d'une application. Dans la console du système, c'est la façon
habituelle d'administrer le serveur.

### Commande d'alerte

Exécution au niveau système que lance le serveur lorsqu'une **alerte** se
déclenche. Elle admet des commandes externes et des *scripts* propres.

### Commenter ou décommenter un paramètre

Mettre un paramètre en commentaire, avec le caractère spécial au début de sa
ligne, pour que le programme l'ignore. On le **décommente** quand on lui retire
ce caractère et que le paramètre est de nouveau lu.

### Command Center

Couche de gestion au-dessus de plusieurs installations de Pandora FMS, qu'elle
appelle **nœuds**. Depuis une seule interface, elles se voient ensemble, leur
configuration se synchronise et on opère sur toutes. Chaque nœud conserve son
serveur et sa base de données : le Command Center ne les remplace pas, il les
coordonne. C'est le nom en vigueur de l'ancienne **Metaconsola**. Voir
[Introduction et architecture](../parte-1/1.2-introduccion-y-arquitectura.md).

### Composant

Modèle pour créer un **module**. Il peut être local (l'EndPoint l'exécute sur la
machine) ou réseau, et parmi ceux du réseau il y a plugin, WMI, TCP, SNMP et
ICMP.

### Console web

Interface de Pandora FMS dans le navigateur. C'est celle qui sert à configurer,
exploiter et consulter la plateforme. Dans les menus, la première mention de
chaque section s'écrit « Console web » pour ne pas la confondre avec la console
du système.

## D

### DAEMON

De l'anglais *Disk And Execution Monitor*. Programme sans interface graphique
qui s'exécute au niveau du système d'exploitation avec peu ou pas d'interaction
de la part de l'utilisateur.

### Dépendance

Ensemble de fichiers, normalement compilés en langage machine, avec des
fonctions communes que peuvent utiliser une ou plusieurs applications du
système d'exploitation.

### Downgrade

Retour à la version précédente d'un serveur. Il s'utilise quand une mise à jour
(*upgrade*) apporte un inconvénient qu'on ne peut pas attendre de corriger.

## E

### EndPoint

Programme installé sur la machine pour collecter des informations locales. Il
reste en exécution, prend des données à chaque **intervalle** et les envoie au
serveur dans des fichiers XML, par Tentacle ou par l'API 2.0. C'est la pièce qui
apporte les données que l'on ne voit que de l'intérieur de la machine. Ce n'est
pas la même chose que l'**agent** : l'agent est le conteneur de la console.

### Environnements *nix

Abréviation pour désigner les environnements Unix et Linux.

### État du module

Les quatre états dans lesquels un module peut se trouver. **NORMAL** (*normal*)
est la valeur comprise dans ses seuils. **AVERTISSEMENT** (*warning*) et
**CRITIQUE** (*critical*) indiquent des conditions d'erreur de gravité
différente et ont des seuils indépendants. **INCONNU** (*unknown*) est l'état
d'un module qui n'a pas reçu de données depuis plus du double de son intervalle.

### Événement

Tout incident qui se produit dans les systèmes supervisés. Un événement va d'un
changement d'état d'un module à une alerte déclenchée ou rétablie, ou à un
redémarrage du système.

## F

### Faux positif et faux négatif

Un **faux positif** est une vérification qui renvoie une erreur qui ne s'est pas
produite. Un **faux négatif** est une vérification qui ne renvoie pas d'erreur
alors qu'elle s'est bien produite. La **protection Flip Flop** existe pour
amortir les deux.

### Feature Release (FR)

Version de fonctionnalités, celle qui apporte les nouveautés du produit. Une FR
ne reçoit des correctifs **que dans des situations précises**, celles que
reconnaît la politique officielle de support. Elle s'oppose à la **version
LTS**. Voir
[Politique de versions et de support](../parte-1/1.3-versiones-y-estabilidad.md).

### Fichier de données (XML de données)

Fichier XML que génèrent les **EndPoint**. Il contient les informations de
leurs modules et, en plus, les données de l'EndPoint lui-même : version, système
d'exploitation et le reste.

## H

### Hiverner ou hibernation

Enregistrer sur un dispositif de stockage fixe tout ce qui se trouve en mémoire
RAM, données et programmes en cours d'exécution, de la part d'un système
d'exploitation.

## I

### Instance

Installation de Pandora FMS préparée pour que le **Command Center** y accède et,
de façon facultative, pour répliquer ses événements dans le Command Center. Dans
le monde du Command Center, on l'appelle **nœud**.

### Intervalle inverse

Option qui définit des plages non contiguës dans les **seuils**. Dans les
modules de type chaîne de texte, le seuil se définit comme une sous-chaîne.

## K

### Kernel

Logiciel qui fait communiquer le matériel avec le reste des logiciels de la
machine et constitue l'essence d'un système d'exploitation.

## L

### Licence perpétuelle

Modèle de licence de la version on-premise. Elle s'acquiert une fois et, chaque
année, on renouvelle le support et la maintenance pour continuer à recevoir des
correctifs et des versions nouvelles. L'autre modèle on-premise est
l'**abonnement**. Voir [Licences](../parte-1/1.5-licenciamiento.md).

## M

### Merging (code)

Fusion de code source, par exemple pour incorporer une caractéristique nouvelle.
Il s'applique aussi à d'autres processus similaires, comme fusionner deux bases
de données sur un troisième serveur.

### Mode de débogage

Informations détaillées des processus et des paramètres d'une application, pas à
pas, pour localiser les exceptions et les erreurs de code.

### Module

Entité atomique d'information de Pandora FMS. Elle enregistre des valeurs
numériques ou alphanumériques et **une seule métrique** chacune (CPU, RAM,
trafic...). Elle vit à l'intérieur d'un **agent** et toujours associée à un seul ;
un agent peut avoir beaucoup de modules. Sa lecture s'interprète par des
**seuils**, qui donnent l'**état du module**.

### Supervision asynchrone

Celle d'un module qui renvoie des données en fonction de changements ou
d'événements, qui peuvent se produire ou non.

### Supervision synchrone

Celle d'un module qui renvoie des données à intervalles réguliers, par exemple
une mesure de température toutes les cinq minutes.

### Mosaïque

Apparition simultanée de différents documents ou de parties de ceux-ci,
normalement minimisés et sur un même plan. Elle s'utilise dans la console GIS.

## N

### Nœud

Chacune des installations de Pandora FMS que gère un **Command Center**. Elle
conserve son propre serveur et sa propre base de données. La licence du Command
Center se compte par nœuds actifs, et les répliques de redondance ne
s'additionnent pas.

## O

### OpenSSH

Ensemble d'applications qui permettent des communications chiffrées à travers un
réseau avec le protocole SSH.

## P

### Pandora Web Robot Daemon

**PWRD**. Il fournit les outils pour automatiser des sessions de navigation web
et les superviser ensuite avec WUX.

### Paquet

Programme ou ensemble de programmes empaquetés dans un format prêt à installer
sur un système d'exploitation et une version donnés.

### Paquet .disco

Paquet installable d'un assistant de Discovery (applications, clouds ou autres
origines). Il s'installe depuis le Marketplace ou en téléversant le fichier
`.disco`, et chaque tâche créée avec lui réalise la supervision qu'il déclare.
Voir
[Étendre Discovery](../parte-2/2.3-monitorizacion-y-descubrimiento-automatico-con-discovery.md).

### Correctif

Correction sur une version déjà publiée. Un correctif apporte de la sécurité et
des corrections de bugs critiques, et il ne rétroporte pas vers la version
corrigée les améliorations qui n'existent que dans des versions plus récentes.
Dans la version LTS, ils se numérotent sur la base : la 800 reçoit 800.1, 800.2
et ainsi de suite. Voir
[Politique de versions et de support](../parte-1/1.3-versiones-y-estabilidad.md).

### Profil

Ensemble d'autorisations sur les opérations possibles dans Pandora FMS : voir un
agent, le modifier, lui attribuer des alertes et le reste. Il s'attribue à un
utilisateur et toujours sur un groupe déterminé.

### Ping

Utilitaire de diagnostic de réseaux qui vérifie la latence et la connectivité
entre la machine locale et une autre distante, au niveau du protocole IP. Il
utilise des paquets ICMP de demande (*Echo Request*) et de réponse
(*Echo Reply*).

### Modèle d'alerte

Définit les conditions de déclenchement d'une **alerte** : la valeur ou l'état
du module qui la déclenche, combien de fois elle peut se déclencher dans un
intervalle et dans quelle plage horaire.

### Polling SNMP

Interrogation régulière par SNMP depuis Pandora FMS vers les équipements
supervisés.

### Protection Flip Flop

Mécanisme qui évite qu'un module change d'état à la première oscillation de sa
valeur. Le phénomène *flip flop* est la valeur qui alterne fréquemment entre
mauvais et bon. La protection se configure avec le **seuil FF** (*FF
threshold*), le nombre de fois consécutives où la condition doit se produire
pour que le changement ait lieu, plus l'intervalle FF. Elle amortit les faux
positifs et négatifs.

## R

### Rotation des journaux

De l'anglais *log rotation*. Processus automatisé d'administration de systèmes
dans lequel les fichiers journaux sont compressés, archivés, renommés ou
supprimés. Les données nouvelles vont dans un fichier nouveau, normalement au
même emplacement.

## S

### Serveur

Le `Pandora Server`. Il traite les informations que collectent les autres
pièces, exécute les alertes, applique les politiques et enregistre les données
dans la base de données. Depuis la version 784, il regroupe en moins de
processus plusieurs services qui étaient auparavant des instances séparées, et
chacun peut être activé ou désactivé selon le besoin.

### Serveur distant

Serveur auquel on accède par le réseau, par opposition au serveur local.

### Serveur satellite

Installation de Pandora FMS qui surveille un réseau distant sans dépendre de la
connexion au serveur principal. Elle interroge le serveur toutes les quelques
secondes (30 par défaut) pour savoir s'il y a des changements, elle lance
elle-même la connexion (aucun port à exposer) et elle admet un tunnel SSH
inverse depuis la version 785. Voir
[Introduction et architecture](../parte-1/1.2-introduccion-y-arquitectura.md).

### Shell ou ligne de commande

Interface qui permet de saisir des commandes sur une machine avec le clavier.

### SIEM

De l'anglais *Security Information and Event Management*. Système qui collecte,
filtre, normalise, corrèle et présente des événements de sécurité. Ce que Pandora
SIEM apporte, c'est que la collecte est déjà faite. Les journaux qui
l'alimentent sont les mêmes que ceux que collecte déjà la plateforme. Le moteur
d'événements de sécurité s'appuie sur ce travail préalable, au lieu de monter un
second système à part.

### Logiciel natif

Le logiciel, ou les formats de données, conçus pour s'exécuter ou être traités
sur un système d'exploitation concret.

### Superadmin

Superutilisateur de Pandora FMS, comme `root` l'est sous Linux. À l'installation
d'un serveur complet, un utilisateur `admin` est créé, qui est le premier
superadmin, et il n'est pas le seul : il y a des utilisateurs avec le **bit
d'accès PM**, pratiquement identiques sauf qu'ils ne peuvent pas créer de
commandes d'alerte ni nommer d'autres superadmins. Certaines fonctions ne sont
accessibles qu'à un superadmin.

### Abonnement

Modèle de licence de la version on-premise dans lequel on paie chaque année,
avec le support et la maintenance inclus tant que dure le contrat. Le logiciel
et les fonctionnalités sont les mêmes qu'avec la **licence perpétuelle**, le
choix relève donc de la trésorerie, pas du produit. Voir
[Licences](../parte-1/1.5-licenciamiento.md).

### SVN / Subversion / Dépôt de code

Système de contrôle de versions qui conserve un dépôt avec les différentes
versions des fichiers d'un projet tout au long de sa vie.

### Sync Server

Pièce qui inverse le problème quand le réseau distant ne peut pas lancer de
communication vers le serveur. Le serveur principal prend l'initiative et va
chercher les données sur un serveur Tentacle déployé dans le réseau isolé, qui
sert d'entrepôt temporaire : l'information s'y accumule jusqu'à ce que le
principal la télécharge, et ce qui est téléchargé disparaît de l'entrepôt. Voir
[Introduction et architecture](../parte-1/1.2-introduccion-y-arquitectura.md).

## T

### Tarball

Archive avec un programme ou plusieurs empaquetés au format TAR. Contrairement à
un **paquet**, elle ne porte pas d'information sur la façon de l'installer et
n'est pas spécifique à un système d'exploitation.

### Tentacle

Protocole de transfert de données qu'utilisent les **EndPoint** et le **serveur
satellite** pour envoyer des données au serveur de Pandora FMS. Il est
multiplateforme et il utilise par défaut le port 41121, attribué par l'IANA.

## U

### Seuil

Valeur minimale ou maximale d'un module à partir de laquelle se produit un
changement d'**état**.

### Seuil d'alerte (Alert threshold)

Intervalle de temps pendant lequel s'appliquent les restrictions définies dans
le **modèle d'alerte**.

### Utilisateur root

Dans les environnements *nix, l'utilisateur dédié à l'administration du système
d'exploitation, avec des privilèges spéciaux pour installer, configurer et
maintenir le logiciel. D'autres utilisateurs peuvent hériter de ces privilèges
s'ils appartiennent au groupe `root`.

## V

### Version LTS

Version de support prolongé. Le support dure **deux ans**, prolongeables de deux
ans de plus avec un contrat de support de longue durée. Elle reçoit les
correctifs de sécurité et de bugs critiques, pas les fonctionnalités des
versions supérieures, et elle coexiste avec les **Feature Release**, qui
apportent les nouveautés. Voir
[Politique de versions et de support](../parte-1/1.3-versiones-y-estabilidad.md).

## W

### Warp Update

Système de mise à jour depuis la console elle-même. Ses assistants téléchargent,
appliquent et vérifient la mise à jour, et il existe aussi un mode hors ligne
pour les environnements isolés. C'est la voie recommandée face à la **mise à
jour manuelle**. Voir [Mises à jour](../parte-1/1.4-actualizaciones.md).

### Watchdog

Fonctionnalité qui vérifie si un système est en cours d'exécution et, s'il est
arrêté, le redémarre.

### Widget

Élément d'interface qui offre un point d'interaction pour un type de données. Il
montre une disposition de l'information que l'utilisateur peut modifier, comme
une fenêtre ou une zone de texte. Combinés dans une application, ils réunissent
les données traitées et les interactions disponibles sur celles-ci.
