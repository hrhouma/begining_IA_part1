# (PRATIQUE#5) PROJET #2 Original MNIST

Généré automatiquement par Colab.

Le fichier original se trouve à l'adresse suivante :
[Colab](https://colab.research.google.com/drive/13B7oPTQ5OEOeLiFdA_nA_UVMU2p7t6zd)


# Tâche 1 : Introduction

Bienvenue dans la classification d'images basiques avec TensorFlow.

Ce graphique décrit visuellement le problème que nous tentons de résoudre. Nous voulons créer et entraîner un modèle qui prend une image de chiffre écrit à la main comme entrée et prédit la classe de ce chiffre.

![Classification de chiffres écrits à la main](https://drive.google.com/uc?export=view&id=1OZMTtcN1l-xVu8YXtU9qAUUHBs6ZmYzt)

# 1 - Importation de TensorFlow

```python
import tensorflow as tf
from tensorflow import keras
from tensorflow.keras.callbacks import TensorBoard
import os
import numpy as np
import matplotlib.pyplot as plt
from datetime import datetime
```

- Voici une description détaillée de chaque librairie importée :

1. **tensorflow** : TensorFlow est une bibliothèque open-source développée par Google pour le machine learning et le deep learning. Elle fournit des outils pour la création et l'entraînement de réseaux de neurones, ainsi que des primitives pour l'optimisation et le calcul sur des tenseurs.

2. **keras** : Keras est une API haut niveau pour la construction de réseaux de neurones. Elle permet de créer, entraîner et déployer des modèles de manière rapide et intuitive. Depuis TensorFlow 2.0, Keras est intégré nativement à TensorFlow, ce qui permet d'utiliser les fonctionnalités de TensorFlow tout en bénéficiant de la simplicité de l'API Keras.

3. **TensorBoard** : TensorBoard est un outil de visualisation fourni par TensorFlow. Il permet de visualiser les graphes computationnels, de suivre la progression de l'entraînement des modèles, d'analyser les performances, etc. L'import de `TensorBoard` ici indique probablement l'intention d'utiliser TensorBoard pour le suivi de la formation des modèles.

4. **os** : Le module `os` fournit des fonctionnalités liées au système d'exploitation. Il est utilisé ici pour interagir avec le système de fichiers, comme la création de répertoires ou la manipulation de chemins de fichiers.

5. **numpy** : NumPy est une bibliothèque très populaire pour le calcul numérique en Python. Elle fournit des structures de données telles que les tableaux multidimensionnels (ndarray), ainsi que des fonctions pour effectuer des opérations mathématiques sur ces tableaux.

6. **matplotlib.pyplot** : Matplotlib est une bibliothèque de visualisation en Python. Le sous-module `pyplot` fournit une interface similaire à celle de MATLAB pour la création de graphiques. Il est couramment utilisé pour tracer des courbes, des histogrammes, des diagrammes en barres, etc.

7. **datetime** : Le module `datetime` fournit des classes et des fonctions pour manipuler des dates et des heures en Python. Il est utilisé ici probablement pour travailler avec des objets de date et d'heure, peut-être pour enregistrer des horodatages ou pour générer des noms de fichiers uniques.

# Résumé: 
- ce code importe différentes bibliothèques nécessaires pour le développement et l'entraînement de modèles de machine learning avec TensorFlow, ainsi que pour la manipulation de données, la visualisation et la gestion du système de fichiers.

# Tâche 2 : Le Dataset

# 2 - Importation de MNIST

```python
# Chargement des données MNIST
fashion_mnist_data = keras.datasets.mnist
(x_train, y_train), (x_test, y_test) = fashion_mnist_data.load_data()
```


# Tâche 3 : Encodage One Hot

Après cet encodage, chaque étiquette sera convertie en une liste de 10 éléments où l'élément à l'indice correspondant à la classe sera mis à 1, le reste à 0.

# 3 -  Encodage des étiquettes

```python
from tensorflow.keras.utils import to_categorical

y_train_encoded = to_categorical(y_train)
y_test_encoded = to_categorical(y_test)
```

# Tâche 4 : Réseaux Neuronaux

# 4 - Équations Linéaires

![Neurone simple](https://drive.google.com/uc?export=view&id=1X53G3QBhSBZsCHchyvgOsRrczmh0IoXY)

Le graphique ci-dessus représente simplement l'équation :

$$
y = w1 * x1 + w2 * x2 + w3 * x3 + b
$$

où `w1, w2, w3` sont appelés les poids et `b` est un terme d'interception appelé biais. L'équation peut également être *vectorisée* comme ceci :

$$
y = W . X + b
$$

où `X = [x1, x2, x3]` et `W = [w1, w2, w3].T`. .T signifie *transposé*. Ceci est nécessaire car nous voulons que le produit scalaire nous donne le résultat souhaité, c'est-à-dire `w1 * x1 + w2 * x2 + w3 * x3`. Cela nous donne la version vectorisée de notre équation linéaire.

Un approche simple et linéaire pour résoudre le problème de classification d'images de chiffres écrits à la main - pourrait-elle fonctionner ?

![Neurone simple avec 784 caractéristiques](https://drive.google.com/uc?export=view&id=1usn-vb6FOIOkDuKOimQuFDgGwVSckG5W)



### Réseaux Neuronaux

![Réseau neuronal avec 2 couches cachées](https://drive.google.com/uc?export=view&id=1-P9jSpGodu2fl-cvEXun3_zQytJDH5Yn)

Ce modèle est bien plus susceptible de résoudre le problème car il peut apprendre des mappings de fonctions plus complexes pour les entrées et les sorties de notre ensemble de données.

## Tâche 5 : Prétraitement des Exemples

# 5 - Transformation des tableaux N-dimensionnels en Vecteurs

```python
import numpy as np

x_train_reshaped = np.reshape(x_train, (60000, 784))
x_test_reshaped = np.reshape(x_test, (10000, 784))
print('Forme de x_train_reshaped', x_train_reshaped.shape)
print('Forme de x_test_reshaped', x_test_reshaped.shape)
```



# 5.1 - Affichage des valeurs des pixels

```python
print(set(x_train_reshaped[0]))
```

# 5.2 -  Normalisation des données

```python
x_mean = np.mean(x_train_reshaped)
x_std = np.std(x_train_reshaped)

epsilon = 1e-10

x_train_norm = (x_train_reshaped - x_mean) / (x_std + epsilon)
x_test_norm = (x_test_reshaped - x_mean) / (x_std + epsilon)
```



# 5.3 - Affichage des valeurs des pixels normalisés

```python
print(set(x_train_norm[0]))
```

## Tâche 6 : Création d'un Modèle

# 6.1 - Création du Modèle

```python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense

model = Sequential([
    Dense(128, activation='relu', input_shape=(784,)),
    Dense(128, activation='relu'),
    Dense(10, activation='softmax')
])
model.summary()
```

# 6.2 -Fonctions d'Activation

La première étape dans le noeud est la somme linéaire des entrées :

$$
Z = W . X + b
$$

La deuxième étape dans le noeud est la sortie de la fonction d'activation :

$$
A = f(Z)
$$

### Représentation graphique d'un noeud où les deux opérations sont

![ReLU](https://drive.google.com/uc?export=view&id=1QYbrKPd5_4Lz89q3faOn0ZE-JPbAljV4)

# 6.3 - Compilation du Modèle

```python
model.compile(optimizer='adam', loss='categorical_crossentropy', metrics=['accuracy'])
```

## Tâche 7 : Entraînement du Modèle

# 7.1 - Entraînement du Modèle

```python
model.fit(x_train_norm, y_train_encoded, epochs=3)
```

# 7.2 - Évaluation du Modèle

```python
loss, accuracy = model.evaluate(x_test_norm, y_test_encoded)
print('Précision sur le jeu de test :', accuracy * 100)
```



## Tâche 8 : Prédictions

# 8.1 - Prédictions sur le jeu de test

```python
preds = model.predict(x_test_norm)
print('Forme des prédictions :', preds.shape)
```

# 8.2 - Affichage des Résultats

```python
import matplotlib.pyplot as plt
import numpy as np

plt.figure(figsize=(12, 12))
start_index = 0

for i in range(25):
    plt.subplot(5, 5, i+1)
    plt.grid(False)
    plt.xticks([])
    plt.yticks([])

    pred = np.argmax(preds[start_index+i])
    gt = y_test[start_index+i]
    col = 'g' if pred == gt else 'r'

    plt.xlabel('i={}, préd={}, vr={}'.format(start_index+i, pred, gt), color=col)
    plt.imshow(x_test[start_index+i], cmap='binary')

plt.show()
```

# 8.3 - Affichage d'un Graphique de Prédictions

```python
plt.plot(preds[8])
plt.show()
```

- Ce README décrit de manière détaillée chaque étape, depuis l'importation des données jusqu'à la prédiction, en passant par la création et l'entraînement du modèle. Cela aide à comprendre comment construire, entraîner et évaluer un modèle de classification d'images avec TensorFlow, en utilisant le dataset MNIST.




# (IMPORTANT) - ANNEXES et Points de discussion

## 1. Description des librairies 📚
- Dans ce projet, nous utilisons plusieurs librairies pour le développement et l'entraînement de modèles de machine learning avec TensorFlow.
- Voici une brève description de chacune d'entre elles :
  
```python
import tensorflow as tf               # TensorFlow, une bibliothèque de machine learning et de deep learning.
from tensorflow import keras          # Keras, une API haut niveau pour la création de réseaux de neurones.
from tensorflow.keras.callbacks import TensorBoard  # TensorBoard, un outil de visualisation pour suivre l'entraînement des modèles.
import os                             # Le module os, pour interagir avec le système de fichiers.
import numpy as np                    # NumPy, une bibliothèque pour le calcul numérique.
import matplotlib.pyplot as plt       # Matplotlib, une bibliothèque de visualisation.
from datetime import datetime         # Le module datetime, pour manipuler des dates et des heures.
```

## 2. Données d'entraînement et de test 📊
- Il est essentiel de comprendre la taille et les types de données d'entraînement et de test pour un bon prétraitement des données.

## 3. Encodage One Hot vs alternative Categorical 🎨
- L'encodage One Hot est souvent utilisé pour représenter des catégories dans les données.
- Alternativement, l'encodage catégorique peut être utilisé.

## 4. Équation linéaire et biais 📈
- Une explication de l'équation linéaire et du rôle des biais dans les modèles linéaires.

## 5. Transformation des tableaux N-dimensionnels en vecteurs 🔄
- Utilisation des fonctions `reshape` ou la couche d'entrée `Flatten` pour transformer des tableaux N-dimensionnels en vecteurs.

## 6. Bonnes pratiques 🌟
- Affichage des images, types de données, et vérification continue du développement.

## 7. Normalisation vs Standardisation des données 📊
- Comparaison de la normalisation et de la standardisation des données, avec des exemples dans deux projets différents.

## 8. Construction du modèle 🏗️
- Comparaison entre deux approches de construction de modèles dans deux projets distincts.
- Comparaison entre les deux approches dans le projet 1 et projet 2.

## 9. Fonctions d'activation ⚡
Exploration des différentes fonctions d'activation utilisées dans les couches des réseaux neuronaux.

## 10. Paramètre batch_size et concept des hyperparamètres 🚀
- Utilisation du paramètre `batch_size` dans la compilation et l'entraînement des modèles, avec une explication du concept des hyperparamètres.

## 11. Accuracy sur les données de Test ✅
Explication du concept d'accuracy sur les données de test, avec du code illustratif.


# (IMPORTANT) Points de discussion


1 - description des librairies  

2 - Données d'entrainement et de test, importance de voir la taille de vos données, ainsi que les types de vos données (prétraitement) 

3 - Encodage One Hot sinon alternative Categorical 

4 - C'est quoi équalition linéaire et les biais (udem exemple) 

5 - Nécesssité de transformer des tableaux N-dimensionnels en Vecteurs soir en utilisant la fonction reshape ou Flatten dans l'autre code 

6 - Bonne pratiques : affichage des images , des types de données , vérification à fur et à mesure du développement.  

7 - Normalisation vs Standardisation des données (Nécessité pour un algorithme IA + Les exemples dans les 2 projets projet1 normalisation avec un code simple et projet2 standadisation bas niveau  avec un code plus compliqué - comparaison des codes) 

8 - Construction du modèle (comparaison entre les deux approches dans le projet 1 et projet 2) 

9  -Fonctions d'activations  

10 - Pour la compilation et le fonction fit, on peut ajouter le paramètre batch_size 32, 64 , (ce qui explique le 1875 affiché alors que nous avons 60.0000 images ==> Concept des hyperparamètres) 

11 - Concepts d'accuracy sur les données de Test + code


# Annexe 1  (bias) : Comprendre le Biais dans les Réseaux Neuronaux

Expliquons le concept de biais (bias) dans les réseaux neuronaux:


## Introduction

Lorsqu'on parle de réseaux neuronaux, il est courant d'entendre parler de poids (weights) et de biais (bias). Si vous êtes familier avec les pixels d'une image comme entrées d'un modèle, et les poids comme coefficients qui ajustent l'importance de ces entrées, le concept de biais peut sembler un peu moins intuitif. Dans ce document, nous allons explorer ce qu'est le biais, pourquoi il est crucial dans les modèles d'apprentissage automatique, et comment il fonctionne avec des analogies simples et des exemples de la vie réelle.

## Qu'est-ce que le Biais?

Le biais est un terme additionnel dans les modèles de machine learning, notamment dans les réseaux neuronaux, qui permet au modèle d'ajuster les prédictions à des valeurs plus réalistes dans le contexte des données. C'est un peu comme un ajustement de base qui est ajouté à la prédiction.

### Exemple de la Vie Réelle

Imaginons que vous êtes professeur et que vous devez prédire la note finale d'un étudiant basée sur le nombre d'heures d'étude. Votre modèle initial pourrait simplement multiplier le nombre d'heures par un certain poids pour prédire la note. Cependant, si les notes ont tendance à inclure un bonus de participation de 10 points que tout le monde reçoit, votre modèle prédira systématiquement des notes inférieures de 10 points. Le biais, dans ce cas, serait ce bonus de 10 points ajouté à la prédiction de base pour aligner le modèle avec la réalité observée.

## Pourquoi le Biais est-il Important?

Sans biais, votre modèle peut être forcé à partir de l'hypothèse irréaliste que lorsque toutes les entrées sont à zéro, la sortie doit aussi être zéro. Le biais donne à votre modèle plus de flexibilité : il lui permet de commencer à prédire à partir d'un point différent de zéro.

### Exemple de Réglage du Biais

Prenons un exemple simple de chauffage d'une maison. Si vous créez un modèle pour prédire la quantité de chaleur nécessaire pour chauffer une maison en fonction de la température extérieure, les poids ajusteront l'importance de la température extérieure, mais le biais pourrait représenter le chauffage minimal nécessaire, même lorsque la température extérieure est agréable. Sans ce biais, votre modèle pourrait sous-estimer le besoin de chauffage lors des jours légèrement frais.

## Les Poids (Weights)

Les poids dans un réseau neuronal sont des facteurs qui pondèrent l'importance des entrées reçues. Si nous revenons à l'exemple de l'étudiant, le poids pourrait représenter combien chaque heure d'étude améliore la note de l'étudiant. Un poids plus élevé signifie que chaque heure supplémentaire d'étude est jugée plus influente sur la note finale.

## Conclusion

Le biais est un concept crucial qui aide les modèles d'apprentissage automatique à mieux correspondre à la réalité complexe des données qu'ils cherchent à modéliser. Il ajuste la sortie du modèle indépendamment des entrées, permettant ainsi des prédictions plus précises et plus adaptées. En ajoutant le biais, nous ne supposons pas que nos prédictions commencent à partir de zéro, mais plutôt d'un point qui a du sens dans le contexte des données réelles.


# Annexe 3 - code final

- inclure ceci  : [<script src="https://gist.github.com/hrhouma/65357cde6c166b83ca869fdf3a44ab4e.js"></script>](https://gist.github.com/hrhouma/65357cde6c166b83ca869fdf3a44ab4e)
- {%gist 65357cde6c166b83ca869fdf3a44ab4e%}
- git clone https://gist.github.com/65357cde6c166b83ca869fdf3a44ab4e.git



