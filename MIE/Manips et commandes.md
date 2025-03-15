## **Fastboot**
WIN + R --> powercfg.cpl    
Aller dans _Options d'Alimentation --> Décocher _Activer démarrage rapide_
______________________________________________________________________

## **Déceler une boucle réseaux**
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

__________________________________________________________________
