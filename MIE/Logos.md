# **LOGOS**
_________

>#### 1- Vider les caches Logos
>#### 2- Activer carte CPS
>#### 3- Problèmes accès dossier Wlogos2\Patients
>#### 4- Supprimer un dossier patient
>#### 5- Problème de télétransmission
>#### 6- [Fusionner carte CPS et CPE]()
>#### [7- Erreur rouge dll]()
>#### [8- Problème DBS Win]()
>#### [9- Configuration des boîtes gmail]()

___________________

## **1- Vider les caches Logos:**

Dans l'explorateur de fichier--> Ce PC--> C:\--> Windows--> Temp --> Supprimer les fichiers caches s'y trouvant.  

Ce PC--> C:\--> Utilisateurs--> Utilisateur(de la cession)--> .AppData (Si pas visible cocher masqué dans l'onglet _Affichage_)--> Local--> Temp--> Vider les fichiers.  

Vider la corbeille.
_____________________
_____________________

## **2- Activer carte CPS:**

`La carte doit être insérée dans le lecteur de carte`

- Dans Logos--> _Outils_--> _Profil Utilisateurs
- Cliquer sur le profil concerné
- Aller sur l'onglet _Sécurité Sociale_
- Cliquer sur _Lire la carte_
- Le praticien rentre le code de la carte
- Contrôler sur l'icône ampoule que tout est bon--> cliquer _SAVE_
    - Si la carte est bloquée:
        - Lancer l'utilitaire de débloquage
        - Cliquer sur l'icône débloquer
        - Le praticien doit rentrer le code 3 fois
        - Fermer l'utilitaire et retourner sur _Lire la carte_
- Cliquer _OUI_ pour recopier les infos CPS
- Pour **l'adresse de télétransmission**, si le praticien n'en a pas:
    - Comparer avec un autre praticien si c'est une adresse Logos (facile) ou autre. Si c'est Logos:
    - Cliquer sur l'icône de l'ampoule
    - Cliquer sur le **+**
    - Cliquer sur l'icône d'outils
    - Cliquer sur_Adresse facile_
___________________________________________
___________________________________________

## **3- Problème accès dossier Wlogos2\Patients:**

- Aller sur le **poste serveur** (Par exemple: Nom= PANO)
- Ouvrir la console _Gestion de l'ordinateur_ (**WIN+R: compmgmt.msc**)
- Si besoin créer un profil Logos avec pour mot de passe Logos
- Rajouter ce nouveaux profil dans le groupe Administrateurs
- Dans l'explorateur de fichier (**WIN+E**), trouver le dossier **Patients** ( Le chemin est indiqué sur le message d'erreur du poste client), par défault celui-ci est _C:\Wlogos2\Patients_
- Faire un clic droit sur ce dossier--> _Partage_
- Il y apparraît le chemin de partage réseaux. Par exemple PANO\Wlogos2
- Cliquer sur _Partage_
- Rentrer le nom du profil Logos dans le menu déroulant--> Cliquer sur _Ajouter_
- Dans la fenêtre du bas apparaît Logos--> Cliquer sur le menu déroulat et cliquer sur _Lecture et écriture_
- Cliquer sur _Partager_
- Le chemin de partage s'affiche--> Cliquer sur _Terminer_

**Sur le poste Client**
- Contrôler Windows Defender (**WIN+R: wf.msc**), le partage par mot de passe et le [fastboot](https://github.com/Bilal-Aldimashq/Notes/blob/main/MIE/Manips%20et%20commandes.md#1--fastboot-1). Les désactiver si nécessaire
- Ouvrir une console mmc et rentrer _netplwiz_
- Onglet _Options avancées_--> _Gérer les mots de passe_
- Cliquer sur _Informations d'identification Windows_--> _Ajouter des informations d'identification Windows_
- Rentrer le nom du poste serveur (PANO), ainsi que les identifiant créés Logos et mot de passe Logos--> _OK_.  
    >- REMARQUE: Si Logos ne s'ouvre pas, changer le nom du PANO par son IP
- Activer les sessions invités dans les stratégie de groupe si possible
- Relancer le logiciel Logos
_____________________
_____________________

## **4- Supprimer un dossier patient**
Dans Logos--> _PATIENTS_--> Cliquer sur le dossier du patient
Aller sur _Etat civile_--> _Options_--> _Supprimer ce dossier_

____________________
____________________

## **5- Problème de télétransmission**

- Cliquer sur l'îcone de messagerie--> _Paramètres_--> _Test_ (Mails)--> Tester envoie (Normalement toujours bon)
- _Test reception_--> Coché _SSL_ et _ Identification_
- Dans la case _PORT_, renseigner 465
- Dans _Authentification--> Pour Mot de passe _Idem FSE_
- Faire le test (Doit être OK)
____________
____________

## **6- Fusionner carte CPS et CPE**

- Dans Logos--> _Outils_--> _Profil Utilisateur_--> _Profil Assistante_--> Cocher les cases des praticiens attachés--> _Enregistrer_
______
______

## **7- Erreur rouge dll**
Lors du démarrage de Logos si le message d'erreur apparaît dans une fenêtre rouge:
- Essayer mise à jour de Logos dans la barre d'outils de Logos
#### **Si cela ne suffit pas, réinstaller Logos:**
- Ouvrir Logos--> _Outils_--> _Profil d'utilisateur_--> Prendre les renseignements des passerelles (Nom et chemin d'éxecutable) si possible
- Fermer Logos
- Renommer le fichier wlogos1 (sur le C:\) en wlogos1.old
- Lancer l'installation de Logos. Soit dans le dossier C:\MIE ou en le copiant depuis le repo interne
- Une fois l'installation terminnée, aller sur le fichier C:\wlogos1\config
- Renseigner le chemin du dossier Patients partagé depuis le serveur
- Appuyer sur la touche tab afin que les autres chemin du tableaux se remplissent automatiquement
> Si les chemins se remplissent en rouge et sans afficher les dossiers des praticiens, contrôler l'accessibilté du chemin ou changer le nom du serveur par son IP
- Lancer Logos et le laisse faire les MAJ
- Si un problème persiste, redémmarrer le poste
- Refaire les passerelles dans _Outils_--> _Profil d'utilisateurs_--> Sélectionner l'application d'imagerie et le chemin de son éxecutable (Copier sur un autre poste si besoin)

_____
_____

## **8- Problème DBS Win**
S'il y a un problème avec DBS Win
- Prendre le chemin sans le .ini
- Authentifier comme pour le dossier Patients
_____
_____

## **9- Configuration des boîtes gmail**

- Sur Logos --> Icône _Mail_ (à gauche)--> _Oui_--> Cocher Gmail--> Rentrer le nom du Dr ou du centre--> Rentrer l'adresse mail
- Rentrer le nom qui apparaîtra en destination--> Rechercher--> Sélectionner le compte--> Continuer-->Cocher Delete--> Continue--> Cocher les utilisateurs
- Cliquer sur les signtures--> OK
_____
_____


