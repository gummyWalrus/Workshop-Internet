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
3. Faites de meme pour l'autre site web

# Docker-compose

docker-compose est un orchestrateur de container permettant de démarrer vos containers en définissant des réseaux de containers qui leurs permettront de communiquer entre eux

1. Définissez un docker-compose chargé de démarrer l'image du premier site "fedora 42" en ouvrant les bons ports sur votre machine
2. Faites de meme pour l'autre site web

# Traefik

Traefik est un "loadbalancer" et un "reverse-proxy".

Les loadbalancer permettent d'équilibrer les requetes clients entre différentes addresses IP de votre infrastructure pour optimiser la charge appliqué à vos machines, nous n'utiliserons pas cette fonctionnalités mais sachez qu'elle existe et qu'elle est utilisée dans toutes infrastructures comportant plusieurs serveurs chargés d'assurer le fonctionnement d'un meme service.

Les reverse-proxy permettent de faire pointer des noms de domaines différents vers des ports spécifiques de votre machine ils permettent d'avoir plusieurs sites web sur une meme IP sans que les utilisateurs soient obligés de spécifier un port auquel se connecter

1. Définissez des noms de domaines différents pointant tout les deux vers votre IP dans le fichier /etc/hosts
2. Modifiez vos docker-compose pour y ajouter des labels qui permettront a traefik de retrouver vos containers et de savoir quel nom de domaine correspond a votre site ainsi que d'y assurer le bon fonctionnement du protocole HTTPS.
3. Démarrez une instance de traefik chargés de faire correspondre les noms de domaines et de rafraichir les certificats SSL de ceux-ci

# POG !!!

Après quelques minutes, vos sites web devraient etre accessible en HTTPS via les noms de domaines que vous leur avez associés. Félicitations, vous avez compris les bases de Docker, docker-compose et du pointage DNS ainsi que l'un de leur cas d'utilisation dans l'hébergement web.
