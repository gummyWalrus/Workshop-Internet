# Workshop sur Internet

Le but de ce workshop est de déployer plusieurs sites web sur une meme machine et de les différencier sur internet via un nom de domaine

Cette expérience permet de réaliser les différents composants qui mène un site à etre disponible sur internet et par là, de découvrir le fonctionnement d'internet

1. Dans ce repo vous trouverez 2 sources de sites web à déployer l'un écoute le port 8000 l'autre le port 8080
2. Vous utiliserez docker pour déployer les 2 sites dans des environnements virtuels respectifs
3. Vous utiliserez l'orchestrateur docker-compose pour démarrer ces environnements (ou containers) dans un réseau partagé
4. Vous configurerez une instance de traefik pour résoudre des noms de domaines et les faire pointer sur vos deux sites web
5. Vous utiliserez traefik pour génerer automatiquement des certificats SSL et activer le HTTPS sur votre site

Seul [docker](https://docs.docker.com/get-started/overview/) et [docker-compose](https://docs.docker.com/compose/) sont requis pour débuter ce workshop. Installez les en suivant la [doc d'installation](https://docs.docker.com/get-docker/).

# Docker

Docker est un puissant outil pour créer des environnements virtuels (containers) rapidement.

1. Définissez un Dockerfile capable de construire une image qui déployerais le premier site "fedora 42"
2. Démarrez le sur votre machine et essayez d'y accéder
3. Faites de meme pour votre 
