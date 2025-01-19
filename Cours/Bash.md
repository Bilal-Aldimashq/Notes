# **BASH**  
____

1. [_Wilcards_](https://github.com/Bilal-Aldimashq/Notes/new/main/Cours#wilcards)  
2. [_Terminale_](https://github.com/Bilal-Aldimashq/Notes/new/main/Cours#terminale)
    * [_Copier et déplacer_](https://github.com/Bilal-Aldimashq/Notes/new/main/Cours#copier-et-d%C3%A9placer)





## **Wilcards:**
`*` = Tous les fichiers   
? = Un caractère quelconque  
[] = Un caractère parmi  
	     liste [abc]  
	     suite [a-z]  
	     possible combine a[bc]*  

_________
_________





## **Terminale:**  
-ou-- : Arguments de commande (flags) modifient le comportement de la commande  
‘ = Simple quote: Ne prend pas en compte les métacaractères  
“ =Double quotes: Prend tous les caractères  
/ : Séparateur de répertoire  
\ = Supprime la fonction du caractère suivant  
; = Permet de lancer plusieurs commande l’une après l’autre  
| = pipe  
`>` ou >> =  Redirection   
< ou << = Donne en entrée  
&& =  Fait ce qui suit si ce qui précède est bon  
|| = Fait ce qui suit si ce qui précède est pas bon  
|& = Envoie une sortie si ce qui suit et précède est une erreur  
~ : Représente User dans le terminal  
.. : Représente le dossier parent  
. : Représente le dossier actuel  
cd : change directory  
cd / : Aller à la racine  
cd ~ : Aller à User  
cd .. : Remonter d’un dossier  
cd ~/ : Aller directement au dossier (depuis n’importe où)  
pwd : Affiche le chemin actuel (print working directory)  
ls : Ouvre le dossier  
ls -a : Ouvre le répertoire avec les dossier ou fichiers cachés  
ls -l : Ouvre le dossier en colonne avec plus de détails  
ls -l ~/.bashrc = Affiche le timestamp (Horodatage)  
du = Affiche la taille du répertoire  
touch ~/.bashrc = Sauvegarde à l’instant le timestamp  


>**ls -larth** = Liste les dossiers avec les propriétées ( En graphique clique droit sur le dossier→ propriétées)  
 -rwxrw-r-x = premier tiret (Type de répertoire),  
du 2 au 4 droit d’utilisateur (read,write,execute),  
5 à 7 droit de groupe (read, write, pas execute),  
 8 à 10 droit des autres utilisateurs (read, pas lecture, execute)  



>**chmod** = change les droits des dossiers.  
chmod 640 test =  
  >+ 6 pour l’user;  
  >+ 4 pour les groupe;  
  >+ 0 pour les autres.  
r=4; w=2; x=1. user a r et w; groupe a r; others a rien  
chmod o-w fichier3 = enlève les droits d’écriture aux autres sur le fichier3 (option -R pour la récursivité)  
	u = Utilisateur  
	g = Group  
	o = Autre ( ni u ni g)  
	a = Tout le monde  
  `+` = Ajouter  
	`-` = Supprimer  
	= = affectation


chown = Changement de propriétaire  
chown toto fichier1 = change le propriétaire de fichier1 par toto  
chgrp = changement de groupe  
chrgp alumnis fichier2 = Change le  groupe actuel du fichier2 par le groupe alumnis  
setfacl = Modifier les droits ACL  
getfacl = Affiche les droits ACL  

echo : traite ce qu’il y a après comme du texte et non une commande

cat = Affiche le contenu d’un fichier  
tee = Affiche à la fin de la liste  
more =  Affiche le fichier page/page  
less = more plus lisible  
head = Affiche les 10 premières lignes d’un fichier  
tail = Affiche les 10 dernières lignes d’un fichier  
-n = Suivi d’un nombre en argument de head et tail, spécifie le nombre de pages à afficher  
-f = Argument de head ou tail = follow, suivre en direct  
wc = compte les lignes du fichiers  
sort = Affiche par ordre alphabétique  
sort -u = Liste par ordre Alphabétique en gardant la 1er lignes si doublons  
grep = filtre suivant motif indiqué après la commande  
grep -E “1|2|3” = grep multiples mots (extension d’expressions)  
nano : Éditer un fichier  
#### Copier et déplacer 





