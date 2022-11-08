---
title: Créer un VPN sur son NAS Synology
date: 2021-10-09 14:00:00 +0800
categories: [Synology]
tags: [synology, vpn, l2tp, ipsec]
image:
  src: /img/vpn.jpg
  width: 800
  height: 500
---

Pour mettre en place le serveur VPN sur mon NAS Synology je me suis beaucoup inspiré du guide ci-dessous posté sur un célèbre forum de discussion autour des NAS. Le guide décrit de manière détaillé les étapes à suivre de l'installation du paquet sur le NAS jusqu'à la configuration du VPN client sur mobile. Ce guide traite également la question de la configuration du routeur qui est indipensable pour laisser passer le trafic VPN. Je recommande fortement de suivre scrupuleusement ce tutoriel :
<https://www.nas-forum.com/forum/topic/53328-tuto-vpn-server/>

Pour ma part j'ai installé le VPN L2TP/IPSec qui combine sécurité et facilité d'installation tout en étant compatible avec les mobiles. Mais vous êtes libre de choisir une autre solution si nécessaire du moment qu'il ne s'agit pas du PPTP.
