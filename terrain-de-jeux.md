![](https://camo.githubusercontent.com/3a65632873f21bd9e74904ae40cfd239df80662e/687474703a2f2f696d672e796f75747562652e636f6d2f76692f4835796c536654664e67382f302e6a7067)

Ce didacticiel vous guide à travers les bases de d'Armory.  Nous créerons une scène de type terrain de jeu, présentant les fonctionnalités essentielles étape par étape.

### Bonjour le monde

Utilisez ce [fichier blend](https://github.com/armory3d/armory_tutorials/releases) pour ce tutoriel. 

Récuperez ce [tutoriel d'installation](https://github.com/armory3d/armory/wiki/setup) ,Ouvrez Blender, enregistrez le projet et appuyez sur Armory Player - Lancer avec la touche (F5) pour le jouer dans la fenêtre.

Dans le panneau Armory Player, vous pouvez:

* Sélectionnez le Runtime à utiliser:

                * Krom pour jouer en lecteur autonome.
                * Navigateur pour le déploiement HTML5.

* Sélectionnez un mode Camera:

                * Scène : pour démarrer le jeu à partir du point de la caméra de scène active.
                * Viewport : pour démarrer le jeu depuis la vue de la fenêtre. 
Ceci est utile pour un aperçu rapide de la scène car il vous permet également de contrôler la caméra.

    
* Spécifiez une scène à lancer ou laissez vide pour utiliser la scène active actuelle.

En outre, vous pouvez modifier les dimensions dans l'onglet Propriétés - Sortie pour la taille de la fenêtre. 
Pour exécuter en plein écran, sélectionnez Projet Armurerie - Fenêtre - Mode - Plein écran.

![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/playground/0.jpg)

### Objets

Nous commencerons par quelques notions de base de Blender sur la manière de manipuler les objets dans scène:

* Dans la vue 3D, appuyez sur F3 et tapez Ajouter un plan pour créer un objet plan (ou faites Ajouter - Maillage - Plan à partir de l'en-tête de la vue 3D).
    
* Appuyez sur S pour agrandir le plan, R pour faire pivoter ou G pour saisir et translater.
    
* Supprimez des objets en appuyant sur X.

### Modifiers

Blender a une variété de Modifiers qui appliquent des effets procéduraux sur l'objet actif. 
Sélectionnez le Cube, accédez à l'onglet Modifiers et ajoutez un Modifiers Bevel pour que les bords du cube paraissent polis.

![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/playground/1.jpg)

### Materials

Sélectionnez Cube et basculez vers l'éditeur de shader.  Activez et Utiliser les nœuds.  Vous pouvez désormais modifier la couleur et la rugosité du matériau à l'aide du nœud BSDF Principled par défaut.

![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/playground/2.jpg)

Ensuite, revenez à la vue 3D et sélectionnez le Plan.  Nous voulons y mettre une texture.  Créez un nouveau matériau dans l'onglet Matériau.  Basculez vers l'éditeur de shader comme nous l'avons fait auparavant.

![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/playground/grid_base.png)
![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/playground/grid_rough.png)

Enregistrez les images ci-dessus et glissez-déposez simplement les fichiers sur le canevas du nœud dans Blender.  Connectez les nœuds de texture d'image aux sockets de couleur de base et de rugosité du nœud BSDF à principes.

![](https://github.com/armory3d/armory_wiki_images/raw/master/getting_started/playground/3.jpg)

Suite à ces étapes, une scène de base se dessine déjà.  Appuyez sur F5 pour jouer la scène dans Armory!

![](https://github.com/armory3d/armory_wiki_images/raw/master/getting_started/playground/4.jpg)

### Animation

Créons une animation faisant pivoter le cube. 
Localisez la timeline et passez à l'image 1. Sélectionnez le Cube et appuyez sur I - Rotation pour insérer des images clés pour la rotation. 
Ensuite, passez à l'image 60 de le timeline. 
Avec le Cube sélectionné, appuyez sur R pour le faire pivoter suivant un degré souhaitée et appuyez à nouveau sur I - Rotation.

![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/playground/5.jpg)

### Lumières

Sélectionnez l'objet lumière dans la hiérarchie et passez à l'onglet Données d'objet. "l'outliner" 
Vous pouvez définir le type de lumière et modifier la couleur et l'intensité de la lumière.

![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/playground/6.jpg)

### Environnement

Les nœuds de mondiaux sont utilisés pour configurer l'environnement. 
Basculez vers le Shader Editor - World pour accéder aux nœuds. 
Dans ce didacticiel, nous utilisons le nœud Sky Texture pour rendre le ciel procédural. 
Si nous devions ajouter une carte d'environnement, nous utiliserions le nœud Texture d'environnement couplé au fichier .hdr.

![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/playground/7.jpg)

### La physique

Avec l'objet sélectionné, accédez à l'onglet Physique et appuyez sur le bouton Corps rigide."Rigid Body" 
Définissez la forme souhaitée représentant l'objet dans le panneau Collision.

Dans le panneau Corps rigide, définissez la masse et le type de l'objet:

* Sélectionnez Actif pour les objets librement affectés par la physique.
* Sélectionnez Passif pour les objets statiques ou animés sur la timeline.

![](https://github.com/armory3d/armory_wiki_images/raw/master/getting_started/playground/8.jpg)

### Importation d'actifs "d'Asset"

Avec Blender, nous pouvons facilement importer des formats d'actifs courants.

 * Sélectionnez le Fichier - Importer pour importer les formats de fichier.
    
 * Sélectionnez le Fichier - Ajouter pour importer des objets à partir d'autres fichiers .blend.
    
 * Sélectionnez le Fichier - Lien pour lier des objets à partir d'autres fichiers .blend.

### Nœuds logiques "Logic Nodes"

Les nœuds logiques fournissent un moyen visuel de créer des scènes interactives. 
Lorsque vous construisez votre projet, les arborescences de nœuds créées sont automatiquement compilées en scripts (cela peut conduire à des avertissements en fonction du nom de l'arborescence de nœuds. Si vous voyez un tel avertissement, veuillez vous y [référer](https://github.com/armory3d/armory/wiki/troubleshooting#warning-trait-names-differ)

Le système se compose de 5 catégories essentielles:

 * Événements - nœuds où l'exécution commence, déclenchés par l'événement souhaité
 * Actions - une fois qu'un événement est déclenché, ces nœuds agissent
 * Logique - nœuds utilisés pour contrôler le flux d'exécution, à l'aide de branchements, de boucles, de portes.
 * Variables - nœuds utilisés pour stocker des données dans une arborescence logique
 * Valeurs - nœuds utilisés pour récupérer des données à partir d'autres objets

Nous animerons le cylindre de manière procédurale à l'aide de nœuds logiques. 
Basculez vers la zone de l'éditeur logique et appuyez sur Nouveau pour créer une nouvelle arborescence de nœuds.

Vous pouvez parcourir tous les nœuds disponibles via l'élément de menu Ajouter, ou appuyez simplement sur Maj A pour commencer la recherche.

   * Recherchez le nœud On Update et placez-le. 
Il s'agit d'un nœud d'action qui est appelé à chaque image.
   * Connectez-le au nœud Set Location.
   * Ajoutez un nœud Vector et connectez-le au nœud Set Location. 
Chaque image, l'emplacement du cylindre sera défini sur ce vecteur.
   * Pour l'emplacement X, ajoutez le nœud Math et définissez-le sur Sine.
   * Ajoutez le nœud Time pour piloter le nœud sinus.
   * Ajoutez un autre nœud Math, en mettant à l'échelle la sortie sinusoïdale.
   * Nous garderons les emplacements Y et Z inchangés.

Chaque arbre de nœuds doit être attaché à un objet. 
Sélectionnez Cylindre et créez un nouveau trait de nœuds dans Propriétés - Objet - Traits d'Armory. 
Entrez notre nouvelle arborescence de nœuds en tant qu'entrée d'arbre.

![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/playground/9.jpg)

Remarque: pour voir la sortie du nœud d'impression, activez Armory Project - Flags - Debug Console.

### Scripts Haxe

Nous pouvons programmer les traits d'objet directement en utilisant le langage de programmation Haxe. 
Créons un trait qui génère une boîte après avoir appuyé sur une touche.

Tout d'abord, créez un cube et nommez-le "Box". 
Activez Corps rigide et Actif pour le cube dans l'onglet Physique.

Créez un objet vide dans la scène (F3 - Ajouter vide). 
L'emplacement de cet objet servira de point d'apparition. 
Créez un nouveau trait Haxe dans Propriétés - Objet - Traits d'Armory. 
Appuyez sur le bouton Nouveau script.

Ensuite, appuyez sur Modifier le script pour ouvrir le fichier de script dans Kode Studio. 
Kode Studio est un éditeur de code dédié qui inclut la complétion de code et la prise en charge du débogage.

package arm;

import iron.object.Object;
import iron.system.Input;
import iron.Scene;
import armory.trait.physics.RigidBody;

class SpawnBox extends iron.Trait {
	public function new() {
		super();
		// We want to get notified every frame
		notifyOnUpdate(update);
	}

	function update() {
		// f key was pressed
		if (Input.getKeyboard().started("f")) {
			// Spawn Box object
			Scene.active.spawnObject("Box", null, boxSpawned);
		}
	}

	// Box just got spawned
	function boxSpawned(o:Object) {
		// Translate cube to the location of empty object
		var traitOwner = object;
		o.transform.loc.setFrom(traitOwner.transform.loc);
		// Box object has a rigid body trait
		// Notify physics system to take new location into effect!
		o.getTrait(RigidBody).syncTransform();
	}
}

![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/playground/10.jpg)

### Scripts groupés

Armory est livré avec un ensemble de scripts pré-créés. 
Semblable au script normal, le script groupé peut être attaché à un objet en tant que trait. 
Dans ce tutoriel, nous utiliserons le trait PhysicsDrag. 
Lorsque ce trait est attaché à un objet compatible avec la physique, il nous permet de faire glisser cet objet à l'aide de la souris.

Toile de l'interface utilisateur "UI Canvas"

Pour créer une interface de jeu, un outil ArmorUI dédié est utilisé.

Outre les objets, la scène elle-même peut également contenir des traits. 
C'est un bon ajustement pour les caractéristiques de l'interface utilisateur. 
Passez à l'onglet Scène et ajoutez un nouveau trait d'interface utilisateur dans le panneau Traits d'Armory. 
Appuyez sur le bouton Nouvelle toile. 
Ensuite, le bouton Modifier le canevas lancera ArmorUI.

Dans ArmorUI, appuyez sur le bouton Texte pour générer un objet texte. 
Ajustez le texte dans le panneau Propriétés et appuyez sur Enregistrer. 
Si vous lancez le jeu maintenant, le canevas s'affichera.

![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/playground/11.jpg)

### Chemin de rendu "Render Path" 

Armory est alimentée par un système de chemin de rendu programmable. 
Accédez au panneau Rendu - Chemin de rendu de d'Armory pour accéder aux paramètres. 
Lors de la création d'un nouveau chemin de rendu, plusieurs préréglages sont disponibles pour une configuration simple.

Plusieurs chemins de rendu peuvent être créés. 
Lors de l'exportation du projet, vous pouvez utiliser le chemin de rendu qui convient le mieux au matériel cible.

![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/playground/12.jpg)

### Exporter

Lorsque nous sommes prêts à publier notre projet, Properties - Render - Armory Exporter fait le travail.

Vous pouvez créer plusieurs préréglages d'exportation, chacun spécifiant une plate-forme cible, une API graphique, un chemin de rendu et une scène de démarrage. 
Sélectionnez la plate-forme souhaitée et appuyez sur le bouton Publier. 
Une fois terminé, appuyez sur Triangle - Ouvrir le dossier pour afficher les fichiers exportés. 

![](https://raw.githubusercontent.com/armory3d/armory_wiki_images/master/getting_started/playground/13.jpg)

 * Continuer vers le [tutorial Tanks](https://github.com/armory3d/armory/wiki/tanks)

