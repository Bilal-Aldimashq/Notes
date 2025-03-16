# **MIE-BOX**
______
>#### 1- Général
>#### 2- Contrôler sauvegardes MIE-BOX
>#### 3- Dépannage MIE-BOX
>#### [4- Commande MIE-BOX]()
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
Une fois logger sur la box (suivant les mails root)
- `ls /mnt/smb/*` Affiche les points de montage
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
- Génération de Box: `dmiecode | grep -A3 '^system information^'`
- Nom du cabinet: Aller dans le dossier script et afficher docteur.txt
- Status de la box et de l'exeternisation des sauvegarde = `extern` (Réhausse = 200Gb sinon c'est 100Gb)
- Afficher les disque de la box = `fdisk -l`
- Avoir des infos de la box = `uname -a`
- Afficher la version de Debian = `cat /etc/apt/source.list`
- Voir les VPN Clients= `cd /etc/openvpn`--> `cat clients`
  

