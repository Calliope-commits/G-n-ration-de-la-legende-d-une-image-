# Generation-de-la-legende-d-une-image-

Modélisation de systèmes de vision : Génération de la légende d’une image

## Contexte : 
● Génération de la légende d’une image, image captioning : tâche cible(
downstream taks )

● Traitement de données multimodales

● Intéressant pour différents cas de figures :
 - améliorer l’expérience utilisateur
 - génération automatique de description visuelle


## Présentation du modèle : encodage de l'image 
● Entraîné sur Image Net 

● 25 millions de paramètres 

● Extraction des vecteurs des images, taille du format : (1,2048)

● On retire la couche de softmax (il n’y a pas de classification)

