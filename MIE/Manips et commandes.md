# **Manips et Commandes**
____________
>#### 1- Commandes Windows
>#### 2- Fastboot  
>#### 3- Déceler une boucle réseaux 
>#### 4- Démarrage iDrac
>#### 5- Fichier Hosts
>#### 6- Scan vers Ordi
>#### 7- MDP sur Word
>#### 8- Raccourci scanner CC4
>#### 9- Check IP Publique
>#### 10- Check connexion TeamViewer
>#### 11- SAV Dell
>#### 12- Lenteur PC
>#### [13- Autoriser session invité pour partage](https://github.com/Bilal-Aldimashq/Notes/edit/main/MIE/Manips%20et%20commandes.md#13--autoriser-session-invit%C3%A9-pour-partage-1)
>#### [14- BlueScreen Violation Drivers](https://github.com/Bilal-Aldimashq/Notes/edit/main/MIE/Manips%20et%20commandes.md#14--bluescreen-violation-drivers-1)
>#### [15- Empêcher Adobe de s'ouvrir pour fichier web](https://github.com/Bilal-Aldimashq/Notes/blob/main/MIE/Manips%20et%20commandes.md#15--emp%C3%AAcher-adobe-de-souvrir-pour-fichier-web-1)
_________________________
## **1- Commandes Windows**
### WIN+R:
- Gestion alimentation: powercfg.cpl
- Redémarrage poste: shutdown /r /f /t 0
- Console _Stratégie de groupe_: gpedit.msc
- Console _Gestion de l'ordinateur_: compmgmt.msc

### CMD:
- powercfg /h off = Désactiver le fastboot
- sfc /scannow = Analyse et réparation des fichiers du système
- Dism /Online /Cleanup-Image/ CheckHealth = Contrôle l'intégrité de l'image Windows
- Dism /Online /Cleanup-Image/ RestoreHealth = réparation de l'image Windows (A faire après Checkhealth si l'opération réussi

____________________________
____________________________
## **2- Fastboot**
WIN + R --> powercfg.cpl    
Aller dans _Options d'Alimentation --> Décocher _Activer démarrage rapide_
______________________________
______________________________

## **3- Déceler une boucle réseaux**
- Débrancher électriquement ou du réseau, les switchs présent dans la baie informatique.
- Les rebrancher un par un jusqu'a prendre la main sur un poste
- Lorsqu'un poste est disponible, faire un ping vers 8.8.8.8 -t
   - Tant qu'il est stable c'est que la boucle n'est pas sur ce switch
- Rebrancher les switchs un par un tout en contrôlant que le ping passe toujours
- Quand le ping est instable ou ne passe plus, c'est que le switch qui vient d'être rebranché crée la boucle.
- Redébrancher le switch, relancer le ping et rebrancher les autres switchs s'il en reste, afin de contrôler l'absence de boucle sur ces derniers.
- A ce stade, tout les switch sont branchés excépté celui créant la boucle.
- Débrancher tout les câbles connecter à ce switch.
- Relancer le ping 8.8.8.8 -t sur un poste disponible
- Rebrancher un par un les câbles du switch en attendant au moins 5 réponses de ping à chaque câbles brancher
- Quand le ping est instable ou ne passe plus, la boucle est présente sur ce câble.
    - Le retirer pour le moment en le mettant de côté.
    - Continuer avec les autres câbles afin de s'assurrer qu'il n'y a pas d'autres boucles
- Quand tout est rebrancher, repérer sur quel noyau le câble créant la boucle est branché.
- Diagnostiquer sur la prise ou l'appareil correpondant au repère du noyau ce qu'il se passe (Souvent un appareil avec deux câbles ethernet). Il peut s'agir d'une défaillance d'un appareil ou d'un câble.

_________________________
_________________________

## **4- Démarrage iDrac**
- Faire un ipscanner depuis un poste du réseau
- Repérer l'adresse iDrac et la rentrer dans la barre de recherche d'un navigateur web
- Les login sont **root** et **MDP@**  ou sont dans le Wiki
- Une fois sur la console, on peut gérer l'alimentation du serveur ou contrôler les journaux d'évènement

___________________________
___________________________

## **5- Fichiers Hosts**

Pour remplir le fichier Hosts permettant de faire la traduction d'un hôte avec son adresse ip:
- Ouvrir un CMD en Admin
- Taper _ipfonfig /flushdns_
- Retourner au niveau C:\
- _cd windows_--> _cd system32_--> _cd drivers_--> _cd etc_--> _dir_ (pour afficher les fichiers présent)
- _notepad hosts_
- en bas du fichier, renseigner l'adresse IP et le nom d'hôte correspondant

____________
____________

## **6- Scan vers Ordi**

- Aller sur l'interface web de l'imprimante.  
- Onglet _Connexion_--> _Numérisation_--> _Numériser vers FTP/SFTP_--> Cocher réseau

**Sur un profil**  
- _Numériser vers profil--> remplir Nom, Chemin du dossier partagé, Nom d'utilisateur et si besoin MDP.
>Pour scan vers mail, utilisé un compte Laposte
__________
__________

## **7- MDP sur Word**
Dans Word:
- Cliquer sur _Fichier_--> _Informations_--> _Protéger le document_--> _Chiffrer avec un mot de passe_
- Taper un mot de passe --> _OK_--> Rtaper le mot de passe--> _OK_ pour confirmer
________
________

## **8- Raccourci scanner CC4**
Pour une imprimante Brother MFC-9577DW
- Faire un clic droit sur le bureau--> _Nouveau_--> _Racourci_
- Ciblant vers: "C:\Program Files (x86)\ControlCenter4\BrCcBoot.exe" /model="MFC-9577DW"
________
________

## **9- Check IP Publique**
Pour avoir l'IP Publique d'un poste
- Ouvrir une page web--> _checkip.eljonjon.net
**Ou**
- Ouvrir un CMD--> tracert
________
________

## **10- Check connexion TeamViewer**
Explorateur de fichier--> Teamviewer--> Connections-incoming
________
________

## **11- SAV Dell**
Pour contrôler un PC Dell qui fonctionne mal:  
- Redémarrer le poste en appuyant sur F12 pour accéder au bios
- _Boot menu_--> _Diagnostics_--> Affichage du résultat et du code erreur s'il y a--> _Validation_
- Redémarrer en appuyant sur F2--> _System information_--> _Hard drive_ pour avoir des informations sur l'état du disque
______
______

## **12- Lenteur PC**
- Ouvrir le _Gestionnaire de tâches_--> Contrôler le temps d'utilisation--> Mettre fin au tâches inutiles
- Dans l'onglet des applications de démarrage, Désactiver les applications inutiles au démarrage
- Contrôler l'espace disque
- Vider les caches Windows et Utilisateurs
- Désactiver le fastboot, Désactiver la veille prolongée et coché la case _Performance élevée_
- Nettoyer le disque **WIN+R: cleanmgr**--> Sélectionner les fichiers temporaire--> _OK_
- Contrôler l'état du disque dans l'explorateur de fichier--> Clic droit sur le disque--> _Propriétés_--> _Outils_--> _Vérifier_
>Si un problème sur le disque est détecté, lancer la commande CMD en admin: **chkdsk /f C:** (C: s'il s'agit du disque C)
- **Optimiser les performance du disque**: Ouvrir la fenêtre de défragmenteur disque (**WIN+R: dfrgui**)--> _Optimiser_
- Vider la corbeille
- Ouvrir un CMD en tant qu'Admin et lancer la commande:
   - **scf /scannow**, suivi de:
   - **Dism /Online /Cleanup-Image /CheckHealth**, si l'opération réussi faire:
   - **Dism /Online /Cleanup-Image /RestoreHealth**
- Mise à jour du bios sur le support constructeur
- Reboot du poste
_____
_____

## **13- Autoriser session invité pour partage**
- Ouvrir la console _Stratégie de groupe locale_ (**WIN+R: gpedit.msc**)
- _Configuration Ordinateurs_--> _Modèle d'administration_--> _Réseau_--> _Station de travail LANMAN_--> _Activer les ouvertures de session invité non sécurisé_--> Cocher _Activer_--> _Appliquer_--> _OK_
_____
_____

## **14- BlueScreen Violation Drivers**
- Démarrer windows 2 ou 3 fois
- Sur l'écran de démarrage avancée --> _Options Avancées_--> _Dépanner_--> __Options avancées_--> _Paramètres de démarrage_--> _Redémarrer_--> Choix **6** (Mode sans échec avec invite de commande)
> Si cela ne fonctionne pas choisir _invite de commande_ dans options avancées
>- Taper la commande: `bcdedit /set {default} safeboot minimal`
>- Taper _Exit_ --> Eteindre le PC
- Une fois que Windows redémarre, Ouvrir un CMD en admin
- Taper la commande:
  - verifier /bootmode resetonbootfail
  - bcdedit /deletevalue {current} safeboot
- Exit
- Redémarrer le poste
_____
_____

## **15- Empêcher Adobe de s'ouvrir pour fichier web**
Dans l'application d'Adobe--> _Menu_--> _Préférences_--> _Internet_--> Décocher la case lecture par défault
_____
_____
