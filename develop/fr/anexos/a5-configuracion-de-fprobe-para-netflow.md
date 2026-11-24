# Configuration de fprobe pour Netflow

## Quand utiliser une sonde fprobe

Si l'équipement réseau exporte déjà NetFlow, configurez-y la destination du
collecteur. S'il ne peut pas l'exporter, `fprobe` permet de capturer les
paquets sur une interface Linux et d'envoyer des enregistrements de flux au
collecteur de Pandora FMS. La sonde ne transforme pas une interface sans trafic
en fenêtre sur tout le réseau : pour observer le trafic d'un switch, il faut le
faire arriver sur cette interface, par exemple au moyen d'un port miroir. Et le
miroir doit transporter le trafic que l'on veut mesurer, pas celui qui restait
libre pour l'essai.

Cette annexe décrit la sonde NetFlow, pas le service de requêtes de Pandora
FMS. Pour activer et configurer le collecteur, consultez [Supervision du trafic
avec NetFlow](../parte-2/2.8-monitorizacion-de-trafico-con-netflow.md), section
« Activer et configurer Netflow et sFlow dans la console ».

## Prérequis et données préalables

Avant d'installer, notez l'interface réelle de capture, l'adresse du collecteur
et **le port UDP configuré sur celui-ci**. Ne présumez pas que le nom de
l'interface ou le port de l'exemple coïncident avec ceux de votre installation.

| Exigence | Détail |
|---|---|
| Équipement pour la sonde | Linux avec une interface qui reçoit le trafic souhaité et les droits pour installer le paquet et capturer des paquets. La procédure correspond à Ubuntu 22.04, où elle a été vérifiée. |
| Paquet `fprobe` | Outil externe à Pandora FMS, disponible dans les dépôts d'Ubuntu 22.04 (version 1.1-8 lors du test). Il s'installe avec `apt install fprobe`. |
| Interface de capture | Identifiez son nom avec `ip -br link` sur la machine de la sonde et confirmez qu'elle reçoit le trafic recherché. La suggestion `eth0` de l'installation décrite dans le wiki n'identifie pas nécessairement votre interface. |
| Collecteur NetFlow | `nfcapd` installé et Netflow activé sur le serveur Pandora FMS. Vérifiez dans la console web le port d'écoute et le chemin de données configurés ; le port initial de NetFlow est `9995/udp`, mais il peut être modifié. |
| Connectivité | La sonde doit pouvoir envoyer de l'UDP vers l'IP et le port du collecteur. Autorisez ce trafic dans les pare-feu et vérifiez que le collecteur écoute ; l'état de la sonde ne prouve pas à lui seul que les datagrammes arrivent. |

## Installer et configurer la sonde

Sur l'équipement Ubuntu 22 choisi pour la sonde, vérifiez d'abord quelle
interface reçoit les paquets. N'utilisez pas le nom qui apparaît dans un exemple
étranger :

```bash
ip -br link
sudo apt install fprobe
```

L'installation décrite dans le [wiki de développement de Pandora
FMS](https://pandorafms.com/manual/!development/es/documentation/pandorafms/monitoring/18_netflow#ks2_4_2_1)
demande l'interface de capture et la destination du collecteur. Indiquez
`<INTERFACE_DE_CAPTURE>` (le nom vérifié auparavant) et
`<IP_DU_COLLECTEUR>:<PORT_NETFLOW>` ; ce dernier doit coïncider avec le port UDP
configuré pour `nfcapd` dans la console web. Par exemple, si le collecteur écoute
sur le port initial, le format est `<IP_DU_COLLECTEUR>:9995`, et non une adresse
à copier littéralement. Les réponses sont enregistrées dans
`/etc/default/fprobe`, que vous pouvez modifier en cas d'erreur :

```bash
INTERFACE="<INTERFACE_DE_CAPTURE>"
FLOW_COLLECTOR="<IP_DU_COLLECTEUR>:<PORT_NETFLOW>"
OTHER_ARGS="-fip"
```

Après avoir modifié le fichier, redémarrez le service avec
`sudo systemctl restart fprobe`. Les paramètres `-d` (inactivité, 60 s par
défaut) et `-e` (flux actif, 300 s) peuvent être ajoutés à `OTHER_ARGS` si vous
avez besoin que les flux soient exportés plus tôt.

## Démarrer et vérifier la réception

Sur la sonde, vérifiez séparément que le service s'exécute :

```bash
sudo systemctl status fprobe
```

Si l'unité est arrêtée, examinez d'abord sa configuration et les messages du
service ; après les avoir corrigés, démarrez-la avec
`sudo systemctl start fprobe` et vérifiez de nouveau son état. Seulement si vous
voulez qu'elle démarre avec le système et qu'elle n'est pas encore activée,
exécutez `sudo systemctl enable fprobe`. Le paquet d'Ubuntu 22.04 fournit un
script d'init classique (`/etc/init.d/fprobe`), que `systemd` gère avec
`systemctl` ; ce script n'admet pas `service fprobe status`, utilisez donc
`systemctl` ou vérifiez le processus avec `pgrep -a fprobe`.

Générez du trafic qui **passe par l'interface de capture**. Sur le serveur du
collecteur, vérifiez que `nfcapd` écoute sur le port configuré et que des
fichiers `nfcapd.*` récents apparaissent dans le chemin de données Netflow
configuré dans Pandora FMS. Dès qu'il y a des fichiers de capture, consultez leur
contenu sur ce même serveur :

```bash
nfdump -R <CHEMIN_DE_DONNEES_NETFLOW>
```

Remplacez le marqueur par le chemin réel du collecteur, pas par celui de la
sonde. Si le chemin réseau général est `/var/spool/pandora/data_in/` et le
sous-répertoire `netflow`, le chemin résultant est
`/var/spool/pandora/data_in/netflow`. La présence d'un service actif sur la sonde
n'équivaut pas à de nouveaux fichiers ; de nouveaux fichiers sans enregistrements
du trafic attendu ne prouvent pas non plus que le port miroir observe ce que vous
vouliez. `nfdump` doit afficher des enregistrements de la période avec un trafic
connu avant de considérer la vérification comme terminée. Avec les valeurs par
défaut, un flux est exporté quand il est inactif depuis 60 secondes : attendez
une ou deux minutes après avoir généré le trafic avant de conclure que rien
n'arrive.

## Si aucun flux n'arrive

Examinez le tronçon où la chaîne s'interrompt, dans cet ordre :

1. L'interface choisie reçoit-elle le trafic que vous voulez mesurer ? Comparez
   le nom sélectionné avec `ip -br link` et vérifiez le port miroir ou le
   trajet réel des paquets. Un service actif ne peut pas capturer un trafic qui
   ne passe pas par cette interface.
2. La sonde pointe-t-elle vers l'IP et le port UDP de `nfcapd` configurés dans la
   console web ? Si le port a été changé par rapport à `9995`, changez aussi la
   destination de la sonde et vérifiez le pare-feu entre les deux équipements.
3. Netflow est-il activé et `nfcapd` écoute-t-il ? Le serveur Pandora FMS démarre
   le collecteur à son lancement ; après avoir activé Netflow ou changé son port,
   redémarrez le serveur Pandora FMS pour appliquer le changement au collecteur.
   Vérifiez ensuite l'écoute et les journaux du serveur.
4. Des fichiers récents apparaissent-ils dans le chemin de données configuré ?
   S'ils existent mais que `nfdump -R <CHEMIN_DE_DONNEES_NETFLOW>` n'affiche pas
   le trafic attendu, vérifiez de nouveau l'interface et la période consultée.
   Utilisez le chemin du collecteur ; la sonde envoie des flux, elle ne stocke
   pas là les fichiers de Pandora FMS.

La vérification se termine sur les enregistrements reçus, pas sur un « actif » de
`systemctl`. C'est une petite différence, jusqu'à ce qu'il faille expliquer
pourquoi le graphique reste vide.
