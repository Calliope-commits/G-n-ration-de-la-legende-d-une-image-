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


![image](https://github.com/Calliope-commits/Generation-de-la-legende-d-une-image-/assets/61286710/1fae94ee-474e-43bb-a572-245a2adb3901)

## Présentation du modèle : entrainement 

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

![image](https://github.com/Calliope-commits/Generation-de-la-legende-d-une-image-/assets/61286710/7775023a-4eb9-4502-ae03-93037b3ead3f)

Prédiction avec Greedy Search : "a man in a white shirt is
standing in front of a man in a black shirt " ,**bleu score : 65%**

Préciction avec Beam Search : “a group of people are sitting on
a bench with a stick in his mouth” , **bleu score k=3 : 51%**





