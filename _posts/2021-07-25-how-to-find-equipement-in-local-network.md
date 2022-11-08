---
title: Comment trouver l'adresse IP de son NAS Synology
date: 2021-07-25 14:00:00 +0800
categories: [Synology]
tags: [synology, ip]
image:
  src: /img/nas_network.jpg
  width: 800
  height: 500
---
Dans cet article je vous expliquerai comment trouver facilement l'adresse IP de votre NAS dans votre réseau local.
Il s'agit d'une procédure très utile lorsqu'on a oublié l'adresse IP de son NAS dans le réseau local.
On peut également en avoir besoin suite à un changement des adresses IP dans son réseau local. Cela peut se produire par exemple lorsqu'on réintialise son routeur ou lorsqu'on change d'opérateur.

## L'assistant en ligne
La première solution consiste à lancer le site mis à disposition par Synology à cet effet.
Ce site est accessible via ce lien : <http://find.synology.com>
La recherche de NAS se lance instantanément pour trouver le NAS dans le réseau local.

Il arrive parfois que le site de Synology ne détecte pas le NAS. Vous aurez alors un message comme celui affiché dans la copie d'écran ci-dessous.
Dans ce cas je vous propose de passer à l'étape suivante.
![Desktop View](/img/synology_not_found_nas.PNG)

## L'outil Synology Assistant
La deuxième option consiste à utiliser l'outil Synology Assistant. Cet outil est disponible via le centre de téléchargement de Synology : <https://www.synology.com/fr-fr/support/download>

Une fois installé, il suffit de cliquer sur "recherche" pour que l'outil scanne le réseau local à la recherche de votre NAS. Le résultat devrait ressembler à la copie d'écran ci-dessous.
![Desktop View](/img/synology_assistant_found_nas.PNG)

## Un outil de scan réseau
La troisième solution consiste à utiliser une application qui peut scanner le réseau local pour lister l'ensemble des équipements connectés.
Plusieurs applications disponibles sur les stores peuvent répondre à ce besoin mais mon application préférée dans cette catégorie est "Fing".
L'application est simple à utiliser et ne nécessite pas la création d'un compte.

Voici les liens pour télécharger l'application sur les stores :
- Pour android : <https://play.google.com/store/apps/details?id=com.overlook.android.fing&hl=fr>
- Pour iOS : <https://apps.apple.com/fr/app/fing-scanner-r%C3%A9seau/id430921107>

Après avoir scanné le réseau local via Fing il ne vous reste plus qu'à identifier votre NAS parmi tous les appareils trouvés. Le résultat devrait ressembler à la copie d'écran ci-dessous.
![Desktop View](/img/fing_found_nas.jpg)

## Se connecter à l'interface d'administration
Maintenant que vous avez trouvé l'adresse ip de votre NAS il ne vous reste plus quà se connecter à l'interface d'administration via le lien <http://ADRESSE_IP_NAS:5000> ou <https://ADRESSE_IP_NAS:5001> si vous avez sécurisé l'interface avec un certificat https.
