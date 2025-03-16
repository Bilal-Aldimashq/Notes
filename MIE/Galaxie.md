# **GALAXIE**
_______________
>#### 1- Kill session
>#### 2- Problème fichier FSE
>#### 3- [Scan sur TSE]()
>#### 4- [Changer affichage monétaire]()

_______________
## **1- Kill session** 
- Identifier le nom de la session posant problème sur le poste client
- Aller sur le serveur TSE (Il gère les sessions distante)
- Aller sur _Gestionnaire de serveur_--> _Service de Bureaux à Distance_--> _Collections_--> _TSE_
- Dans le tableaux des connections, faire un clic droit sur la session identifier sur le poste client--> _Déconnecter_ (x2 ou 3)
- reconnecter la session sur le poste client


#### Ou par gestionnaire de tâches:
- Sur le serveur, Ouvrir le gestionnaire de tâches (**WIN+R: taskmgr**)
- Dans l'onglet _Utilisateurs_--> Clic droit sur la session identifier sur le poste client--> _Déconnecter_ (x2 ou 3)

_______
_______

## **2- Problème fichier FSE**
- Aller sur le serveur
- Ouvrir un cmd et rentrer _netshare_
- Trouver le dossier partagé pouvant contenir Pyxvital
- Mapper sur le poste client avec l'IP du serveur

_______
_______

## **3- Scan sur TSE**

Sur le poste, trouver le dossier "Scanner_galaxie". Sinon le prendre sur le repo interne
- Lancer l'installation de l'application--> _Install_--> _Ignore_--> Terminer
- Copier le contenu du fichier _Système_ et coller le contenu dans le dossier `Scanner_Galaxie`
- Déconnecter la session TSE
- Lancer l'application _Passerelle scanner sans tw_
- Remplir le chemin (Se trouve sur un autre poste)
- Relancer la session et tester (Si fonctionne pas reboot du poste)
________
________

## **4- Changer affichage monétaire**
Ouvrir le _Panneau de configuration_--> _Horloge et région_--> _Région_--> _Paramètres supplémentaires_--> _Symboles monétaires_--> _Symboles décimal_--> choisir **,** ou **.**--> _Appliquer_--> _OK_
________
________
