---
title: "Configurer la répartition de charge"
slug: configurer-la-repartition-de-charge
---


La répartition de charge permet de distribuer les requêtes entrantes sur plusieurs ressources de calcul. Ceci permet d'améliorer la performance ainsi que la disponibilité à travers un niveau de redondance. Dans le contexte de cloud.ca, cet objectif est réalisé en associant des règles de répartition de charge à une adresse IP publique d'un VPC.

Note: il n'est pas possible de configurer des règles de répartition de charge sur une adresse IP publique qui est déjà utilisée à des fins de NAT source, VPN ou redirection de port. De plus, un seul tiers au sein d'un VPC peut avoir des adresses IP pour des fins de répartition de charge.

Dans l'example suivant, nous allons mettre en place un répartition de charge sur le traffic HTTP (port TCP 80), pour les instances web1 et web2 en utilisant un algorithme d'ordonnancement en tourniquet.

Aller à la page de Services
Sélectionnez l'environnement approprié dans la barre de navigation de gauche.
Choisissez l'onglet de réseautage.
A partir du VPC cible, cliquez sur le bouton IP publiques.
Cliquez sur le bouton Acquérir une adresse IP.




Ajoutez une règle de répartition de charge à l'adresse IP nouvellement acquise:




Nommez votre règle. spécifiez le port TCP pour la répartition de charge et sélectionnez le tier contenant les instances cibles:


Sélectionnez l'algorithme de répartition désiré. Dans cet exemple, nous ne spécifions aucune méthode de persistance et nous ciblons le protocole TCP:




Sélectionnez ensuite les instances sur lesquelles vous voulez répartir le traffic puis cliquez sur Terminer:


Le système confirmera la création de la nouvelle règle:


Cliquez le lien Adresses IP Publiques dans la piste de navigation et validez la bonne création de la règle de répartition de charge:


Finalement, validez le bon fonctionnement de la règle de répartition en laissant rouler du trafic et en vérifiant que chaque instance sert une part égale des requêtes. Une façon d'effectuer cela est de forcer chaque serveur à retourner un réponse légèrement différente (ex.: le nom de l'hôte) dans sa réponse (ou dans les entêtes de réponse).
