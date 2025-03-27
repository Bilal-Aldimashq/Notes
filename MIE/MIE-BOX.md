# **MIE-BOX**
______
>#### [1- Général](https://github.com/Bilal-Aldimashq/Notes/blob/main/MIE/MIE-BOX.md#1--g%C3%A9n%C3%A9ral)
>#### [2- Contrôler sauvegardes MIE-BOX](https://github.com/Bilal-Aldimashq/Notes/blob/main/MIE/MIE-BOX.md#2--contr%C3%B4ler-sauvegardes-mie-box)
>#### [3- Dépannage MIE-BOX](https://github.com/Bilal-Aldimashq/Notes/blob/main/MIE/MIE-BOX.md#3--d%C3%A9pannage-mie-box-1)
>#### [4- Commande MIE-BOX](https://github.com/Bilal-Aldimashq/Notes/blob/main/MIE/MIE-BOX.md#4--commande-mie-box)
>#### [5- Site MicroBoxConnect](https://github.com/Bilal-Aldimashq/Notes/blob/main/MIE/MIE-BOX.md#5--site-microboxconnect)
>#### [6- Remontées MIE-BOX](https://github.com/Bilal-Aldimashq/Notes/blob/main/MIE/MIE-BOX.md#6--remont%C3%A9es-mie-box)
>#### [7- Préparation MIE-BOX](https://github.com/Bilal-Aldimashq/Notes/blob/main/MIE/MIE-BOX.md#7--pr%C3%A9paration-mie-box)

_____
## **1- Général**
- 1 seul remontées à la fois
- Pas de MAJ des Box
- En root sur le terminal
- Pour les sauvegardes **Daily**, contrôler les fichiers **.db** (wlogos2, romexys ...)
  - pour les sauvegardes Romexys, important contrôler la présence fichier **egodat** et **Images**
- en0 = IP de l'interface 1
- tun0 = VPN

______
______

## **2- Contrôler sauvegardes MIE-BOX**
- `cd /mnt/crypted_fs`
- `ll`
- `find . -mtime -1` Affiche les dossier modifier les dernières 24h
_____
_____

## **3- Dépannage MIE-BOX**
**Box remonte pas malgré tout les bon branchement et led verte:**
- Eteindre la box
- Brancher un écran et un clavier
- Rallumer la box. **Elle ne prend pas de DHCP**
- Appuyer sur F9 pour accéder aux options avancées
- _Options_--> _Sata_--> Entrée--> Entrée--> Au message d'alerte Entrée
- Sélectionner _Sata Legacy_
- Appuyer sur la touche échap--> échap--> F10 pour quitter et sauvegarder
- La box reboot
____
____

## **4- Commande MIE-BOX**
- Génération de Box: `dmidecode | grep -A3 '^system information^'`
- Nom du cabinet: Aller dans le dossier script et afficher docteur.txt
- Status de la box et de l'exeternisation des sauvegarde = `extern` (Réhausse = 200Gb sinon c'est 100Gb)
- Afficher les disque de la box = `fdisk -l`
- Avoir des infos de la box = `uname -a`
- Afficher la version de Debian = `cat /etc/apt/source.list`
- Voir les VPN Clients= `cd /etc/openvpn`--> `cat clients`
- Voir ce qui est sauvegarder sur la box = `ncdu`
_____
_____

## **5- Site MicroBoxConnect**
Remplir les informations Box
- `cd script`--> `cat exclude_local` Il doit y en avoir autant que le serveur
- `cat exclude_distant --> Tout mettre dans le premier
- Faire un `cat`de chaque fichier exclude.local--> Coller dans la case exclude local correpondant
- Enregistrer et réouvrir pour assurer l'enregistrement
_____
_____

## **6- Remontées MIE-BOX**
Une fois logger sur la box (suivant les mails root)
- `df -h`
- `ls /mnt/smb/*` Affiche les points de montage
- Si tout les points de montage ne sont présent (df -h) lancer le script mount_smb.sh pour les partages et le script mount_crypted_fs.sh pour monter le crypted
- recontrôler avec df-h
- Si un disque a plus de 90% d'espace utilisé le signaler dans le rapport
- Si un fichier save est dans les points de montage, le signaler dans le rapport
____
____

## **7- Préparation MIE-BOX**
- Insérer 3 disque de 1To ou 3 disque de 512Go dans la box
- Insérer la clé USB de prépa dans la box
- Brancher un clavier et un écran
- Brancher un câble Ethernet sur le port 1
- Cacher le port 2 et ilo
- Noter le N° de la box à l'arrière
- Démarrer la box et appuyer sur F11 (F9 si les disque ne sont détectés)
  - _System option_--> _SATA_--> _Enbed_--> _Legacy_
  - _Server Availaible_--> _Automatic power on_--> _Always-on_
  - _Echap et F10 pour quitter et sauvegarder
  - La box redémarre
- A l'écran d'installation choisir _Install_
- Installer avec _France_
- Nom de box = miebox-465
- Utilisateur root/ MDP = root
- nom d'utilisateur = mieuser
- Choisir partition manuel
- S'il y a des partitions sur les disques les supprimer
- Sur chaque disque:
  - Créer une partition 1Go--> Utiliser comme--> Ne pas utiliser
  - Créer une partition 9Go--> Utiliser comme--> Ne pas utiliser
  - Créer une partition 40Go --> Utiliser comme--> Ne pas utiliser
  - Créer une partition avec le reste--> Utiliser comme--> Ne pas utiliser
![](https://github.com/Bilal-Aldimashq/Notes/blob/main/Ressources/Partition_Debian%20(1).jpg)

- Utiliser les partitions 1Go en Boot en ext4
- Utiliser les partitions 9Go en swap
- Utiliser les partitions 40Go pour root en ext4
- Utiliser les partitions restantes en ext4
- Aller sur _Configurer les RAID avec avec logiciel_
  - Créer RAID 1 avec les partitions boot
  - Créer RAID 1 avec partition Swap
  - Créer RAID 1 avec partition Root
  - Créer RAID 5 avec les partitions restantes
![](https://github.com/Bilal-Aldimashq/Notes/blob/main/Ressources/Partition_Debian%20(4).jpg)

- Terminer les partitions
- Choisir la zone Mirroir des gestionnaire de paquets
- Ne prendre aucun environement de bureau et cocher SSH
- Quand l'installation est finis, débrancher la box--> Enlever la clé--> La redémarrer. Si tout boot bien c'est OK
 




  

