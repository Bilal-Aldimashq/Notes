# **MIE-BOX**
______
>#### 1- Général
>#### 2- Contrôler sauvegardes MIE-BOX
>#### 3- Dépannage MIE-BOX
_____
## **1- Général**
- 1 seul remontées à la fois
- Pas de MAJ des Box
- En root sur le terminal
- Pour les sauvegardes **Daily**, contrôler les fichiers **.db** (wlogos2, romexys ...)
  - pour les sauvegardes Romexys, important contrôler la présence fichier **egodat** et **Images**
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
**Box remonte malgré tout les bon branchement et led verte:**
- Eteindre la box
- Brancher un écran et un clavier
- Rallumer la box et appuyer sur F9 pour accéder aux options avancées
- _Options_--> _Sata_--> Entrée--> Entrée--> Au message d'alerte Entrée
- Sélectionner _Sata Legacy_
- Appuyer sur la touche échap--> échap--> F10 pour quitter et sauvegarder
- La box reboot
____
____
