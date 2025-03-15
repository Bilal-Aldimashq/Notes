>#### 1- Façon Timothée
_____________


## Façon Timothée

`Prévoir une clé USB d'au moins 8Gb`
- Connecter la clé sur un poste qui servira à la préparation
- Télécharger Ventoy en zip
- Dans le repo_interne, prendre BOB (Repo\isos\bob\isos\V.4.985) et le copier sur le poste de préparation.
- Télécharger les pilotes réseaux du poste à réinstaller si besoin
- Mettre Ventoy extrait et les pilotes dans le dossier C:\MIe (Le créé si besoin)
- Ajouter aussi un iso Windows 11 dans le dossier
- Lancer Ventoy--> Choisir _Ventoy 2disk_--> Sélectionner la clé USB--> _Install_
- Copier sur la clé Ventoy, BOB, iso Windows et pilote réseaux
  
  **Sur le poste à réinstaller**
  >##### Si besoin de faire une image:
    >- Utiliser MACRIUM en le téléchargeant
    >- Lancer l'application Macrium--> _create_
    >- Cocher Disque 1
    >- Cliquer _image this disk_--> _Folder_--> _Chemin où installer la copie (NAS ou autre système de sauvegarde s'il y a la place)_--> Next--> _FINISH_
    >- Une fois que le poste réinstaller a de nouveau Windows, copier l'image sur celui-ci après avoir installer Macrium
    >- Sur le fichier de l'image sauvegarder--> clic droit--> Lancer le macrium--> Copier l'image
    >- Lancer l'application Macrium sur le nouveau poste--> Cocher _C_--> _Accepter_--> Copier les données d'utilisateurs
    >- Démonter le Macrium--> Enregistrer dans le dossier C:\MIE le Macrium et l'image (peut servir de BKP)
      
  
- Insérer la clé USB
- Démarrer le poste et appuyer de façon répéter sur la touche F12 pour ouvrir le menu Bios
- Aller dans Bios Setup et désactiver le secure boot (Le poste peut redémarrer)
- Redémarrer le poste avec F12
- Sélectionner UEFI USB--> Ventoy--> Windows 11--> Booting normal mode
- Installer Windows en ignorant la clef
- Si les partitions doivent être sélectionner, toutes les supprimés pour en faire une seul
- Configuration personnelle
- Lors de la demande du compte MICROSOFT, utiliser _Rejoindre un goupe de travail ou un domaine_
- Nommer le poste et la session en _Utilisateur_ sans mot de passe
- Une fois arriver sur le bureau, installer Chrome et teamviewer
- Ouvrir la console de _gestion de l'ordinateur_ (**WIN+R: compmgmt.msc**)
- Créé un nouveau profil MIE et MDP@. Le rajoute dans le groupe Aministrateurs
- Créer le dossier C:\MIE
- Réinstaller les logiciel si besoin et si possibe
______________________
______________________

