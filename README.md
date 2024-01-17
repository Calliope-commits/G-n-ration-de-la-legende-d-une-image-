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
- Entraîné sur Image Net 
- 25 millions de paramètres 
- Extraction des vecteurs des images, taille du format : (1,2048)
- On retire la couche de softmax (il n’y a pas de classification)

![image](https://github.com/Calliope-commits/Generation-de-la-legende-d-une-image-/assets/61286710/46e443e6-e03c-4a36-9ecb-93eeb5fb6ad2)

## Présentation du modèle : encodage du texte 
-Glove intègre la co occurrence
globale des mots pour obtenir
des vecteurs de mots
-Des relations sémantiques
entre les mots sont dérivées
-Avec un vocabulaire de 1660
mot au final : on obtient une
matrice de (1660 , 220)

![image](https://github.com/Calliope-commits/Generation-de-la-legende-d-une-image-/assets/61286710/02261af2-94fe-4155-9ff0-5f9fccefe7cb)




