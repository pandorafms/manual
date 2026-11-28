# Guide de la documentation pour les agents IA

## Comment utiliser ce guide

| Étape | Action | Où |
| --- | --- | --- |
| 1 | Résoudre `latest` : lire `versions.json` et prendre la `version` dont la liste `aliases` contient `latest` | `https://raw.githubusercontent.com/pandorafms/manual/main/versions.json` |
| 2 | Lire l'index de l'édition dans la langue de l'utilisateur | `https://raw.githubusercontent.com/pandorafms/manual/main/<version>/llms.txt` |
| 3 | Ouvrir le chapitre choisi (chemin `.md` de l'index) | `https://raw.githubusercontent.com/pandorafms/manual/main/<version>/<chemin>.md` |
| 4 | Citer le chapitre et la section par leur titre | — |

| Langue | Index | Racine de l'édition |
| --- | --- | --- |
| es | `<version>/llms.txt` | `<version>/` |
| en | `<version>/en/llms.txt` | `<version>/en/` |
| fr | `<version>/fr/llms.txt` | `<version>/fr/` |

## Organisation du site

| Élément | Détail |
| --- | --- |
| Langues | es (racine de la version), en (`en/`), fr (`fr/`) |
| Versions | `develop` (quotidienne), `N` (figée, immuable), alias `latest` et `lts` |
| Markdown brut | À côté de chaque page : `<chemin>.md` en plus de `<chemin>/index.html` |
| Même chapitre dans une autre langue | Même chemin relatif sous `en/` ou `fr/` |
| Où il est servi aujourd'hui | `https://raw.githubusercontent.com/pandorafms/manual/main/` (GitHub) ; `https://pandorafms.com/docs/manual/latest/` quand le serveur le permettra |

| Partie | Chemin |
| --- | --- |
| Partie 01. Démarrage rapide | `parte-1/` |
| Partie 02. Supervision avec Pandora FMS | `parte-2/` |
| Partie 03. Gestion des actifs et automatisation IT | `parte-3/` |
| Partie 04. Gestion des utilisateurs et des permissions | `parte-4/` |
| Partie 05. Apporter de la valeur à la supervision | `parte-5/` |
| Partie 06. Évolutivité et environnements complexes | `parte-6/` |
| Partie 07. Sécurité et supervision | `parte-7/` |
| Partie 08. Pandora AI | `parte-8/` |
| Partie 09. Autres aspects avancés de Pandora FMS | `parte-9/` |
| Partie 10. Base de données | `parte-10/` |
| Partie 11. Annexes techniques | `anexos/` |
| Partie 12. Questions fréquentes (FAQ) | `parte-12/` |
| Partie 13. API v2 | `parte-13/` |

## Plan des chapitres

### Partie 01. Démarrage rapide

| N° | Chapitre | Chemin |
| --- | --- | --- |
| 1.1 | Installation | `parte-1/1.1-instalacion.md` |
| 1.2 | Introduction et architecture | `parte-1/1.2-introduccion-y-arquitectura.md` |
| 1.3 | Politique de versions et de support | `parte-1/1.3-versiones-y-estabilidad.md` |
| 1.4 | Mises à jour | `parte-1/1.4-actualizaciones.md` |
| 1.5 | Licences | `parte-1/1.5-licenciamiento.md` |

### Partie 02. Supervision avec Pandora FMS

| N° | Chapitre | Chemin |
| --- | --- | --- |
| 2.1 | Supervision avec des EndPoints | `parte-2/2.1-monitorizacion-con-endpoints.md` |
| 2.2 | Gestionnaire d'identifiants | `parte-2/2.2-gestor-de-credenciales.md` |
| 2.3 | Supervision et découverte automatique avec Discovery | `parte-2/2.3-monitorizacion-y-descubrimiento-automatico-con-discovery.md` |
| 2.4 | Découverte réseau avec Host et appareils | `parte-2/2.4-descubrimiento-de-redes-con-host-y-dispositivos.md` |
| 2.5 | Tâches de console | `parte-2/2.5-tareas-de-consola.md` |
| 2.6 | Supervision des réseaux | `parte-2/2.6-monitorizacion-de-redes.md` |
| 2.7 | Supervision des traps SNMP | `parte-2/2.7-monitorizacion-de-traps-snmp.md` |
| 2.8 | Supervision du trafic avec NetFlow | `parte-2/2.8-monitorizacion-de-trafico-con-netflow.md` |
| 2.9 | Collections | `parte-2/2.9-colecciones.md` |
| 2.10 | Politiques de supervision | `parte-2/2.10-politicas-de-monitorizacion.md` |
| 2.11 | Opérations massives | `parte-2/2.11-operaciones-masivas.md` |
| 2.12 | Supervision des applications | `parte-2/2.12-monitorizacion-de-aplicaciones.md` |
| 2.13 | Supervision des conteneurs et des orchestrateurs | `parte-2/2.13-monitorizacion-de-contenedores-y-orquestadores.md` |
| 2.14 | Supervision de l'expérience utilisateur (UX) | `parte-2/2.14-monitorizacion-de-experiencia-de-usuario-ux.md` |
| 2.15 | Supervision des environnements Cloud | `parte-2/2.15-monitorizacion-entornos-cloud.md` |
| 2.16 | Supervision des environnements virtualisés | `parte-2/2.16-monitorizacion-entornos-virtualizados.md` |
| 2.17 | Supervision IoT | `parte-2/2.17-monitorizacion-iot.md` |
| 2.18 | Supervision des API | `parte-2/2.18-monitorizacion-de-apis.md` |
| 2.19 | Collecte et supervision des logs | `parte-2/2.19-recoleccion-y-monitorizacion-de-logs.md` |
| 2.20 | Configuration commune des modules | `parte-2/2.20-configuracion-comun-de-los-modulos.md` |
| 2.21 | Configuration commune des agents | `parte-2/2.21-configuracion-comun-de-los-agentes.md` |

### Partie 03. Gestion des actifs et automatisation IT

| N° | Chapitre | Chemin |
| --- | --- | --- |
| 3.1 | Inventaire | `parte-3/3.1-inventario.md` |
| 3.2 | Contrôle à distance avec RC | `parte-3/3.2-control-remoto-con-rc.md` |
| 3.8 | Arrêts planifiés | `parte-3/3.8-paradas-planificadas.md` |

### Partie 04. Gestion des utilisateurs et des permissions

| N° | Chapitre | Chemin |
| --- | --- | --- |
| 4.1 | Groupes, utilisateurs, profils et tags | `parte-4/4.1-grupos-perfiles-y-tags.md` |
| 4.2 | Authentification externe et centralisation des accès | `parte-4/4.2-autenticacion-externa-y-centralizacion-de-accesos.md` |
| 4.3 | Sécurité et visibilité avancées (ACL avancée) | `parte-4/4.3-seguridad-y-visibilidad-avanzada-enterprise-acl.md` |
| 4.4 | Bonnes pratiques de noms et de tags | `parte-4/4.4-buenas-practicas-de-etiquetado-naming-tags.md` |

### Partie 05. Apporter de la valeur à la supervision

| N° | Chapitre | Chemin |
| --- | --- | --- |
| 5.4 | Console d'événements centralisée | `parte-5/5.4-consola-de-eventos-centralizada.md` |
| 5.5 | Alertes et notifications | `parte-5/5.5-alertas-y-notificaciones.md` |
| 5.8 | Gestion des incidents / ITSM | `parte-5/5.8-gestion-de-incidencias-itsm.md` |
| 5.11 | Cartes SIG | `parte-5/5.11-mapas-gis.md` |
| 5.12 | Application mobile | `parte-5/5.12-aplicacion-movil.md` |

### Partie 06. Évolutivité et environnements complexes

| N° | Chapitre | Chemin |
| --- | --- | --- |
| 6.1 | Architectures distribuées | `parte-6/6.1-arquitecturas-distribuidas.md` |
| 6.2 | Serveurs satellites | `parte-6/6.2-servidores-satelite.md` |
| 6.3 | Command Center | `parte-6/6.3-command-center.md` |
| 6.4 | Distribution et installation automatique des agents | `parte-6/6.4-distribucion-e-instalacion-automatica-de-agentes.md` |
| 6.5 | Base de données d'historique | `parte-6/6.5-base-de-datos-de-historico.md` |
| 6.7 | Optimisation de la base de données | `parte-6/6.7-optimizacion-de-la-base-de-datos.md` |
| 6.8 | Sauvegarde et restauration | `parte-6/6.8-backup-y-restore.md` |

### Partie 07. Sécurité et supervision

| N° | Chapitre | Chemin |
| --- | --- | --- |
| 7.2 | SIEM | `parte-7/7.2-siem.md` |
| 7.3 | SOAR | `parte-7/7.3-soar.md` |
| 7.4 | Analyse des vulnérabilités | `parte-7/7.4-analisis-de-vulnerabilidades.md` |
| 7.5 | Durcissement | `parte-7/7.5-hardening.md` |
| 7.6 | FIM | `parte-7/7.6-fim.md` |
| 7.7 | Supervision de la sécurité | `parte-7/7.7-monitorizacion-de-seguridad.md` |
| 7.10 | Conformité : NIS2, ISO 27001 et ENS | `parte-7/7.10-compliance-nis2-iso-27001-y-ens.md` |
| 7.11 | Configuration sécurisée | `parte-7/7.11-configuracion-segura.md` |

### Partie 08. Pandora AI

| N° | Chapitre | Chemin |
| --- | --- | --- |
| 8.1 | Introduction et installation | `parte-8/8.1-introduccion-e-instalacion.md` |
| 8.2 | Utilisation du chat | `parte-8/8.2-uso-del-chat.md` |
| 8.3 | Automatisation des tâches | `parte-8/8.3-automatizacion-de-tareas.md` |
| 8.4 | Sécurité | `parte-8/8.4-seguridad.md` |
| 8.5 | Audit | `parte-8/8.5-auditoria.md` |

### Partie 09. Autres aspects avancés de Pandora FMS

| N° | Chapitre | Chemin |
| --- | --- | --- |
| 9.1 | Référence complète de configuration de l'EndPoint | `parte-9/9.1-referencia-completa-de-configuracion-del-endpoint.md` |
| 9.2 | Référence complète de configuration de la console | `parte-9/9.2-referencia-completa-de-configuracion-de-la-consola.md` |
| 9.3 | Référence complète de configuration du serveur | `parte-9/9.3-referencia-completa-de-configuracion-del-servidor.md` |
| 9.4 | Référence complète de Tentacle (serveur et client) | `parte-9/9.4-referencia-completa-de-tentacle.md` |
| 9.5 | Chiffrement de la base de données | `parte-9/9.5-cifrado-de-la-base-de-datos.md` |
| 9.6 | Supervision des clusters | `parte-9/9.6-monitorizacion-de-clusters.md` |
| 9.7 | Création de plugins de discovery | `parte-9/9.7-creacion-de-plugins-de-discovery.md` |
| 9.11 | Référence complète du CLI d'administration (pandora_manage) | `parte-9/9.11-referencia-completa-del-cli-de-administracion.md` |
| 9.12 | Découverte automatique avancée : IPMI et tâches de reconnaissance personnalisées | `parte-9/9.12-descubrimiento-automatico-avanzado-ipmi-y-reconocimiento.md` |

### Partie 10. Base de données

| N° | Chapitre | Chemin |
| --- | --- | --- |
| 10.1 | Schéma de la base de données | `parte-10/10.1-esquema-de-la-base-de-datos.md` |
| 10.2 | Référence des tables | `parte-10/10.2-referencia-de-tablas.md` |

### Partie 11. Annexes techniques

| N° | Chapitre | Chemin |
| --- | --- | --- |
| A1 | Mise à jour des versions de PHP | `anexos/a1-actualizacion-de-versiones-de-php.md` |
| A2 | Glossaire des termes | `anexos/a2-glosario-de-terminos.md` |
| A3 | Compatibilité et migration vers la nouvelle architecture de serveurs | `anexos/a3-compatibilidad-y-migracion-a-la-nueva-arquitectura-de-servidores.md` |
| A4 | Étendre les assistants SNMP et WMI avec des composants propres | `anexos/a4-ampliar-los-asistentes-snmp-y-wmi-con-componentes-propios.md` |
| A5 | Configuration de fprobe pour Netflow | `anexos/a5-configuracion-de-fprobe-para-netflow.md` |
| A6 | Mise à jour de la LTS 777 vers la 800 | `anexos/a6-actualizacion-de-la-lts-777-a-la-800.md` |
| A7 | Guide de la documentation pour les agents IA | `anexos/a7-guia-de-la-documentacion-para-agentes-de-ia.md` |

### Partie 12. Questions fréquentes (FAQ)

| N° | Chapitre | Chemin |
| --- | --- | --- |
| 12.1 | Qu'est-ce que cette FAQ | `parte-12/12.1-que-es-este-faq.md` |
| 12.2 | Serveur et base de données | `parte-12/12.2-servidor-y-base-de-datos.md` |
| 12.3 | Agents et systèmes | `parte-12/12.3-agentes-y-sistemas.md` |
| 12.4 | Console web et licences | `parte-12/12.4-consola-web-y-licencias.md` |
| 12.5 | Modules et réseau | `parte-12/12.5-modulos-y-red.md` |
| 12.6 | Alertes et événements | `parte-12/12.6-alertas-y-eventos.md` |
| 12.7 | Rapports, logs et courrier | `parte-12/12.7-informes-logs-y-correo.md` |
| 12.8 | Grands environnements | `parte-12/12.8-entornos-grandes.md` |
| 12.9 | Automatisation et plugins | `parte-12/12.9-automatizacion-y-plugins.md` |
| 12.10 | Opérations massives | `parte-12/12.10-operaciones-masivas.md` |

### Partie 13. API v2

| N° | Chapitre | Chemin |
| --- | --- | --- |
| 13.1 | Premiers pas et authentification | `parte-13/13.1-primeros-pasos-y-autenticacion.md` |
| 13.2 | Conventions de l'API : pagination, filtres et erreurs | `parte-13/13.2-convenciones-de-la-api.md` |
| 13.3 | Exemples d'utilisation | `parte-13/13.3-ejemplos-de-uso.md` |
| 13.4 | API v2 endpoint reference | `parte-13/13.4-referencia-de-endpoints/index.md` |
| 13.4.1 | API v2 endpoints: Agents | `parte-13/13.4-referencia-de-endpoints/agents.md` |
| 13.4.2 | API v2 endpoints: Modules | `parte-13/13.4-referencia-de-endpoints/modules.md` |
| 13.4.3 | API v2 endpoints: Alerts | `parte-13/13.4-referencia-de-endpoints/alerts.md` |
| 13.4.4 | API v2 endpoints: Events | `parte-13/13.4-referencia-de-endpoints/events.md` |
| 13.4.5 | API v2 endpoints: Policies | `parte-13/13.4-referencia-de-endpoints/policies.md` |
| 13.4.6 | API v2 endpoints: Collections | `parte-13/13.4-referencia-de-endpoints/collections.md` |
| 13.4.7 | API v2 endpoints: Users and access | `parte-13/13.4-referencia-de-endpoints/users-and-access.md` |
| 13.4.8 | API v2 endpoints: Dashboards and notifications | `parte-13/13.4-referencia-de-endpoints/dashboards-and-notifications.md` |
| 13.4.9 | API v2 endpoints: Reports | `parte-13/13.4-referencia-de-endpoints/reports.md` |
| 13.4.10 | API v2 endpoints: Services and scheduled downtimes | `parte-13/13.4-referencia-de-endpoints/services-and-downtimes.md` |
| 13.4.11 | API v2 endpoints: Bulk operations and data | `parte-13/13.4-referencia-de-endpoints/bulk-operations-and-data.md` |
| 13.4.12 | API v2 endpoints: Security | `parte-13/13.4-referencia-de-endpoints/security.md` |
| 13.4.13 | API v2 endpoints: Pandora AI and ITSM | `parte-13/13.4-referencia-de-endpoints/ai-and-itsm.md` |
| 13.4.14 | API v2 endpoints: Network Configuration Manager | `parte-13/13.4-referencia-de-endpoints/ncm.md` |
| 13.4.15 | API v2 endpoints: RMM | `parte-13/13.4-referencia-de-endpoints/rmm.md` |
| 13.5 | CLI de l'API v2 (pandora-cli) | `parte-13/13.5-cli-de-la-api-v2-pandora-cli.md` |

## Si vous cherchez X, allez à Y

| Si vous cherchez | Aller à |
| --- | --- |
| Installer Pandora FMS | [1.1 Installation](../parte-1/1.1-instalacion.md) |
| Passer à une version plus récente | [1.4 Mises à jour](../parte-1/1.4-actualizaciones.md) |
| Versions LTS, stabilité et support | [1.3 Politique de versions et de support](../parte-1/1.3-versiones-y-estabilidad.md) |
| Licences et limites de la licence | [1.5 Licences](../parte-1/1.5-licenciamiento.md) |
| Surveiller un serveur avec un EndPoint | [2.1 Supervision avec des EndPoints](../parte-2/2.1-monitorizacion-con-endpoints.md) |
| Découvrir automatiquement les équipements du réseau | [2.4 Découverte réseau avec Host et appareils](../parte-2/2.4-descubrimiento-de-redes-con-host-y-dispositivos.md) |
| Surveiller les équipements réseau en SNMP | [2.6 Supervision des réseaux](../parte-2/2.6-monitorizacion-de-redes.md) |
| Recevoir des traps SNMP | [2.7 Supervision des traps SNMP](../parte-2/2.7-monitorizacion-de-traps-snmp.md) |
| Collecter et surveiller les logs | [2.19 Collecte et supervision des logs](../parte-2/2.19-recoleccion-y-monitorizacion-de-logs.md) |
| Configurer un module (intervalle, seuils) | [2.20 Configuration commune des modules](../parte-2/2.20-configuracion-comun-de-los-modulos.md) |
| Appliquer la même configuration à de nombreux agents | [2.10 Politiques de supervision](../parte-2/2.10-politicas-de-monitorizacion.md) |
| Créer des alertes et des notifications | [5.5 Alertes et notifications](../parte-5/5.5-alertas-y-notificaciones.md) |
| Consulter et gérer les événements | [5.4 Console d'événements centralisée](../parte-5/5.4-consola-de-eventos-centralizada.md) |
| Utilisateurs, groupes et permissions | [4.1 Groupes, utilisateurs, profils et tags](../parte-4/4.1-grupos-perfiles-y-tags.md) |
| Se connecter avec LDAP, Active Directory ou SAML | [4.2 Authentification externe et centralisation des accès](../parte-4/4.2-autenticacion-externa-y-centralizacion-de-accesos.md) |
| Répartir Pandora FMS sur plusieurs serveurs | [6.1 Architectures distribuées](../parte-6/6.1-arquitecturas-distribuidas.md) |
| Gérer plusieurs installations depuis une seule console | [6.3 Command Center](../parte-6/6.3-command-center.md) |
| Optimiser ou nettoyer la base de données | [6.7 Optimisation de la base de données](../parte-6/6.7-optimizacion-de-la-base-de-datos.md) |
| Sauvegarde et restauration | [6.8 Sauvegarde et restauration](../parte-6/6.8-backup-y-restore.md) |
| Collecter et corréler les événements de sécurité (SIEM) | [7.2 SIEM](../parte-7/7.2-siem.md) |
| Utiliser le chat de Pandora AI | [8.2 Utilisation du chat](../parte-8/8.2-uso-del-chat.md) |
| Paramètres du fichier de configuration de l'EndPoint | [9.1 Référence complète de configuration de l'EndPoint](../parte-9/9.1-referencia-completa-de-configuracion-del-endpoint.md) |
| Paramètres de configuration de la console | [9.2 Référence complète de configuration de la console](../parte-9/9.2-referencia-completa-de-configuracion-de-la-consola.md) |
| Paramètres de configuration du serveur | [9.3 Référence complète de configuration du serveur](../parte-9/9.3-referencia-completa-de-configuracion-del-servidor.md) |
| Structure de la base de données | [10.1 Schéma de la base de données](../parte-10/10.1-esquema-de-la-base-de-datos.md) |
| Questions fréquentes et problèmes courants | [12.1 Qu'est-ce que cette FAQ](../parte-12/12.1-que-es-este-faq.md) |
| Sens d'un terme (y compris les anciens noms) | [A2 Glossaire des termes](../anexos/a2-glosario-de-terminos.md) |
| Passer de la LTS 777 à la 800 | [A6 Mise à jour de la LTS 777 vers la 800](../anexos/a6-actualizacion-de-la-lts-777-a-la-800.md) |
| Appeler l'API v2 depuis un script ou un agent | [13.1 Premiers pas et authentification](../parte-13/13.1-primeros-pasos-y-autenticacion.md) |
| Paginer, filtrer et comprendre les erreurs de l'API v2 | [13.2 Conventions de l'API : pagination, filtres et erreurs](../parte-13/13.2-convenciones-de-la-api.md) |
| Exemples d'appels à l'API v2 | [13.3 Exemples d'utilisation](../parte-13/13.3-ejemplos-de-uso.md) |
| Trouver un endpoint de l'API v2 (paramètres, champs et erreurs) | [13.4 API v2 endpoint reference](../parte-13/13.4-referencia-de-endpoints/index.md) |

## Conventions que l'agent doit respecter

| Règle | Détail |
| --- | --- |
| Terminologie | Toujours utiliser le terme canonique du tableau ci-dessous ; anciens noms et synonymes dans le glossaire ([A2](a2-glosario-de-terminos.md)) |
| Identifiants du code | Ni traduits ni renommés : tables, jetons, fichiers et clés sont cités tels quels |
| Intégrations (plugins) | Pointer vers `https://pandorafms.com/docs/integrations/latest/<langue>/` ; ne pas citer le dépôt |
| Captures d'écran | Console en anglais dans les trois éditions |
| API v2 d'une console | La spécification exacte de sa version se trouve à `<console>/api/v2/swagger.json` et son Swagger UI à `<console>/api/documentation/` ; la référence du manuel est celle de la version publiée |
| Langue de la réponse | Celle de l'utilisateur ; ouvrir l'édition dans cette langue |

| Terme canonique |
| --- |
| RMM |
| paquete .disco |
| Ajuste fino |
| Versión LTS |
| EndPoint |
| Pandora ONE |
| Pandora NMS |
| Pandora RMM |
| Pandora SIEM |
| Pandora RC |
| Pandora ITSM |
| Command Center |
| cifrado |
| script |
| kernel panic |
| Pandora AI |
| el asistente |
| pandora-cli |

## Comment chercher

| Étape | Action |
| --- | --- |
| 1 | Chercher la question dans « Si vous cherchez X, allez à Y » |
| 2 | Sinon, chercher par titre dans l'index de l'édition (`llms.txt`) |
| 3 | Si cela ne suffit pas, chercher dans `search/search_index.<langue>.json` de la version |
| 4 | Ouvrir le chapitre et trouver la section par son titre |
| 5 | Si la réponse n'y est pas, le dire ; ne pas l'inventer |

## Ce que la documentation ne couvre pas

### Chapitres encore à rédiger (ne pas les lire : ils n'ont pas de contenu)

| N° | Chapitre |
| --- | --- |
| 3.3 | Distribution automatique de logiciels |
| 3.4 | Exécution à distance de scripts et de commandes |
| 3.5 | Mise à jour corrective des systèmes |
| 3.6 | Gestion de configuration des équipements réseau (NCM) |
| 3.7 | Gestion des IP (IPAM) |
| 3.9 | Intégration des actifs avec l'ITSM |
| 5.1 | Tableaux de bord |
| 5.2 | Rapports |
| 5.3 | Supervision métier et de services |
| 5.6 | Consoles visuelles |
| 5.7 | Cartes topologiques du réseau |
| 5.9 | Analyse prédictive et capacity planning |
| 6.6 | Mécanismes d'auto-approvisionnement |
| 6.9 | Haute disponibilité (HA) |
| 7.1 | Architecture de sécurité de Pandora |
| 7.8 | Audit interne |
| 7.9 | Intégrations dynamiques d'IoC (MISP) et création de règles propres |
| 9.8 | Création de plugins locaux |
| 9.9 | Création de plugins distants |
| 9.10 | Création d'extensions de console |
| 9.13 | Dépannage avec Pandora |
| 9.14 | Analyse volumétrique et conceptions pour la haute capacité |
