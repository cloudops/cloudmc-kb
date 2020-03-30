---
title: "Gestion des modèles"
slug: gestion-des-modeles
---


### Créer un modèle à partir d'une instance existante

Cette section présente comment créer un modèle à partir d'une instance existante en production sur cloud.ca. Ce processus requiert d'abord qu'une copie instantanée du volume soit effectuée.

#### Effectuer une copie instantanée initiale d'un volume

Dans la section **Volume**, localisez l'instance dont vous voulez dérivez un modèle. Notez que ce processus ne fonctionne que pour une Volume Principal (ROOT). Disons que pour cette exemple, nous utiliserons l'instance *preprod-mysql-node01*.

![Liste de volumes](/assets/working-with-instance-templates-fr-1.png)

Sélectionnez le volume principal de l'instance et cliquez ensuite sur le bouton Action. Sélectionnez l'option **Prendre une copie instantanée** et cliquez sur **Confirmer** dans la fenêtre contextuelle. Un message va confirmer que la tâche est en cours. Ce processus peut prendre un certain temps dépendent de la taille de l'instance.

![Prendre une copie instantanée](/assets/working-with-instance-templates-fr-2.png) <br><br>
![Copie instantanée en création](/assets/working-with-instance-templates-fr-3.png)

#### Créer votre modèle

Maintenant, déplacez vous dans la table **Snapshot**. Vous devriez voir votre copie instantanée pour votre volume ainsi que son statut à **Sauvegarder**.

![Liste de copies instantanées](/assets/working-with-instance-templates-fr-4.png)

Sélectionnez votre copie instantanée et cliquez sur **Action**. Ensuite, cliquez sur **Créer un modèle**. Une nouvelle fenêtre va apparaître comme dans l'exemple ci-bas.

![Créer un modèle](/assets/working-with-instance-templates-fr-5.png)

Ensuite, il faut simplement remplir le contenu des champs requis suivants :

- **Nom :** Ceci est le nom qui sera affiché dans la liste des modèles et dans l'outils de création d'instance.
- **Description :** Vous pouvez ajouter plus d'informations dans ce champ.
- **Système d'exploitation :** Ce champ est populé automatiquement basé sur le système d'exploitation de l'instance initiale. Il y a peu de chance que vous deviez changer cette valeur.
- **Options :** Il y a 3 options pour votre modèle.
   - *Clé SSH activé* : Ceci veut dire que votre modèle est capable de manipuler les clé SSH avec un script personnalisé ou cloud-init.
   - *Mot de passe activé* : Ceci veut dire que votre modèle est capable de configurer le mot de passe de l'usager root avec un mot de passe généré par le système lors du premier démarrage. Là également, vous avez besoin d'un script ou de cloud-init pour que cela fonctionne.
   - *Extensible dynamiquement* : Cela veut dire que votre modèle possède les outils XenServer et peut supporter un rehaussement de l'offre de service de calcul sans redémarrer votre instance. Il existe toutefois des limitations. Vous pouvez rehausser le niveau une seule fois et pouvez seulement doubler la capacité de CPU/Mémoire basé sur l'offre de calcul initiale.

Cliquez sur **Terminer**. Vous devriez recevoir un message de confirmation que le processus est en cours. Encore une fois, ce processus peut prendre quelques minutes dépendent de la grandeur du disque de l'instance. Une fois complété, vous verrez votre modèle apparaître dans la liste sous la section Modèle ainsi que dans l'outil de création d'instance.

### Importer son propre modèle

cloud.ca offre la possibilité aux usagers d'importer leurs propres modèles créés à l'extérieur de la plateforme. Ce processus est décrit dans cette section.

Premièrement, vous devez cliquez sur le bouton **Importer**. Une nouvelle fenêtre contextuelle va apparaître comme dans l'image suivante.

![Importer un modèle](/assets/working-with-instance-templates-fr-6.png)

Tous les champs sont obligatoires. Voici une description de chacun d'eux :

- **Nom :** Ceci est le nom qui sera affiché dans la liste des modèles et dans l'outils de création d'instance.
- **Description :** Vous pouvez ajouter plus d'informations dans ce champs.
- **URL d'imporation :** Vous ne téléverser pas des modèles vers cloud.ca, cloud.ca va le télécharger pour vous. Dans cette optique, vous devez fournir un **URL accessible publiquement** vers votre VHD en utilisant soit **HTTP** ou **FTP**. **Notez:** HTTPS ne fonctionnera pas.
- **Hyperviseur :** Ceci sera toujours XenServer dans notre cas, du moins pour le moment.
- **Format :** Ceci sera toujours VHD dans notre cas, du moins pour le moment.
- **Système d'exploitation :** Fournir le type de système d'exploitation pour votre modèle. Par exemple, si vous avez installé Ubuntu 14.04 avec PVHVM, vous devrez selectionner **Other (64 bit)**. Si vous avez installé CentOS 6 en PV, vous devrez utiliser **CentOS 6.4 (64 bit)**. Une table est disponible plus bas pour facilité votre choix.
- **Options :** Il y a 3 options pour votre modèle.
   - *Clé SSH activé* : Ceci veut dire que votre modèle est capable de manipuler les clé SSH avec un script personnalisé ou cloud-init.
   - *Mot de passe activé* : Ceci veut dire que votre modèle est capable de configurer le mot de passe de l'usager root avec un mot de passe généré par le système lors du premier démarrage. Là également, vous avez besoin d'un script ou de cloud-init pour que cela fonctionne.
   - *Extensible dynamiquement* : Cela veut dire que votre modèle possède les outils XenServer et peut supporter un rehaussement de l'offre de service de calcul sans redémarrer votre instance. Il existe toutefois des limitations. Vous pouvez rehausser le niveau une seule fois et pouvez seulement doubler la capacité de CPU/Mémoire basé sur l'offre de calcul initiale.

### Concordance des systèmes d'exploitation

| Système d'exploitation du modèle | Système d'exploitation pour cloud.ca |
| --- | --- |
| CentOS 6.x | CentOS 6.4 (32/64 bit) |
| CentOS 7.x | Other (64 bit) |
| Ubuntu 12.x | Ubuntu 12.04 (32/64 bit) for PV, Other (64 bit) for PVHVM |
| Ubuntu 14.x | Ubuntu 12.04 (32/64 bit) for PV, Other (64 bit) for PVHVM |
| Ubuntu 16.x | Ubuntu 12.04 (32/64 bit) for PV, Other (64 bit) for PVHVM |
| CoreOS x.x | Other (64 bit) |
| Windows Server 2008 R2 | Windows Server 2008 R2 (64 bit) |
| Windows Server 2012 | Windows Server 2012 (64 bit) |

### Installation des outils de l'hyperviseur

Cette étape est obligatoire.

- Désinstaller les autres outils d'hyperviseur :
   - Assurez-vous que le paquet `open-vm-tools` n'est pas installé. La commande suivante retournera null si le paquet n'est pas installé :
      - Debian : `sudo dpkg-query -l | grep open-vm-tools`
      - RedHat : `sudo yum list installed |grep open-vm-tools`
   - Si installé, désinstaller en exécutant  :
      - Debian : `sudo apt-get remove open-vm-tools -y`
      - RedHat : `sudo yum remove open-vm-tools.x86_64 -y`
- Attachez le ISO d' installation à l'instance en utilisant CloudMonkey :
   - Trouvez l'ID de l'ISO : `list isos listall=true filter=id isofilter=executable name='xs-tools.iso'``
   - Trouvez l'ID de l'instance : `list virtualmachines listall=true projectid=-1 filter=name,id name='[InstanceName]'``
   - Attachez l'ISO à l'instance : `attach iso id=[ISO ID] virtualmachineid=[instance ID]``
- Installez les outils d'hyperviseur dans l'instance :
   - Debian : `sudo mount /dev/cdrom /mnt && sudo /mnt/Linux/install.sh`
   - RedHat : `sudo mount /dev/cdrom /mnt && sudo /mnt/Linux/install.sh`
   - Windows : Execute 'As an administrator' the file `[CDRom drive]:\installwizard.msi`
- Redémarrez l'instance
- Detachez l'ISO d'installation de l'instance : `detach iso virtualmachineid=[instance ID]`
