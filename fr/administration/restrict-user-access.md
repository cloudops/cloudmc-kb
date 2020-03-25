---
title: "Restreindre l'accès aux utilisateurs"
slug: restreindre-l-acces-aux-utilisateurs
---


Les rôles assignés à un utilisateur déterminent les fonctionalités qui lui seront offertes. Un rôle consiste en un ensemble de permissions parmis celles offertes dans le système. Par exemple, la permission **Ajouter utilisateur** fait partie du rôle **Org. Admin**, mais pas du rôle **End User**. Conséquemment, seul un utilisateur possédant le rôle **Org. Admin** est autorisé à ajouter de nouveaux utilisateurs au sein de son organisation.

Pour vérifier votre/vos rôles actuels, procédez comme suit:

- Dans le menu correspondant à votre nom d’utilisateur (dans la barre de menu), sélectionnez Préférences et consultez la valeur de l’item Rôle système.

Par défaut il y a deux rôles pré-configurés (**Org. Admin** et **End-user**), que vous pouvez renommer à votre guise (par exemple si tous vos utilisateurs sont francophones). Si vous avez besoin de davantage de granularité au niveau du modèle de sécurité, vous pouvez créer de nouveaux rôles en utilisant n’importe quelle combinaison de permissions. Vous pouvez ensuite sélectionner les rôles appropriés pour chacun de vos utilisateurs, où le résultat effectif sera l’union des permissions des rôles choisis.

Pour se prémunir contre les élévations de privilèges, un utilisateur possédant la permission *Modifier utilisateur* n’a que le droit d’assigner à autrui les roles qu’il possède lui-même.
