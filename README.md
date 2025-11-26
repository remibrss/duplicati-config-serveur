# 📘 README — Service Duplicati (Sauvegardes) — Classe SISR

## 📌 Présentation
Duplicati est un service de sauvegarde permettant de protéger les données du serveur grâce à des sauvegardes chiffrées et automatisées.  
Dans le cadre de la classe SISR, il sera intégré dans le **docker-compose global**, aux côtés d’autres conteneurs pédagogiques.

Ce service permet d’assurer la sauvegarde régulière de répertoires importants, tels que `/home`, vers un espace dédié sur le serveur.

---

## 🏗️ Description du service

Le service Duplicati utilise l’image officielle LinuxServer.io et est configuré pour :

- proposer une interface web accessible sur le port **8200**,  
- stocker la configuration dans un répertoire dédié (`/var/duplicati/config`),  
- enregistrer les sauvegardes dans `/var/duplicati/backups`,  
- accéder au dossier `/home` du serveur afin de l’inclure dans les sauvegardes,  
- utiliser un mot de passe administrateur défini dans les variables d’environnement,  
- protéger les paramètres internes grâce à une clé de chiffrement,  
- redémarrer automatiquement en cas d'arrêt du conteneur.

---

## 🔐 Sécurité

- L’accès à l’interface web est sécurisé par un mot de passe administrateur.  
- Une clé de chiffrement protège la configuration interne du service.  
- Les sauvegardes et la configuration sont isolées dans des volumes dédiés pour éviter les risques de perte de données.

---

## 📘 Intégration dans le docker-compose de la classe

Ce service sera intégré au **fichier docker-compose commun de la classe**, aux côtés d’autres services tels que les serveurs web, bases de données, outils d’administration ou plateformes pédagogiques.  
Cette intégration permet à l’ensemble de l’infrastructure d’être cohérente, centralisée et facilement déployable, tout en illustrant la mise en place réelle d’une solution de sauvegarde au sein d’un environnement Docker.
