# Installation de GDATA  
_________
- Désactiver Fast boot (powercfg / off)
- Désactiver veille
- Désactiver Microsoft Defender
- Ouvrir powershell en admin
- Sur une page web: eljonjon.net/Public/msp.txt (si fonctionne pas: eljonjon.net/Public/wfa.exe)
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
 
- Faire une capture d'écran du numéro de série du poste, de la clé ComputerName, de l'espace de stockage du poste et de la console GData
- Contrôler les moyens de sauvegardes du client et leur états si possible. Faire capture d'écran 
- Envoyé par mail en réponse à tous du BL correspondant, les captures d'écran et des remarques du client si besoin  
  
 
______________________________________________________________

# Renouvellement AV GData

- Ouvrir console GData
- Rentrer le nom du client dans le filtre

**Sur le poste Client**
- Ouvrir le gestionnaire de clé Regedit (**WIN+R: regedit**)
- Contrôler la ComputerName dans _`HK_LOCAL_MACHINE`_--> _SOFTWARE_--> _WOW6432Node--> _GDATA_--> _`AVK_CLIENT`_
- Faire une capture d'écran de la clé
- Aller sur la console Gdata et contrôler que le poste remonte bien avec le nom de la clé (Sinon le supprimer et faire remonter comme à l'installation)
- Si besoin de mettre à jour, sur l'icône GData de la barre de tâches--> Clic droit--> Mise à jour--> Cliquer sur _Mettre à jour_ puis _Actualiser_
      - Rafraichir la console Gdata jusqu'a remonté les mêmes versions que le poste. Si besoin redémarrer les services Gdata dans le gestionnaire de _Services_ (**WIN+R: Services.msc**)
- Faire une capture d'écran de la console indiquant protégé et avec le même nom que la clé
   - Si des risques persistent malgré la mise à jour, aller dans l'onglet _Journaux_--> cliquer sur les risques isolés par GData pour les marquer comme lu.
- Faire une capture d'écran du disque de stockage du poste
- Contrôler les moyens de sauvegardes du client et leur états si possible. Faire capture d'écran
- Envoyé par mail en réponse à tous du BL correspondant, les captures d'écran et des remarques du client si besoin

