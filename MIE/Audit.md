## **AUDIT DE POSTES**

- Créer un dossier au nom du client
- Créer un fichier excel à partir du template  
  **Sur le poste à auditer:**
- WIN+R --> msinfo32
- Aller sur _Fichier_ --> Nommer le _NFO-NomDuPoste_--> Enrgistrer sur le bureau
- Aller sur un navigateur--> Télécharger **CPUZ**--> Choisir _SETUP English_  
![cpuz](https://github.com/Bilal-Aldimashq/Notes/blob/main/Ressources/Cpuz.jpg)

- Lancer CPUZ
- Cliquer sur _Save report HTML_--> Nommer le fichier CPUZ-_NomDuPoste_--> Enregistrer sur le bureau
- Cliquer sur _Close_
- Lancer un CMD
- Taper _Hostname_--> Renseigner le tableaux
- Taper _wmic bios get serialnumber_--> Remplir le tableaux
- Depuis _Informations_, remplir le tableaux du Modèle, Type...
- Pour l'âge, prendre Bios + 3-4 ans ou avec le numéro de série sur le Dell Support en rajoutant 3 ans au temps de support
- Ouvrir le _Gestionnaire de tâches_ (**WIN+R: taskmgr.exe**), Remplir la taille et le type de disque de stockage, la RAM et la carte graphique
    -  Pour le débit, clic droit sur Ethernet--> _Afficher les détails_ (1Gb ou 100Mb)
- Ouvrir le _Gestionnaire de périphérique_ (**WIN+R: devmgmt.msc**), remplir si des capteurs ou autres périphérique spéciale raccorder à l'ordinateur.
- Renseigner l'anti-virus. En tapant dans la barre de recherche antivirus ou si un icône de celui-ci est présent sur la droite de la barre de tâches.
- Si besoin laisser un commentaire dans la case du poste
- Placer les fichiers CPUZ et NFO, ainsi que CPUZ, dans le dossier C:\MIE (Le créé s'il n'éxiste pas)
- Les transférer dans le dossier créé pour l'audit du parc client
  
### Onglet Logiciels:  
Dans cette onglet du fichiers Excel, renseigner les logiciels présent sur le poste (Carestream, Eazydent,OphtixNG, ophtiswitch, ophtilink ou autre) ainsi que leur version.

Envoyer par mail (tech; commandes; comptabilité; julien; geoffroy et jonathan) le dossier complet de l'audit comprenant le fichier excel, les rapports CPUZ et NFO.

