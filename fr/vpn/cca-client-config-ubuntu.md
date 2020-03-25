---
title: "Configuration Client :  Ubuntu 18.04"
slug: cca-config-client-ubuntu
---


Ce guide va vous aider à configurer l'accès VPN à distance sur Ubuntu en utilisant le *network manager*, qui est installé par défaut dans la version desktop.

1. Installer les paquets requises :
   - `apt-get install strongswan network-manager-strongswan libcharon-extra-plugins`
1. Ouvrir l'application *Paramètres*, aller à l'onglet *Réseau* à gauche.
1. Cliquer sur **+** à côté de *VPN*.
1. Sélectionner **IPsec/IKEv2 (strongswan)** comme type de VPN.

![Sélection de VPN](/assets/Lx-1-Strongswan.png)

5. Naviguer à l'onglet *Identity*.
5. Donner un nom à la connexion VPN, par exemple: **cloudca-vpn**
5. Dans *Gateway*, le champ *Address* est l'IP publique fournie dans la page de configuration du VPN, et *Certificat* est le certificat fourni dans la page de configuration du VPN.
5. Dans *Client*, mettre *Authentication* à *EAP*.
5. Renseigner les champs *Username* et *Password*.
5. Dans *Options*, cocher la case **Request an inner IP address**.

![Page de configuration du VPN](/assets/Lx-2-Request-internal.png)

11. Si vous le souhaitez, vous pouvez naviguer sur l'onglet *IPv4*, et cocher **Use this connection only for resources on its network**.
11. Cliquer sur *Add* en haut à droite de la fenêtre pour sauvegarder la configuration.


Vous pouvez maintenant activer le VPN depuis la page *Network* ou depuis le widget en haut à droit de l'écran.
