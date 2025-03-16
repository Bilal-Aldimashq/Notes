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

- Cliquer sur _Restore image_
- Cliquer sur _Select a disk to restore to_
- Sélectionner le disque C: (Pas de disque DATA)
- _Next_--> _Finish_
