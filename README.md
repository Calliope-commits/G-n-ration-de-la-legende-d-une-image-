# Generation-de-la-legende-d-une-image-

Modélisation de systèmes de vision : Génération de la légende d’une image
Dataset : Flickr8k
Dans ce repo vous trouverez un notebook , un état de l'art, ainsi qu'un site web qui présente en détail le projet.

## Contexte : 
● Génération de la légende d’une image, image captioning : tâche cible(
downstream taks )         
● Traitement de données multimodales             
● Intéressant pour différents cas de figures :
 - améliorer l’expérience utilisateur
 - génération automatique de description visuelle

## Présentation du modèle : encodage de l'image 
- Entraîné sur Image Net 
- 25 millions de paramètres 
- Extraction des vecteurs des images, taille du format : (1,2048)
- On retire la couche de softmax (il n’y a pas de classification)

![image](https://github.com/Calliope-commits/Generation-de-la-legende-d-une-image-/assets/61286710/46e443e6-e03c-4a36-9ecb-93eeb5fb6ad2)

## Présentation du modèle : encodage du texte 
Dans le dataset Flickr8K, chaque image présente 5 légendes, qui constituent la vérité terrain, comme nous pouvons le voir sur la figure :

![image](https://github.com/Calliope-commits/Generation-de-la-legende-d-une-image-/assets/61286710/59e8148e-bec7-4c4b-ae56-6e5ed4e3a423)


-Glove intègre la co occurrence
globale des mots pour obtenir
des vecteurs de mots

-Des relations sémantiques
entre les mots sont dérivées

-Avec un vocabulaire de 1660
mot au final : on obtient une
matrice de (1660 , 220)


![image](https://github.com/Calliope-commits/Generation-de-la-legende-d-une-image-/assets/61286710/1fae94ee-474e-43bb-a572-245a2adb3901)

Le concept sous-jacent qui distingue l'homme de la femme, c'est-à-dire le genre, peut être spécifié de manière équivalente par diverses autres paires de mots, comme roi et reine ou frère et sœur.



## Présentation du modèle : entrainement 

Pour rappel notre jeu de données est divisé en trois parties :

-Entrainement : 6000 images     
-Validation : 1000 images      
-Test : 1000 images       

Nous avons réalisé une série d'entrainement, tout en comparant les valeurs de perte des données d'entrainement et de validation, nous avons établis un modèle avec les hyperparamètres suivants

Hyperparamètres :
-Optimizer : Adam       
-Taille du batch : 3          
-Dropout  : 0.5         
-Nombre d'epoch : 7        
-Learning rate : 0.001        
-Momentum : 0.99     

![image](https://github.com/Calliope-commits/Generation-de-la-legende-d-une-image-/assets/61286710/e870c867-7eff-4e94-be78-b63631b379d3)

## Evaluation : Bleu Score 
● Indicateur de performance

● Calcul la proportion de
n-grammes (séquence de mot de longueur n)

● Mesure la similitude entre une
phrase générée par le modèle et la
vérité terrain


**Beam Search (k=3) : 52.13%**

**Greedy Search : 48.41**

## Illustration avec un exemple 

![image](https://github.com/Calliope-commits/Generation-de-la-legende-d-une-image-/assets/61286710/51389b5b-9b06-46cc-be9a-c7282350cc25)


Prédiction avec Greedy Search : "a black dog is jumping up to catch a frisbee"

Préciction avec Beam Search : “a black dog and a black dog play with a redball in the grass" 





