# Lecteurs de Cartes

**DiagAm** permet de diagnostiquer les lecteurs de cartes vitale (ATSAM pour le télécharger).  

**Problème lecture de la carte:**  
- Débrancher 30 secondes le lecteur
- Dans **Gestionnaire de périphériques**--> Contrôleur Bus USB--> Gestion d'alimentation--> Décocher **Autoriser l'ordinateurà....**
- Désactiver le fast boot:
    - Commande **powercfg /h off**
      ou
    - Dans **Gestion d'alimentation**--> Choisir l'action des boutons--> Décocher Démarrage rapide.
- Redémarrer le poste
- Eventuellement mise à jour des drivers des ports USB via Dell Support ou similaire suivant marque du poste.   

