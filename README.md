# Deep Learning 2026-2027

Travaux pratiques du cours de Deep Learning, 5e année, ELISA Aerospace. Chaque TP s'ouvre directement dans Google Colab : aucune installation n'est nécessaire.

## TP CNN · Ouvrir la boîte noire d'un réseau convolutif

[![Ouvrir dans Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ArtificialIntelligenceModules/DeepLearning-2026-2027/blob/main/TP_CNN/TP_CNN_2026.ipynb)

Ce TP ouvre un vrai CNN sur les photos du cours. Il regarde ce que calcule chaque couche, compare trois façons d'apprendre une tâche avion / drone / oiseau, cherche où le réseau regarde et comment le tromper, puis passe à la détection avec YOLO.

**Pour commencer**
1. Cliquez sur le bouton **Open in Colab** ci-dessus.
2. Activez le GPU : menu *Exécution → Modifier le type d'exécution → T4 GPU*.
3. Exécutez les cellules dans l'ordre. Les données sont téléchargées automatiquement à la cellule 0.2.

**Travailler hors ligne ou sans Colab** : téléchargez [`TP_CNN_2026.zip`](https://github.com/ArtificialIntelligenceModules/DeepLearning-2026-2027/releases/download/tp-cnn/TP_CNN_2026.zip) (environ 10 Mo). Il contient le notebook et le dossier `data/`.

| Contenu de `data/` | Utilisé au bloc |
|---|---|
| `photos/` : A380, formation A320, masque de l'A380, patch adversarial | 1, 2, 4, 5 |
| `aero3/` : 900 photos avion / drone / oiseau (`train/`, `val/`) | 3, 4 |
| `curves/` : courbes d'entraînement de secours | 3 |

Pensez à enregistrer une copie du notebook dans votre Drive (*Fichier → Enregistrer une copie dans Drive*) : sinon vos réponses sont perdues à la fermeture de l'onglet.

## Crédits

- Photo de l'A380 : Axwel (Flickr), licence [CC BY 2.0](https://creativecommons.org/licenses/by/2.0/), via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Airbus_A380_blue_sky.jpg).
- Image de la famille A320 en formation : © Airbus (Computer Graphic by i3m), utilisée avec l'autorisation d'Airbus pour ce cours. Elle n'est pas sous licence libre et ne doit pas être réutilisée hors de ce TP.
- Jeu avion / drone / oiseau : échantillon de trois jeux Kaggle de nelyg8002000 ([avions](https://www.kaggle.com/datasets/nelyg8002000/commercial-aircraft-dataset), [drones](https://www.kaggle.com/datasets/nelyg8002000/uav-detection-dataset-images), [oiseaux](https://www.kaggle.com/datasets/nelyg8002000/birds-flying)), licence CC0.
- Modèles : ResNet-50 pré-entraîné de [torchvision](https://pytorch.org/vision/stable/models.html) ; [YOLO11n](https://docs.ultralytics.com/models/yolo11/) d'Ultralytics, licence AGPL-3.0, dont les poids sont téléchargés au premier lancement.
