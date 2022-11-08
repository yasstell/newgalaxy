---
title: Partager facilement des fichiers en WiFi avec LANDROP
date: 2021-07-18 14:00:00 +0800
categories: [LAN]
tags: [lan, landrop]
image:
  src: /img/file_transfer_landrop.jpg
  width: 800
  height: 500
---

## Pourquoi LANDrop ?

Lorsqu'on a besoin de transférer des fichiers entre deux appareils connectés au même réseau local on opte souvent pour l'une de ces deux solutions :
- Transférer les fichiers par câble lorsqu'il s'agit d'un transfert entre mobile et PC. Mais lorsqu'il s'agit de deux mobiles alors cette solution est exclue.
- Transférer les fichiers via bleutooth à condition que les fichiers ne soient pas trop volumineux puisque la vitesse de transfert est très lente. Cette limitation rend le bleutooth très peu adapté car la taille des fichiers (et notamment des photos) ne cessent d'augmenter avec le temps. En plus cette solution suppose d'activer le bleutooth sur les deux appareils (chose qui n'est pas souvent activée contrairement au WiFi ) et préparer l'appareil destinataire pour recevoir les fichiers.
- Transférer les fichiers via des services de mail ou de messagerie en ligne. Il s'agit sans doute de la solution la plus simple est la plus largement utilisée. Mais si comme moi vous ne souhaitez pas que les géants du web s'emparent stockent ces données dans le cloud alors ce n'est pas la solution à retenir. Sans parler de l'impact écologique de ces transferts ponctuels puisque nos boîtes mail et nos messageries sont remplis de messages qui deviennent inutiles après la réception et téléchargement des fichiers.

Il existe pourtant une solution simple qui allie la rapidité du réseau WiFi et la sécurité des données. Il s'agit de l'application LANDrop : une application open source disponible sur plusieurs plateformes (android, ios, windows, macos et linux) et qui permet de faire du transfert peer to peer entre l'appareil émetteur et l'appareil destinataire sans sortir du réseau local. Pour en savoir plus voici le site de l'application : <https://landrop.app/>

Pour illustrer un cas pratique je vais prendre l'exemple d'un transfert depuis un mobile vers un PC sous windows. Le principe que j'explique dans cet article fonctionne également dans lorsqu'il s'agit d'autres appareils (par exemple : transfert entre deux smartphones).

## Application mobile

Pour faire un transfert depuis l'application sur mobile, il suffit de lancer l'application et de sélectionner le ou les fichiers à envoyer. On peut réaliser cette sélection en cliquant sur le bouton en haut à droite de l'application. Ensuite il suffit de sélectionner l'appareil destinataire depuis la liste "Devices". Dans l'exemple que je montre ci-dessous il s'agit de l'appareil "PC".

En effet, l'application va scanner automatiquement le réseau à la recherche d'appareils disposant de LANDrop pour les afficher dans la liste "Devices". Vous devriez donc trouver dans cette liste votre appareil vers lequel le transfert est destiné. Sinon assurez vous que l'application est bien lancée dans l'appareil cible.

![Desktop View](/img/landrop_mobile.PNG)

A noter que le transfert est protégé via un code. Il est donc nécessaire de confirmer le code de sécurité dans l'apparreil cible avant de poursuivre le transfert des fichiers. Voici un aperçu de la fenêtre de confirmation du code sur PC.

![Desktop View](/img/landrop_code.PNG)


## Application PC

La procédure est similaire sur PC. Après avoir lancé l'application il suffit de cliquer sur le bouton "Add.." pour sélectionner le ou les fichiers à transférer. Ensuite il faudra cliquer sur le bouton "Send" pour sélectionner l'appareil destinataire.

![Desktop View](/img/landrop_pc.PNG)
