# Compatibilité et migration vers la nouvelle architecture de serveurs

`Pandora Server` regroupe des serveurs spécialisés dans une application
multithread : chacun parcourt sa propre file de tâches (modules à traiter,
agents à analyser, alertes à évaluer) avec son propre nombre de threads. Cet
annexe décrit comment la supervision distante se répartit aujourd'hui et ce
qu'il reste de la génération précédente d'instances spécialisées par type de
vérification. Le nombre de processus du système ne se déduit pas de cette
répartition.

## Pourquoi moins de serveurs

La génération précédente distinguait davantage d'instances spécialisées : ICMP,
SNMP, WMI, plugins distants et inventaire distant, entre autres. Le wiki décrit
une consommation de mémoire élevée même avant de traiter des modules ; il
n'établit pas que chaque sous-type équivalait à un processus indépendant du
système d'exploitation.

Le changement regroupe plusieurs types de vérification dans un même serveur,
avec davantage de threads à l'intérieur. Le consommateur réseau peut prendre en
charge WMI et ICMP lorsque `networkhpserver` est désactivé, sans avoir besoin
d'une instance spécialisée par type. Chaque vérification conserve son propre
délai d'attente : regrouper des serveurs ne signifie pas aligner leurs timeouts.

## Inventaire historique des serveurs

Le wiki énumère **21 dénominations de la génération précédente**. C'est un
inventaire historique, et non la liste des serveurs que démarre la configuration
actuelle, ni une prévision de ceux qui existeront dans d'autres versions :

Data Server · SNMP Console · Syslog Server · Export Server · Sync Server ·
Discovery Server · WEB Server · Network Server · WMI Server · Plugins Server ·
Inventory Server · ICMP Server · SNMP Server · Event Server · Log Server ·
SIEM Server · NetFlow Server (sFlow inclus) · NCM Server ·
Policy Manager Server · WUX Server · MADE Server.

Dans cette liste, **SNMP Server** désignait les vérifications de modules SNMP ;
**SNMP Console** recevait les traps. Les noms anciens ne correspondent pas à eux
seuls à des instances spécialisées au démarrage actuel.

## Ce que fait chaque serveur aujourd'hui

De toute la famille de serveurs qui existait, seuls trois se partagent
aujourd'hui la supervision distante (agents sans EndPoint, ou EndPoints vérifiés
aussi de l'extérieur) :

| Serveur | Jeton | Ce qu'il exécute |
|---|---|---|
| Réseau (`Network Server`) | `networkserver` | TCP, commandes distantes (SSH et Windows distant), WMI, modules de prédiction et modules web ; également ICMP et SNMP ordinaires si `networkhpserver` est explicitement désactivé |
| Réseau haute performance (`Network HP Server`) | `networkhpserver` | ICMP par lots avec `fping` et SNMP par lots avec `pandorafsnmp` (v1, v2c et v3) |
| Heavy (`Heavy Server`) | `heavyserver` | Plugins distants de serveur, inventaire distant, gestion de la configuration des équipements réseau ([NCM](../parte-3/3.6-gestion-de-configuracion-de-equipos-de-red-ncm.md)) et exportation de données vers un autre Pandora FMS |

La répartition d'ICMP et de SNMP entre les deux premiers n'est pas un choix de
l'administrateur module par module : avec le serveur de réseau haute performance
actif (il l'est d'usine), le serveur de réseau renonce à ICMP et à SNMP et garde
le reste ; si `networkhpserver` est explicitement désactivé, le serveur de
réseau reprend les deux à sa charge, requête par requête, avec les outils du
système plutôt qu'avec le traitement par lots. Il n'y a qu'une exception : un
module SNMP qui accumule plus d'erreurs que ne le permet la nouvelle tentative
(`braa_retries`) bascule vers le serveur de réseau, même si celui de haute
performance reste actif. Si le serveur de haute performance ne démarre pas faute
de `fping` ou de `braa`, son constructeur ne désactive pas `networkhpserver` :
il ne faut pas considérer la commutation automatique d'ICMP et de SNMP comme
acquise. Le détail de la répartition figure dans
[Supervision des réseaux](../parte-2/2.6-monitorizacion-de-redes.md).

Deux serveurs de la liste précédente de la version antérieure ont disparu sans
laisser de substitut propre : le serveur de prédiction et le serveur web. Leurs
fonctions n'ont pas été reprises par un nouveau serveur, mais par le serveur de
réseau lui-même, qui identifie le type de module avant de l'exécuter et appelle
la routine de prédiction ou celle de vérification web selon le cas, sans passer
par une instance spécialisée distincte.

Outre ces trois, le wiki décrit des serveurs associés au maître : le gestionnaire
de politiques sur un nœud, ainsi que la migration et l'auto-provisionnement sur
un Command Center. Le gestionnaire de politiques n'est pas un serveur à part : il
s'exécute depuis la console elle-même, et non comme un processus de serveur
indépendant. La migration et l'auto-provisionnement dans le Command Center
dépendent bien d'un interrupteur de serveur propre (voir le jeton
`provisioningserver` dans la
[référence complète](../parte-9/9.3-referencia-completa-de-configuracion-del-servidor.md#2-activation-des-serveurs-et-nombre-de-threads)).
Le serveur de synchronisation est désactivé d'usine ; pour démarrer, il exige
`syncserver` actif et `sync_address` défini. Son constructeur n'exige pas d'être
maître.

## Serveurs activés par défaut

Le modèle active cinq serveurs et laisse désactivés les onze interrupteurs
indiqués ci-dessous. Le démarrage effectif dépend aussi des prérequis de chaque
composant. Ce sont des valeurs **du modèle**, et non les valeurs internes
qu'utilise l'analyseur lorsqu'une option manque, ni un inventaire exhaustif de
toutes les fonctions du produit (voir la
[référence complète](../parte-9/9.3-referencia-completa-de-configuracion-del-servidor.md#2-activation-des-serveurs-et-nombre-de-threads)
de chaque jeton) :

| Activés dans le modèle | Désactivés dans le modèle |
|---|---|
| Données (`dataserver`) | Console SNMP (`snmpconsole`) |
| Réseau (`networkserver`) | Événements (`eventserver`) |
| Réseau haute performance (`networkhpserver`) | Journal (`logserver`) |
| Heavy (`heavyserver`) | WUX (`wuxserver`) |
| Discovery (`discoveryserver`) | Syslog (`syslogserver`) |
| — | RMM (`rmmserver`) |
| — | Alertes (`alertserver`) |
| — | NetFlow (`netflowserver`) |
| — | MADE (`madeserver`) |
| — | SIEM (`siemserver`) |
| — | Événements SIEM (`siemevents`) |

La liste des désactivés du wiki inclut **Mainframe Server**, mais il n'existe pas
d'interrupteur équivalent parmi les jetons de ce modèle ni parmi les options
qu'analyse `Config.pm` dans le checkout examiné. Aucune valeur par défaut ne lui
est donc attribuée, et il n'est pas déduit pour autant qu'il n'existe pas dans
d'autres composants. Le wiki qualifiait **Export Server** de désactivé par
défaut dans la répartition antérieure ; `heavyserver 1` ne permet pas de déduire
l'état actuel de l'exportation.

## Jetons retirés et leur substitut

L'installation au moyen des paquets de serveur examinés place la configuration
habituelle dans `/etc/pandora/pandora_server.conf`. L'exécutable accepte le
chemin du fichier comme argument, de sorte que cet emplacement n'est pas
obligatoire dans toutes les installations. Pour changer l'activation ou les
threads, modifiez le fichier qu'utilise **votre** service.

Les interrupteurs hérités sont toujours lus dans `pandora_server.conf`, mais ils
n'instancient pas les anciens serveurs dans le chemin de démarrage actuel. Les
anciens jetons de threads sont également analysés, mais ils **n'ajustent pas les
threads** des serveurs qui réalisent aujourd'hui ces tâches : il faut configurer
le nouveau jeton de threads indiqué dans chaque ligne.

| Jeton hérité (activation / threads) | Fonction actuelle | Substitut d'activation / threads |
|---|---|---|
| `predictionserver` / `prediction_threads` | Prédiction | `networkserver` / `network_threads` |
| `webserver` / `web_threads` | Web | `networkserver` / `network_threads` |
| `wmiserver` / `wmi_threads` | WMI | `networkserver` / `network_threads` |
| `icmpserver` / `icmp_threads` | ICMP | `networkhpserver` / `networkhpserver_threads` ; avec HP désactivé, `networkserver` / `network_threads` |
| `snmpserver` / `snmp_threads` | SNMP | `networkhpserver` / `networkhpserver_threads` ; avec HP désactivé ou au dépassement de `braa_retries`, `networkserver` / `network_threads` |
| `pluginserver` / `plugin_threads` | Plugins distants | `heavyserver` / `heavyserver_threads` |
| `inventoryserver` / `inventory_threads` | Inventaire distant | `heavyserver` / `heavyserver_threads` |
| `exportserver` / `export_threads` | Exportation | `heavyserver` / `heavyserver_threads` |
| `ncmserver` / `ncmserver_threads` | NCM | `heavyserver` / `heavyserver_threads` |

`snmpserver` conserve en outre une lecture spécifique pour vérifier l'activité de
`snmptrapd` ; il n'active pas le traitement des modules SNMP.

`reconserver` et `recon_threads` constituent un cas différent, et non une simple
équivalence : il n'a jamais existé de serveur de reconnaissance réseau séparé de
Discovery. `reconserver` est aujourd'hui un second interrupteur de marche pour le
Discovery Server lui-même, alternatif à `discoveryserver` (il suffit que l'un des
deux soit actif), et `recon_threads` continue de produire un effet : le nombre de
threads qu'utilise Discovery est le plus grand entre `discovery_threads` et
`recon_threads`, et non l'un des deux exclusivement. Il convient de ne pas y
toucher à l'aveugle en pensant qu'il s'agit d'un résidu sans effet.

## Vérifications à intervalles courts

L'intervalle de vérification habituel est de 300 secondes (5 minutes). Dans
l'éditeur de modules de la console web, des intervalles de 15 secondes sont
autorisés pour la disponibilité et la latence ICMP ainsi que pour SNMP numérique
et numérique incrémental ; l'éditeur rejette les valeurs inférieures à
15 secondes et les corrige avec un avertissement. La même validation fixe
300 secondes pour les types asynchrones 21, 22 et 23, et 60 secondes pour les
autres types vérifiés. Elle excepte les modules de Data Server avant d'appliquer
ces minimums : cela ne constitue pas une interdiction universelle pour tous les
modules et ne démontre pas une validation équivalente côté serveur.

Le seuil de 300 secondes affecte aussi deux autres comportements :

- **Aucun état inconnu n'est généré.** La vérification périodique qui marque un
  module comme inconnu lorsqu'il reste trop longtemps sans donnée exige un
  intervalle de 300 secondes ou plus ; avec un intervalle inférieur, ce module
  ne passe pas à inconnu par cette vérification d'inactivité.
- **La précision de la donnée change :** `process_data` formate les données
  numériques avec cinq décimales lorsque `module_interval` vaut 300 secondes ou
  moins, et avec une seule lorsqu'il dépasse 300 secondes. Le wiki décrit
  l'ordre inverse.

## Compactage et suppression des données à intervalle court

Avec une connexion active et opérationnelle à la base de données
[d'historique](../parte-6/6.5-base-de-datos-de-historico.md), la maintenance
appelle `pandora_historydb_smallint` avec un délai de **7 jours** pour les
modules dont `module_interval` est supérieur à zéro et inférieur à 300 secondes.
Le hook sélectionne ces modules et appelle le transfert vers l'historique module
par module. La purge et le transfert général s'exécutent avant, de sorte que ces
sept jours ne garantissent ni une semaine universelle de conservation ni le
transfert en l'absence de connexion à l'historique. Ce n'est pas un délai
configurable depuis
[Performances](../parte-9/9.2-referencia-completa-de-configuracion-de-la-consola.md#3-performances).

Lors du transfert de données numériques vers l'historique, un
[compactage](../parte-6/6.7-optimizacion-de-la-base-de-datos.md) par intervalles
temporels peut s'appliquer ; les données texte n'entrent pas dans cette branche.
Il est désactivé d'usine (`days_compact=0`) ; `step_compact` vaut `1` échantillon
par heure d'usine, et non les cinq indiqués dans le wiki. La console web permet
de le configurer entre 1 et 12 ; la routine limite également les valeurs hors de
cette plage. Le compactage regroupe les échantillons numériques par module et par
intervalle : il calcule la moyenne ou, pour les types `_proc`, conserve zéro si
un zéro apparaît. Cela ne revient pas à promettre un nombre exact d'échantillons
conservés par heure dans tous les cas. L'option se trouve dans
`Réglages → Configuration du système → Performances`, avec le reste des purges.
