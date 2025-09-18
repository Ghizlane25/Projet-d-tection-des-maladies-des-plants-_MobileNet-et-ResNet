# Projet-d-tection-des-maladies-des-plants-_MobileNet-et-ResNet
 
##Description

Ce projet a pour objectif de développer un système de classification automatique des maladies des plantes à partir d’images de feuilles. Il compare deux architectures CNN pré-entraînées :

ResNet-50 : modèle profond et précis.

MobileNetV2 : modèle léger, rapide et optimisé pour les appareils mobiles.

L’approche repose sur le transfer learning, appliqué au New Plant Diseases Dataset (87 000+ images, 38 classes).

Dataset
Nom : New Plant Diseases Dataset

Taille : 87 900 images (RGB, 256×256)

Classes : 38 (maladies + plantes saines)

##Split :

Entraînement : 55 356

Validation : 7 909

Test : 7 030

##Exemple de classes :

Apple___Apple_scab

Corn___Common_rust

Potato___Late_blight

Tomato___Yellow_Leaf_Curl_Virus

Healthy samples (plantes saines)

##Data Augmentation appliquée :

Flip horizontal aléatoire

Rotation (±20°)

Zoom aléatoire

Ajustement de contraste

##Méthodologie

Prétraitement des images (224x224, normalisation).

Utilisation des modèles pré-entraînés (ResNet50, MobileNetV2 sur ImageNet).

Ajout d’un classifieur dense : GlobalAveragePooling + Dense + Softmax.

Entraînement avec Adam (lr=1e-5, batch=32, epochs=10).

Évaluation avec accuracy, F1-score, matrice de confusion, ROC-AUC.

Résultats
Modèle Accuracy (test) F1-score AUC Remarques ResNet-50 79 % 0.78 0.993 Bonne discrimination mais surapprentissage MobileNetV2 84.5 % 0.84 0.996 Plus léger, robuste, adapté aux mobiles

##Analyse :

ResNet50 → meilleure profondeur mais plus lourd et sujet à l’overfitting.

MobileNetV2 → compromis idéal rapidité / précision, adapté aux applications mobiles.
