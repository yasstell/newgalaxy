---
title: Héberger un gestionnaire de mot de passe sur son NAS Synology
date: 2021-08-01 14:00:00 +0800
categories: [Sécurité]
tags: [synology, password, keeweb]
image:
  src: /img/password_manager.jpg
  width: 800
  height: 500
---
Il existe plusieurs applications qui proposent de stocker les mots de passe et d'y accéder depuis n'importe quel appareil. L'intérêt de ces services est de simplifier la gestion des mots de passe puisqu'il vous sera demandé de retenir un seul mot de passe "maître" permattant d'accéder au service. Par contre, si comme moi, vous préférez garder le contrôle de vos données sensibles et de ne pas les confier à des services en ligne qui fonctionnent sur le clould alors il existe des solutions pour héberger soit même ses mots de passe.

Il existe plusieurs applications compatible avec l'auto-hergement mais pour ma part je prefère l'application "keeweb". Il s'agit d'une application open source qui peut être exécuté sur navigateur ou via un logiciel de bureau. Cette application permet de gérer des mots de passe de manière simple. La base de données des mots de passe est quant à elle stocké sous un format compatible avec keepass.

A noter que le principe que j'explique dans cet article s'applique à n'importe quelle application qui supporte la lecture d'un fichier dans le réseau local.

## Client desktop
Dans un premier temps je vous propose de nous intérsser à l'application qui va jouer le rôle de client. Ce client permettra d'afficher la liste des mots de passe disponible mais également d'en créer des nouveaux quand c'est nécessaire.
Vous pouvez télécharger le client compatible avec votre système d'exploitation via cette adresse : <https://keeweb.info/>

![Desktop View](/img/keeweb_open_file.PNG)

La première étape consiste à créer un nouveau fichier en cliquant sur le bouton "+". Ensuite vous pouvez commencer à ajouter vos mots de passe en cliquant sur le bouton "+" à côté de la barre de recherche. Vous aurez alors une liste déroulante qui permet d'ajouter une nouvelle entrée, un groupe ou un template. Pour ajouter un nouveau mot de passe il suffit de cliquer sur "entrée". Vous pouvez alors répéter ces étapes pour ajouter autant de mots de passe que nécessaire.

L'application dispose de plusieurs fonctionnalité qui facilitent l'organisation des mots de passe (groupement des mots de passe, utilisation d'un code couleur ...). Elle permet également de générer des mots de passe aléatoire en fonction des critères définis par l'utlisateur (nomre de caractères, présence de chiffres, présence de caractères spéciaux ...). Pour des raisons de sécurité il est toujours recommandé de choisir un mot de passe complexe avec le plus de caractères possible.

![Desktop View](/img/keeweb_new_entry.PNG)

## Hébergement du fichier de mots de passe sur le NAS
Le gestionnaire "keeweb" stocke les mots de passe dans un fichier local ayant l'extension kdbx. Une fois que vous aurez ajouté vos mots de passe dans l'outil vous allez pouvoir déplacer le fichier pour le stocker sur votre NAS. Ainsi le fichier kdbx reste stocké uniquement sur votre NAS en toute sécurité. Pour réaliser cette étape il suffit de cliquer sur "new" en bas à gauche de l'application. Vous serez alors redirigé vers une nouvelle fenêtre qui permet d'nregistrer le fichier en cliquant sur le bouton "Save to ..."

![Desktop View](/img/keeweb_save_file.PNG)

Pour accéder à nouveau à ces mots de passe via "keeweb" alors vous auez besoin d'ouvrir le fichier distant depuis grâce au bouton "ouvrir" dans l'écran principal. Une fois que vous aurez sélectionné le fichier alors il ne vous reste plus qu'à saisir le mot de passe "maître" pour déverouiller le fichier.

## Client mobile
Sur mobile il n'existe pas d'application officielle dans les stores. Mais il existe une alternative qui permet tout de même d'utiliser le gestionnaire de mots de passe "keeweb". Il s'agit d'une webapp accessible via navigateur et qui permet de charger "keeweb" sans avoir à l'installer. Ainsi on dispose de toutes les fonctionnalités expliqués précédémment dans la rubrique desktop. Vous pouvez y accéder via cette adresse : <https://app.keeweb.info/>

Pour profiter pleinement de cette solution vous aurez besoin d'un moyen pour accéder à distance à votre NAS. Ainsi vous pourrez récupérer vos mots de passe sans être à domicile. Pour avoir un tel accès j'utilise pour ma part un VPN personnel qui relie mon smartphone à mon NAS. J'écrirai un article dédié pour vous expliquez comment accéder à votre NAS via VPN.
