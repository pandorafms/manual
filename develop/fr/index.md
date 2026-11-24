# Pandora FMS — Documentation produit

Pandora FMS est une plateforme de supervision : elle surveille des serveurs, des
réseaux, des applications et des services, et prévient quand quelque chose sort
de la normale avant que l'utilisateur final ne le remarque. Pour cela, elle
s'appuie sur des **EndPoints** installés dans la machine, sur des contrôles
distants qui ne touchent pas la cible, sur **Discovery** pour trouver seul ce qui
vit sur le réseau, et sur un moteur d'événements et d'alertes qui décide qui
déranger et quand. Au-dessus de ces données se montent des tableaux de bord, des
rapports et des cartes pour que l'information serve à celui qui la regarde, pas
seulement à celui qui la collecte.

Cette documentation couvre le produit : quoi installer, comment le configurer et
ce que fait chaque pièce. Ce n'est ni un manuel d'architecture réseau ni un guide
général de supervision ; c'est la référence de Pandora FMS.

## Par où commencer

Si vous installez Pandora FMS pour la première fois, commencez par la
[Partie 01 — Installation](parte-1/1.1-instalacion.md) : elle couvre le serveur,
la console, l'EndPoint et le satellite, avec leurs prérequis. Si votre
environnement tourne déjà et que vous cherchez un jeton précis ou le détail exact
d'une option, la
[Partie 09](parte-9/9.1-referencia-completa-de-configuracion-del-endpoint.md) est
la référence technique complète. Les annexes (Partie 11) rassemblent des
procédures ponctuelles et le glossaire des termes.

## Carte de la documentation

| Partie | Contenu |
|---|---|
| [01. Démarrage rapide](parte-1/1.1-instalacion.md) | Installation, architecture, politique de versions et support, mises à jour et licences |
| [02. Supervision avec Pandora FMS](parte-2/2.1-monitorizacion-con-endpoints.md) | EndPoints, identifiants, Discovery, Host et appareils, tâches de console, réseaux, netflow, politiques et supervision par domaine (applications, conteneurs, UX, Cloud, IoT, API, logs) |
| [03. Gestion des actifs et automatisation IT](parte-3/3.1-inventario.md) | Inventaire, contrôle à distance, distribution de logiciels, mise à jour corrective, NCM, IPAM, ITSM |
| [04. Gestion des utilisateurs et des permissions](parte-4/4.1-grupos-perfiles-y-tags.md) | Groupes, profils, tags, authentification externe, ACL Enterprise |
| [05. Apporter de la valeur à la supervision](parte-5/5.1-dashboards.md) | Tableaux de bord, rapports, événements, alertes, cartes, capacity planning |
| [06. Évolutivité et environnements complexes](parte-6/6.1-arquitecturas-distribuidas.md) | Architectures distribuées, satellites, Command Center, base de données d'historique, haute disponibilité |
| [07. Sécurité et supervision](parte-7/7.1-arquitectura-de-seguridad-de-pandora.md) | SIEM, SOAR, vulnérabilités, durcissement, FIM, conformité |
| [08. Pandora AI](parte-8/8.1-introduccion-e-instalacion.md) | Introduction, installation, utilisation du chat, tâches programmées, sécurité et audit |
| [09. Autres aspects avancés](parte-9/9.1-referencia-completa-de-configuracion-del-endpoint.md) | Référence complète de configuration, plugins, API REST, dépannage |
| [10. Base de données](parte-10/10.1-esquema-de-la-base-de-datos.md) | Schéma de la base de données : carte par zones, tables principales, codes, historique et référence complète des tables |
| [11. Annexes techniques](anexos/a1-actualizacion-de-versiones-de-php.md) | Procédures ponctuelles et glossaire des termes |
| [12. Questions fréquentes (FAQ)](parte-12/12.1-que-es-este-faq.md) | Questions récurrentes de la communauté et du support, vérifiées et mises à jour, classées par thème |

### Questions fréquentes (FAQ)

La Partie 12 rassemble les questions qui reviennent le plus, déjà confrontées au
code et mises à jour. Neuf sections par thème, plus la page d'accueil :

- [12.1 Qu'est-ce que cette FAQ](parte-12/12.1-que-es-este-faq.md) — ce que vous trouverez ici et l'index des sections.
- [12.2 Serveur et base de données](parte-12/12.2-servidor-y-base-de-datos.md) — le serveur qui ne démarre pas ou qui tombe, et la base de données lente ou endommagée.
- [12.3 Agents et systèmes](parte-12/12.3-agentes-y-sistemas.md) — l'agent qui n'apparaît pas, Tentacle, les files d'attente XML et les particularités de Windows et de Linux.
- [12.4 Console web et licences](parte-12/12.4-consola-web-y-licencias.md) — accès, réglages de sécurité et licence (la renouveler).
- [12.5 Modules et réseau](parte-12/12.5-modulos-y-red.md) — ICMP, WMI, contrôles web, MIB, traps et le port 162.
- [12.6 Alertes et événements](parte-12/12.6-alertas-y-eventos.md) — les alertes qui ne se déclenchent pas, celles qui se déclenchent trop et le courriel d'avis.
- [12.7 Rapports, logs et courrier](parte-12/12.7-informes-logs-y-correo.md) — les PDF qui ne sortent pas, les collections, la visionneuse de logs et le courrier qui n'arrive pas.
- [12.8 Grands environnements](parte-12/12.8-entornos-grandes.md) — Command Center, plusieurs nœuds, réplication d'événements et haute disponibilité.
- [12.9 Automatisation et plugins](parte-12/12.9-automatizacion-y-plugins.md) — CLI, API, macros et plugins.
- [12.10 Opérations massives](parte-12/12.10-operaciones-masivas.md) — déployer des agents, configurations massives et nettoyages.

!!! note "Documentation en cours"
    Tous les chapitres ne sont pas encore rédigés. Ceux qui manquent seront
    complétés au fur et à mesure ; si vous tombez sur une page sans contenu,
    revenez plus tard.
