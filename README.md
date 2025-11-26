# Service Duplicati

## Vue d'ensemble

Duplicati est une solution de sauvegarde chiffrée et automatisée déployée dans un environnement Docker. Elle assure la protection régulière des données critiques via des sauvegardes sécurisées et isolées.

## Fonctionnalités

Le service Duplicati (image LinuxServer.io) offre :

- Interface web de gestion accessible sur le port **8200**
- Sauvegarde automatisée et chiffrée des répertoires importants
- Stockage isolé de la configuration et des sauvegardes en volumes dédiés
- Authentification par mot de passe administrateur
- Clé de chiffrement pour la sécurisation des paramètres internes
- Redémarrage automatique en cas d'indisponibilité

## Architecture

| Composant | Détails |
|-----------|---------|
| **Image** | LinuxServer.io - Duplicati |
| **Port** | 8200 |
| **Volumes** | Configuration, sauvegardes, répertoire `/home` |
| **Sécurité** | Authentification, chiffrement des données |
| **Persistance** | Volumes dédiés pour les sauvegardes et la configuration |

## Installation et déploiement

### Démarrage du service

Le service Duplicati est fourni dans le fichier `docker-compose.yml` et peut être lancé facilement :

```bash
docker compose up -d
```

Cette commande démarre le conteneur Duplicati ainsi que tous les autres services définis dans la composition Docker.

### Accès à l'interface

Une fois le service actif, l'interface de gestion est accessible via :

```
http://37.64.159.66:8200
```

## Sécurité

- **Authentification** : L'accès à l'interface web est protégé par un mot de passe administrateur
- **Chiffrement** : Une clé de chiffrement sécurise la configuration interne
- **Isolation** : Les données sont stockées dans des volumes Docker isolés et persistants

## Intégration infrastructure

Ce service s'intègre dans une architecture Docker multi-conteneurs aux côtés d'autres services (serveurs web, bases de données, outils d'administration). Cette approche garantit une infrastructure cohérente, centralisée et facilement déployable pour l'environnement pédagogique SISR.
