### Jeux de tanks

![](https://camo.githubusercontent.com/4e9df9d5f78e6aab2226935bc7c14c03819c4557/687474703a2f2f696d672e796f75747562652e636f6d2f76692f356239376552355f6651492f302e6a7067)

Construisons un mini-jeu! 
Il sera composé de 2 joueurs manipulant un tank et s'affrontant. 
Nous construisons une petite aire de jeux avec des obstacles et deux modèles de chars. 
Chaque objet a un ensemble de corps rigide. 
Certains des obstacles sont animés sur le Timeline pour rendre le jeu plus dynamique. 
La configuration de l'éclairage est basée sur le [tutorial terrain ](https://github.com/armory3d/armory/wiki/terrain-de-jeux)

![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/tanks/0.jpg)

**Le char rouge** agit comme un **joueur 1**. Nous autorisons les commandes du clavier et de la manette de jeu, mais codons en dur les touches utilisées pour plus de simplicité. 
Dans une arborescence Player1Controls, la touche gauche du clavier ou de la manette de jeu est définie pour envoyer un événement nommé **«turn_left»** "tourner à gauche". 
Plus tard, nous utilisons cet événement pour faire pivoter le tank contrôlé par le joueur.

![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/tanks/1.jpg)

Faites cela pour toutes les touches - **gauche**, **droite**, **avant** et **arrière**.

![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/tanks/2.jpg)

**Blue tank** agit comme un **joueur 2**. Nous définissons les mêmes contrôles, mais mappons les touches vers **WSAD** et la deuxième manette connectée à la place.

Dans un **TankTree** "arbre-tank", nous écoutons les événements et effectuons des actions pour contrôler réellement le tank. 
La raison pour laquelle cet arbre de nœuds est séparé est que nous l'attachons aux deux réservoirs, évitant ainsi la duplication des arbres de nœuds.

Le nœud d'événement est configuré pour écouter l'événement 'turn_left'. 
Pour le **joueur 1**, cet événement est déclenché lorsque la touche gauche est enfoncée. 
Pour le **joueur 2**, cela se produit en appuyant sur la touche **A**. 
Le nœud On Event est connecté au nœud Rotate Object, avec la valeur du vecteur **Z **définie sur une petite **valeur positive** contrôlant la vitesse de rotation. 
Jouer au jeu maintenant, en appuyant sur la touche gauche fait tourner le réservoir!

![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/tanks/3.jpg)

Nous faisons de même pour l'événement '**turn_right**', mais la valeur du vecteur **Z** est définie sur une **valeur négative** pour tourner dans la direction opposée.

Passons à l'événement de traitement «avant». 
Pour déterminer dans quelle direction le réservoir doit se déplacer, le nœud Vector from Transform est utilisé avec le type défini sur Look. 
Ce vecteur est ensuite réduit à l'aide du nœud Vector Math pour ralentir la vitesse d'avancement du réservoir. 
Le vecteur résultant est passé au nœud Traduire l'objet.

![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/tanks/4.jpg)

Comme précédemment, nous faisons la même chose pour l'événement «en **arrière**» avec le vecteur de translation inversé.

Maintenant que les chars sont entièrement contrôlables, nous leur faisons tirer des balles. 
Pour que la scène reste claire, l'objet puce est placé dans une collection séparée avec l'icône de rendu désactivée. 
Cela garantit que l'objet sera exporté mais pas visible par lui-même. 

![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/tanks/5.jpg)

En sélectionnant le réservoir rouge, un objet vide est ajouté en tant qu'enfant - l'emplacement de cet objet définit où tirer les balles. 
Un nouvel arbre logique est ajouté à cet objet vide. 
La touche M ou la croix de manette de jeu / une touche émet un événement «feu». 
Nous faisons de même pour le réservoir bleu.

![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/tanks/6.jpg)

Nous attachons une autre arborescence logique - gestion de la réponse à l'événement **'fire'**   " tire". 
Nous engendrons un nouvel objet - notre modèle de balle de la couche 2, et définissons son emplacement sur le propriétaire de l'arborescence logique - dans ce cas, un point d'apparition de balle - défini comme un objet vide placé en tant qu'enfant du tank.

![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/tanks/7.jpg)

En jouant la scène maintenant, nous découvrons que les balles tombent du canon jusqu'au sol. 
Nous avons besoin de poudre de feu!

![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/tanks/8.jpg)

Le nœud Apply Impulse corrige cela. 
Semblable à faire avancer le char, nous acquérons le vecteur avant et le redimensionnons.

![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/tanks/9.jpg)

Même si Armory élimine les objets de l'écran, il est important de réduire au minimum les ressources utilisées. 
Nous retirons chaque balle après 2 secondes de vie. 
Pour ce faire, le nœud Array (Object) est placé et toutes les puces déclenchées sont stockées dans ce tableau à l'aide du nœud Array Add. 
Nous attendons 2 secondes avec le nœud Sleep et appelons le nœud Remove Object. 
Le nœud Array Shift alimente le premier élément du tableau de puces dans le nœud Remove Object et supprime également cet élément du tableau lui-même.

![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/tanks/10.jpg)

 * [C'est tout - n'hésitez pas à expérimenter davantage!  Obtenez le mélange complet pour ce tutorial:](https://github.com/armory3d/armory_tutorials)