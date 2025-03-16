# **Préparations de postes**
_____
>#### 1- Avec image WDS-prepa ou boitier
____
## **1- Avec image WDS-prepa ou boitier**
- Coller l'étiquette du poste correspondante
- Rajouter les acceissoires supplémentaires (Carte graphique, RAM...)
- Remplir la fiche prépa
- Brancher le câble d'alimentation, Ethernet, clavier et souris
- Allumer le poste et appuyer sur F12
- Une fois sur le bios, aller sur _Bios setup_--> _Storage_
- Sélectionner **AHCI/NVME**--> _Exit_--> _Save & exit_
- Le poste redémarre. Appuyer sur F12 et désactiver le secure boot--> _Save & exit_
- Le poste redémarre. Appuyer sur F12 et choisir IPV4 dans la liste proposée.
- Choisir _PXE_--> _Macrium_
- Sur Macrium, cliquer sur _Browse for an image file_
- Cliquer sur l'îcone de lecteur réseau
- Dans _Share_ rentrer le _\\wds-prepa\img_
- Cliquer sur le disque qui apparaît
- Choisir l'image correspondant au poste

  >**S'il n'y a pas d'image correspondante:**
  > - Eteindre le poste
  > - Brancher un disque dur externe avec Ventoy et iso Win (ou Media Creation Tool)
  > - Démarrer le poste et appuyer sur F12
  > - Sélectionner le disque dur dans le menu bios
  > - Choisir Windows
  > - Lancer l'installation sans clé
  > - Supprimer les partitions du disque pour une seul partition
  > - Choisir Installation personalisée
  > - Installer sans compte Microsoft
  > - Pour Windows 11 rejoindre un groupe de travail ou un domaine (comme pour la réinstallation) ou:
  >   - A la fenêtre de demande de compte Microsoft, Débrancher le câble réseau--> Appuyer sur les touches MAJ+F10 pour ouvrir un cmd.
  >   - Rentrer la commande `OOBE\bypassNRO`
  >   - L'ordinateur va redémarrer
  >   - Sélectionner _Je n'ai pas internet_
  >   - Rebrancher le câble réseau une fois sur le bureau
  >   - Installer Teamviewer, Chrome et adobe

- Cliquer sur _Restore image_
- Cliquer sur _Select a disk to restore to_
- Sélectionner le disque C: (Pas de disque DATA)
- _Next_--> _Finish_
- A la fenêtre indiquant la fin de l'opération, cliquer _OK_--> fermer la fenêtre--> Le poste redémarre

**Partie 2: Windows**
- Ouvrir l'explorateur de fichier
- Sur _Réseau_, ouvrir WDS-PREPA
> S'il n'est pas accessible, ouvrir la console netplwiz--> renseigner **WDS-PREPA** et **Invité**
- Ouvrir un terminal en Admin--> _Set-Execution Policy Unrestricted_--> _Oui_
- Aller dans le dossier C:\MIE--> Clic droit sur script _Change host..._ et l'éxécuter--> Rentrer Nom du client, Poste et Trigramme
- Remplir la fiche prépa avec le Teamviewer
- Créer un Utilisateur MIE avec MDP@ et l'ajouter au groupe Administrateurs
- Activer la licence windows (**WIN+R: slui**)
- Lancer les mise à jour Windows
- Aller sur _Dell Support_ et l'installer
- Lancer les mise à jour Dell
- Installer GData, Office suivant le BL
- Désactiver le fastboot et les veille
- Placer le curseur _UAC_ au plus bas
- Désactiver les notifications Windows
- Désactiver IPV de toutes les cartes réseau
- Désactiver defender
- S'il y a un deuxième disque, l'initialiser avec _Gestionnaire de disque_ (**WIN+R: diskmgmt.msc**)
- Mettre Google Chrome par défaut
- Installer les drivers des imprimantes et scanner si besoin
- Ajout dans le domaine s'il y a
**Pour les serveur**
  Lancer le script WakeOnLan
  - Installer Dell command/configures
  - Exécuter le script PowerShell (sur dossier procédure)
  - Ouvrir un CMD en Admin--> cd C:\programm Files(x86)\Dell\Command configure\x86_64
  - Faire la commande: cctk.exe --wakeonlan --> La sortie doit indiquer _wakeonlan=LANWLAN_
