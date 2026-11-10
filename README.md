# Deep Learning 2026-2027

Travaux pratiques du cours de Deep Learning, 5e année, ELISA Aerospace. Chaque TP s'ouvre directement dans Google Colab : aucune installation n'est nécessaire.

## Les TP

| TP | Sujet | Ouvrir |
|---|---|---|
| [TP CNN](#tp-cnn--ouvrir-la-boîte-noire-dun-réseau-convolutif) | Ouvrir la boîte noire d'un réseau convolutif | [![Ouvrir dans Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ArtificialIntelligenceModules/DeepLearning-2026-2027/blob/main/TP_CNN/TP_CNN_2026.ipynb) |
| [TP RNN](#tp-rnn--où-sera-lavion-dans-2-minutes-) | Où sera l'avion dans 2 minutes ? Prédire des trajectoires réelles avec des réseaux récurrents | [![Ouvrir dans Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ArtificialIntelligenceModules/DeepLearning-2026-2027/blob/main/TP_RNN/TP_RNN_2026.ipynb) |

**Pour chaque TP**
1. Cliquez sur le bouton **Open in Colab** du TP.
2. Activez le GPU : menu *Exécution → Modifier le type d'exécution → T4 GPU*.
3. Exécutez les cellules dans l'ordre. Les données sont téléchargées automatiquement à la cellule 0.2.

Pensez à enregistrer une copie du notebook dans votre Drive (*Fichier → Enregistrer une copie dans Drive*) : sinon vos réponses sont perdues à la fermeture de l'onglet.

## TP CNN · Ouvrir la boîte noire d'un réseau convolutif

[![Ouvrir dans Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ArtificialIntelligenceModules/DeepLearning-2026-2027/blob/main/TP_CNN/TP_CNN_2026.ipynb)

Ce TP ouvre un vrai CNN sur les photos du cours. Il regarde ce que calcule chaque couche, compare trois façons d'apprendre une tâche avion / drone / oiseau, cherche où le réseau regarde et comment le tromper, puis passe à la détection avec YOLO.

**Travailler hors ligne ou sans Colab** : téléchargez [`TP_CNN_2026.zip`](https://github.com/ArtificialIntelligenceModules/DeepLearning-2026-2027/releases/download/tp-cnn/TP_CNN_2026.zip) (environ 10 Mo). Il contient le notebook et le dossier `data/`.

| Contenu de `data/` | Utilisé au bloc |
|---|---|
| `photos/` : A380, formation A320, masque de l'A380, patch adversarial | 1, 2, 4, 5 |
| `aero3/` : 900 photos avion / drone / oiseau (`train/`, `val/`) | 3, 4 |
| `curves/` : courbes d'entraînement de secours | 3 |

## TP RNN · Où sera l'avion dans 2 minutes ?

[![Ouvrir dans Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ArtificialIntelligenceModules/DeepLearning-2026-2027/blob/main/TP_RNN/TP_RNN_2026.ipynb)

Ce TP apprend à des réseaux récurrents à prédire la position d'un avion 2 minutes à l'avance, sur 2 825 arrivées réelles à Toulouse-Blagnac. Il ouvre la cellule RNN, compare la mémoire du RNN, du GRU et du LSTM, puis génère la suite de la trajectoire avec un encodeur-décodeur. Chaque binôme suit son propre vol : entrez votre numéro de binôme à la cellule 0.3.

**Travailler hors ligne ou sans Colab** : téléchargez [`TP_RNN_2026.zip`](https://github.com/ArtificialIntelligenceModules/DeepLearning-2026-2027/releases/download/tp-rnn/TP_RNN_2026.zip) (environ 11 Mo). Il contient le notebook et le dossier `data/`.

| Contenu de `data/` | Utilisé au bloc |
|---|---|
| `lfbo_arrivees.npz` : les 2 825 arrivées, un point toutes les 10 s, découpées en train / val / test par vol | tous |
| `fond_large.jpg`, `fond_zoom.jpg` : photographies aériennes IGN autour de l'aéroport | toutes les cartes |
| `secours/` : poids déjà entraînés, si Colab est trop lent | 2, 3, 4 |

## Crédits

**TP CNN**
- Photo de l'A380 : Axwel (Flickr), licence [CC BY 2.0](https://creativecommons.org/licenses/by/2.0/), via [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Airbus_A380_blue_sky.jpg).
- Image de la famille A320 en formation : © Airbus (Computer Graphic by i3m), utilisée avec l'autorisation d'Airbus pour ce cours. Elle n'est pas sous licence libre et ne doit pas être réutilisée hors de ce TP.
- Jeu avion / drone / oiseau : échantillon de trois jeux Kaggle de nelyg8002000 ([avions](https://www.kaggle.com/datasets/nelyg8002000/commercial-aircraft-dataset), [drones](https://www.kaggle.com/datasets/nelyg8002000/uav-detection-dataset-images), [oiseaux](https://www.kaggle.com/datasets/nelyg8002000/birds-flying)), licence CC0.
- Modèles : ResNet-50 pré-entraîné de [torchvision](https://pytorch.org/vision/stable/models.html) ; [YOLO11n](https://docs.ultralytics.com/models/yolo11/) d'Ultralytics, licence AGPL-3.0, dont les poids sont téléchargés au premier lancement.

**TP RNN**
- Trajectoires : X. Olive et L. Basora (2019), *Reference data sets for detection and identification of significant events in historical aircraft trajectory data*, figshare, [doi:10.6084/m9.figshare.11406735](https://doi.org/10.6084/m9.figshare.11406735), licence MIT. Données ADS-B d'origine : [The OpenSky Network](https://opensky-network.org).
- Fonds de carte : photographies aériennes [IGN](https://geoservices.ign.fr), Licence Ouverte Etalab 2.0.
