# Installation de GDATA  
_________
- Désactiver Fast boot (powercfg / off)
- Désactiver veille
- Désactiver Microsoft Defender
- Ouvrir powershell en admin
- Sur une page web: eljonjon.net/Publics/msp.txt
- Copier le contenu sur la commande powershell 
- Rentrer le nom du cabinet, le nom du poste et le trigramme
- Executer le script
- Ouvrir la console regedit
- HKEY_LOCAL_MACHINE--> SOFTWARE --> WOW6432node --> GDATA: La clé client machine est le nom du poste
- Dans AVK_CLIENT: La clé ComputerName doit avoir le nom de poste donné lors de l'éxécution du script
    - Si elle n'y est pas, la créé en faisant clic droit--> Valeur chaîne--> entrer la valeur ComputerName et le nom souhaité.
    - Si elle éxiste mais n'est pas bonne, l'effacer et la recréer.

- Lancer la console Services et démarrer les services Gdata si besoin  
**Aller sur la console Gdata:**
- Dans le filtre rentrer le nom du poste de la clé ComputerName:
    - s'il n'apparaît pas avec le nom du poste, essayer avec la valeur de la clé client_Machine
    - S'il apparaît avec le nom client_Machine, retourner sur la console regedit au niveau Gdata--> Supprimer les deux cle client_Machine et relancer les services Gdata dans la console de services.
- Quand le poste est remonté, le mettre dans le groupe correspondant en clic droit--> déplacerle client vers--> Choisir le groupe dans l'arborescence.
- Si le poste est protégé, tout est bon
- Si il ne l'est pas:
    - Relancer le service Gdata et rafraîchir la console
    - Les Moteur A et B doivent avoir les mêmes valeurs que sur le Poste. Si les versions ne sont pas les bonnes: Cliquer sur le petit menu rapide du poste--> clic droit sur Gdata--> Mise à jour--> Actualiser et Mettre à jour.
    - Si malgré tout les manipulations ne suffisent pas, Supprimer le poste depuis la console Gdata et relancer les services.
