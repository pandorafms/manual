# Étendre les assistants SNMP et WMI avec des composants propres

Les assistants SNMP et WMI de la fiche de l'agent (voir
[Assistant SNMP](../parte-2/2.6-monitorizacion-de-redes.md#assistant-snmp) et
[Windows sans agent : WMI](../parte-2/2.6-monitorizacion-de-redes.md#windows-sans-agent-wmi))
n'apportent pas une liste fixe de modules : ils proposent ce qu'ils trouvent dans
un catalogue de **composants de l'assistant**. Cette annexe explique comment
étendre ce catalogue avec des fabricants et des composants propres, pour les deux
assistants.

## Ce que sont les composants de l'assistant et quand les créer

Un composant de l'assistant est un modèle qui décrit quoi interroger sur
l'équipement et comment le convertir en module. Lorsque l'assistant explore un
équipement, il n'improvise pas : il parcourt ce catalogue et propose les
composants qui correspondent à ce qu'il a trouvé (le fabricant, en SNMP),
regroupés en blocs selon ce qu'ils mesurent.

Créer un composant propre vaut la peine dans trois cas : un fabricant que
l'assistant ne reconnaît pas encore (l'erreur « PEN n'est pas enregistré » de
[Assistant SNMP](../parte-2/2.6-monitorizacion-de-redes.md#assistant-snmp)), un
OID propriétaire que vous voulez toujours avoir sous la main sans le chercher à
chaque fois, ou une donnée qui ne provient pas d'un seul OID mais de la
combinaison de plusieurs. La différence avec un [composant réseau
ordinaire](../parte-2/2.6-monitorizacion-de-redes.md) tient à l'origine :
celui-là s'applique à la main, en le choisissant dans l'éditeur d'un module ; un
composant de l'assistant est proposé par l'assistant après exploration de
l'équipement, et un seul peut finir par générer de nombreux modules à la fois, un
par ligne trouvée.

!!! example "Quand en créer un et quand s'en passer"
    Un switch que l'assistant SNMP reconnaît déjà, mais auquel il manque un
    capteur de température propriétaire du fabricant : aucun composant nouveau
    n'est nécessaire, [Modules
    SNMP](../parte-2/2.6-monitorizacion-de-redes.md#modules-snmp) et l'OID sous
    la main suffisent pour ce cas ponctuel. Si en revanche la même sonde de
    température doit se répéter sur des dizaines d'équipements du même
    fabricant, un composant de l'assistant évite de la créer à la main sur
    chacun d'eux.

## Enregistrer un fabricant (PEN)

L'assistant SNMP identifie le fabricant de l'équipement par son **PEN**
(*Private Enterprise Number*) : un numéro que chaque fabricant enregistre auprès
de l'IANA et qui occupe une position fixe dans le `sysObjectID` que déclare
l'équipement. Si Pandora FMS n'a pas ce PEN enregistré, l'assistant s'arrête avec
l'avertissement « PEN n'est pas enregistré » et ne propose aucun composant, même
si l'équipement répond parfaitement en SNMP.

Enregistrer le PEN est la première étape, dans **Gestion → Configuration →
Modèles → Numéros privés d'entreprise** (*Private Enterprise Numbers*), avec
trois champs : **PEN** (le numéro que déclare l'équipement), **Fabricant** (le nom
court qui identifie ensuite ses composants) et **Description**. Enregistrer le
PEN ne fait que nommer le fabricant ; cela ne crée pas un seul module à soi seul,
ce sont les composants de la section suivante qui s'en chargent. Cela exige le
profil d'administration de la console.

L'installation apporte 27 fabricants déjà enregistrés, mais seuls quelques-uns
apportent en plus des composants de l'assistant : Cisco, HP, Juniper, F5,
Fortinet et deux numéros génériques pour les équipements qui exposent leurs
informations avec Net-SNMP/UCD, auxquels s'ajoutent les composants génériques
(**All**) proposés à n'importe quel équipement. Le reste des fabricants
enregistrés d'usine (D-Link, MikroTik, Alcatel-Lucent, Ubiquiti, Allied Telesis,
IBM, Dell, Apple, Oracle, Hitachi, Synology, Fujitsu, entre autres) ne fait plus
s'arrêter l'assistant, mais ne reçoit que ces composants génériques tant qu'on ne
lui a pas créé de composants propres. Un fabricant absent de la liste doit être
enregistré à la main, comme dans l'exemple suivant.

!!! example "Enregistrer un onduleur que l'assistant ne reconnaît pas"
    Un onduleur déclare un PEN qui ne figure pas dans le catalogue d'usine. On
    l'enregistre avec son numéro IANA dans **PEN**, `mi-sai` dans
    **Fabricant** et une description brève. À partir de là, l'assistant ne
    s'arrête plus pour cause de PEN non enregistré, même s'il ne propose encore
    aucun module : cela viendra avec le premier composant de la section
    suivante.

## Créer un composant de l'assistant

Les composants de l'assistant se créent dans **Gestion → Configuration →
Modèles → Composants distants**, en choisissant le type de composant assistant.
Ils partagent avec un composant réseau ordinaire les champs habituels —activé,
**Ajouter par défaut** (s'il apparaît déjà coché à l'ouverture de l'assistant),
nom, type de donnée, groupe du composant (le bloc dans lequel il apparaît
regroupé), unité et seuils, description— ainsi que le **Protocole du module**
(SNMP ou WMI) et l'**ID du fabricant** : un fabricant concret déjà enregistré,
ou **All**, qui offre le composant à n'importe quel équipement quel que soit son
PEN.

Deux champs décident du reste du formulaire et du type de module que le composant
va proposer :

- **Scan type** (type d'analyse) : **Fixed** (fixe) crée un seul module ;
  **Dynamic** (dynamique) parcourt une table de l'équipement et crée un module
  par ligne trouvée, sans savoir à l'avance combien il y en aura.
- **Execution type** (type d'exécution) : **Network** (réseau) fait lire la
  valeur directement par le serveur lui-même, comme un module SNMP ou WMI
  ordinaire ; **Plugin** délègue le calcul à un plugin de serveur ou, si
  l'assistant est lancé depuis un serveur satellite, à une commande
  `module_exec`.

| Analyse | Exécution | Ce qui est créé |
|---|---|---|
| Fixed | Network | Un seul module qui lit un OID (ou une requête WMI) directement |
| Fixed | Plugin | Un seul module dont la valeur est calculée par un plugin, à partir d'un ou plusieurs OID ou champs |
| Dynamic | Network | Un module par ligne d'une table, lu directement |
| Dynamic | Plugin | Un module par ligne d'une table, calculé par un plugin |

Dupliquer un composant existant avec l'action **Duplicate** de son listing est le
point de départ le plus rapide pour un nouveau composant similaire ; il n'existe
ni importation ni exportation de composants entre installations.

## Composants SNMP à OID statique

Combinaison analyse fixe + exécution réseau, la plus simple : **OID de la valeur**
est l'OID final qui va être lu, comme dans un module SNMP créé à la main. **Nom de
l'OID** est facultatif et, s'il est renseigné, sa valeur remplace la macro
`_nameOID_` dans le nom du module.

!!! example "Charge de batterie d'un onduleur"
    Avec le fabricant `mi-sai` déjà enregistré, un composant fixe nommé
    « Charge de batterie », avec l'OID propriétaire de charge dans **OID de la
    valeur**, des seuils d'avertissement et critique déjà renseignés et le
    groupe de composant « Énergie ». Dès que l'assistant SNMP est lancé sur un
    agent de ce fabricant, le composant apparaît dans son bloc correspondant,
    prêt à être coché.

## Composants SNMP à OID dynamique

Combinaison analyse dynamique + exécution réseau : **OID de la valeur** et **Nom
de l'OID** cessent d'être des OID finaux pour devenir deux branches
(*sous-arbres*) de l'équipement. L'assistant parcourt les deux entièrement,
croise les résultats par index —le même index dans les deux branches correspond à
la même ligne— et propose un module par index trouvé, avec le nom de cette ligne
en remplacement de `_nameOID_` et l'index lui-même ajouté à la fin de **OID de la
valeur**.

!!! example "Un module par capteur de température"
    Une table propriétaire expose, pour chaque capteur de température de
    l'équipement, son nom dans une branche et sa valeur dans une autre. Un
    composant dynamique avec **Nom de l'OID** pointant vers la branche des noms
    et **OID de la valeur** vers la branche des valeurs crée, après
    l'exploration, un module par capteur trouvé, chacun avec le nom réel de son
    capteur.

## Composants SNMP calculés par un plugin

Pour une donnée qui ne provient pas de la lecture d'un seul OID, l'exécution
passe à **Plugin**. Le formulaire ajoute alors quatre éléments :

- **OID des macros** : une entrée par OID participant au calcul, référencée dans
  le reste du formulaire comme `_oid_1_`, `_oid_2_`…
- **Opération des valeurs** : la formule qui combine ces valeurs, écrite avec les
  mêmes macros `_oid_N_`. Elle ne sert qu'à montrer la valeur dans l'aperçu de
  l'assistant ; le module créé ne l'utilise pas.
- **Plugin de serveur** : le plugin qui effectue réellement le calcul à chaque
  exécution du module. Les deux d'usine partagent les mêmes champs de connexion
  (`_address_`, `_port_`, `_version_`, `_community_` et les identifiants SNMPv3),
  mais diffèrent par ce qu'ils demandent ensuite :
    - **Wizard SNMP module**, pour des valeurs numériques : outre la connexion,
      il demande la **liste d'OID** (`_oid_1_,_oid_2_`…) et l'**Operation**, la
      formule qui combine ces valeurs écrite comme `_o1_`, `_o2_`… selon la
      position de chaque OID dans la liste.
    - **Wizard SNMP process**, pour savoir si un processus est en cours
      d'exécution : au lieu d'une liste d'OID, il demande un seul champ
      **Process** avec le nom du processus (sensible à la casse) ; le plugin
      vérifie lui-même, contre l'arbre SNMP des processus du système, s'il
      apparaît en exécution.
- **Exécution satellite** : la commande équivalente pour le cas où l'assistant
  est lancé depuis un [serveur
  satellite](../parte-6/6.2-servidores-satelite.md), qui utilise les plugins
  `wizard_snmp_module` et `wizard_snmp_process` installés sur le satellite.

Comme l'aperçu et l'exécution réelle utilisent des champs différents, la formule
d'**Opération des valeurs** et celle d'**Operation** doivent dire la même chose ;
sinon, l'assistant propose une valeur et le module finit par en mesurer une
autre.

En analyse dynamique, chaque `_oid_N_` cesse d'être un OID final pour devenir une
branche également parcourue par index, comme dans la section précédente ;
l'assistant calcule une valeur —et donc un module— par ligne trouvée.

!!! example "Pourcentage d'utilisation d'une partition"
    Deux OID d'une table de stockage, espace utilisé et espace total, sont
    enregistrés dans **OID des macros** comme `_oid_1_` et `_oid_2_`.
    **Opération des valeurs** est renseignée avec `(_oid_1_ * 100) / _oid_2_`,
    pour que l'aperçu montre déjà le pourcentage. Dans **Plugin de serveur**,
    on choisit « Wizard SNMP module », avec `_oid_1_,_oid_2_` dans la liste
    d'OID et `(_o1_ * 100) / _o2_` dans **Operation** ; les champs de connexion
    restent avec leurs macros. Chaque module créé calcule le pourcentage
    d'utilisation à chaque exécution, sans post-traitement.

## Composants WMI

L'assistant WMI utilise le même mécanisme de composants, avec son propre jeu de
champs : **Classe WMI** (la classe à interroger), **Champ de clé de requête**
(quelle colonne de la réponse identifie chaque ligne) et **Champs extra de
requête** (le reste des colonnes nécessaires). Chaque colonne est disponible
comme macro `_FIELDNAME_` avec la valeur de cette ligne. Comme en SNMP,
dynamique signifie un module par ligne renvoyée par la requête d'analyse.

Les **Filtres de requête** délimitent, d'une part, les lignes que rapporte
l'exploration et, d'autre part, la façon dont on calcule la valeur du module en
exécution réseau :

- **Field value** : le numéro de la colonne de la réponse dont la valeur devient
  celle du module (`0` est le champ clé lui-même ; `1` et au-delà, chaque champ
  extra de requête dans son ordre).
- **Key string** : facultatif. S'il est renseigné, la valeur du module cesse
  d'être la donnée brute et devient `1` ou `0` selon qu'elle correspond ou non à
  cette chaîne. Ce filtre ne s'applique pas lorsque l'assistant est lancé depuis
  un [serveur satellite](../parte-6/6.2-servidores-satelite.md) : le module
  généré sur le satellite renvoie toujours la donnée brute de **Field value**,
  même si **Key string** a été renseigné.

En exécution de plugin, ces deux filtres sont remplacés par :

- **Value operation** : la formule qui combine les champs de la ligne avec les
  macros `_f1_`, `_f2_`… (une par champ extra de requête, dans l'ordre).
- **Server plugin** : le plugin qui effectue le calcul ; celui d'usine est
  « Wizard WMI module », avec la macro `_class_wmi_` pour la classe interrogée et
  la même famille `_f1_`, `_f2_`… dans son champ **Operation**.
- **Satellite execution** : la commande équivalente pour le cas où l'assistant
  est lancé depuis un serveur satellite, avec le plugin `wizard_wmi_module`
  installé sur place.

!!! example "Espace libre de chaque disque local"
    Composant WMI dynamique sur la classe `Win32_LogicalDisk`, avec le filtre
    de requête `DriveType = 3` (disques locaux uniquement) et `_DeviceID_` dans
    le nom du module : l'assistant crée, sur chaque équipement Windows, un
    module d'espace libre par disque local trouvé, avec la lettre de lecteur
    dans le nom lui-même.

## Référence des champs

| Champ | Protocole | À quoi il sert |
|---|---|---|
| Ajouter par défaut | Commun | Le composant apparaît déjà coché à l'ouverture de l'assistant |
| Groupe du composant | Commun | Bloc dans lequel le composant est regroupé dans l'assistant |
| Protocole du module | Commun | SNMP ou WMI |
| ID du fabricant | SNMP | Fabricant (PEN enregistré) auquel le composant est offert, ou `All` pour n'importe lequel |
| Scan type | Commun | `Fixed` (un module) ou `Dynamic` (un module par ligne) |
| Execution type | Commun | `Network` (lecture directe) ou `Plugin` (calcul délégué) |
| Nom de l'OID | SNMP | OID (ou branche, en dynamique) dont la valeur remplace `_nameOID_` dans le nom |
| OID de la valeur | SNMP, réseau | OID final (ou branche, en dynamique) qui est lu |
| OID des macros | SNMP, plugin | Liste d'OID (ou de branches) participant à l'opération, sous la forme `_oid_N_` |
| Opération des valeurs | SNMP, plugin | Formule avec `_oid_N_` qui calcule la valeur affichée dans l'aperçu ; elle n'est pas utilisée dans le module créé |
| Plugin de serveur | SNMP, plugin | Plugin qui calcule la valeur à chaque exécution du module ; ses champs acceptent les macros du tableau suivant |
| Exécution satellite | SNMP, plugin | Commande équivalente pour le cas où l'assistant est lancé depuis un serveur satellite |
| Classe WMI | WMI | Classe qui est interrogée |
| Champ de clé de requête | WMI | Colonne de la réponse qui identifie chaque ligne |
| Champs extra de requête | WMI | Reste des colonnes nécessaires de la réponse |
| Filtres de requête (Scan / Execution) | WMI | Condition qui délimite l'exploration et, séparément, l'exécution du module |
| Field value | WMI, réseau | Numéro de colonne dont la valeur devient celle du module (`0` = champ clé) |
| Key string | WMI, réseau | Chaîne facultative qui convertit la valeur en `1`/`0` selon la correspondance ; elle est ignorée lors de l'exécution depuis un serveur satellite |
| Value operation | WMI, plugin | Formule avec `_f1_`, `_f2_`… qui calcule la valeur affichée dans l'aperçu |
| Exécution satellite | WMI, plugin | Commande équivalente pour le cas où l'assistant est lancé depuis un serveur satellite, avec le plugin `wizard_wmi_module` |

## Référence des macros

| Macro | Remplacée par | Où elle s'applique |
|---|---|---|
| `_nameOID_` | Nom obtenu depuis `Nom de l'OID` | Nom du module, composants SNMP |
| `_oid_N_` | Dans l'aperçu, la valeur lue ; dans les champs du plugin et dans l'exécution satellite, l'OID de la position N de `OID des macros` (avec son index, en dynamique) | `Opération des valeurs`, champs du `Plugin de serveur`, `Exécution satellite` |
| `_o1_`, `_o2_`… | Valeur de l'OID à cette position de la liste d'OID du plugin | Champ **Operation** du plugin « Wizard SNMP module » |
| `_FIELDNAME_` | Valeur de la colonne `FIELDNAME` de la ligne WMI actuelle | Composants WMI |
| `_class_wmi_` | Classe WMI du composant | Champs du `Server plugin` et `Exécution satellite`, composants WMI de plugin |
| `_field_wmi_N_` | Valeur du champ extra de requête numéro N | Composants WMI de plugin |
| `_f1_`, `_f2_`… | Valeur du champ extra de requête à cette position | `Value operation` et champ **Operation** du plugin « Wizard WMI module » |
| `_address_`, `_port_` | Adresse et port avec lesquels l'assistant a été lancé | Champs du `Plugin de serveur` et `Exécution satellite` (SNMP et WMI) |
| `_version_`, `_community_` | Version SNMP et communauté (v1/v2c) | Champs du `Plugin de serveur` et `Exécution satellite` (SNMP) |
| `_sec_level_`, `_auth_user_`, `_auth_method_`, `_auth_pass_`, `_priv_method_`, `_priv_pass_` | Identifiants SNMPv3 avec lesquels l'assistant a été lancé | Champs du `Plugin de serveur` et `Exécution satellite` (SNMP) |
| `_namespace_wmi_`, `_user_wmi_`, `_pass_wmi_` | Espace de noms et identifiants WMI avec lesquels l'assistant a été lancé | Champs du `Plugin de serveur` et `Exécution satellite` (WMI) |

Les deux assistants peuvent aussi être lancés sur une [politique de
supervision](../parte-2/2.10-politicas-de-monitorizacion.md) au lieu d'un agent
concret, avec une différence importante dans la façon de renseigner ces macros :
`_address_` reste tel quel, comme macro littérale, pour que chaque agent qui
reçoit la politique le remplace par sa propre adresse, comme dans tout autre
[module
réseau](../parte-2/2.6-monitorizacion-de-redes.md#macros-dans-les-champs-du-module) ;
le reste des macros de connexion —version, communauté, identifiants SNMPv3,
espace de noms et identifiants WMI— est également remplacé par ce qui a été écrit
au lancement de l'assistant, et reste figé dans le module de politique obtenu.
Avec une politique appliquée à des agents ayant des communautés ou des
identifiants différents, il convient de revoir ces valeurs dans chaque module
après l'avoir créé.

Créer le plugin qui exécute un calcul propre, au lieu de réutiliser ceux d'usine,
est expliqué dans [9.9 · Création de plugins
distants](../parte-9/9.9-creacion-de-plugins-remotos.md).
