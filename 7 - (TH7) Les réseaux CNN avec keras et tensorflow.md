# Partie 1 - Introduction aux Réseaux de Neurones Convolutionnels (CNNs)

Les réseaux de neurones convolutionnels (CNNs) sont des modèles d'apprentissage automatique particulièrement efficaces pour traiter les images. Voici une explication simplifiée des principaux concepts associés aux CNNs.

## 1. Qu'est-ce qu'une image couleur ?

Une image couleur est composée de pixels, et chaque pixel est représenté par trois valeurs correspondant aux trois couleurs primaires de la lumière : rouge (Red), vert (Green), et bleu (Blue). Ces valeurs sont souvent abrégées en RGB. Par exemple, un pixel avec des valeurs (255, 0, 0) sera rouge vif, tandis qu'un pixel avec des valeurs (0, 255, 0) sera vert vif.

## 2. La Convolution

La convolution est une opération mathématique qui permet d'extraire des caractéristiques de l'image. Imaginez que vous avez une petite fenêtre, appelée filtre ou noyau, que vous faites glisser sur l'image. Chaque fois que vous placez le filtre sur une partie de l'image, vous effectuez une multiplication élément par élément entre les valeurs du filtre et les valeurs de l'image sous la fenêtre, puis vous additionnez ces valeurs. Le résultat de cette opération est un seul nombre, et en répétant cette opération pour chaque position du filtre, vous obtenez une nouvelle image, appelée carte de caractéristiques.

## 3. Les Filtres (ou Noyaux)

Les filtres sont des petits tableaux de nombres (souvent 3x3 ou 5x5) qui détectent certaines caractéristiques de l'image, comme les bords ou les textures. Par exemple, un filtre peut être conçu pour détecter les contours verticaux, tandis qu'un autre peut détecter les contours horizontaux.

## 4. Strides

Les strides (ou pas en français) déterminent de combien de pixels vous déplacez le filtre à chaque fois. Par exemple, un stride de 1 signifie que vous déplacez le filtre d'un pixel à la fois, tandis qu'un stride de 2 signifie que vous le déplacez de deux pixels à la fois.

## 5. Padding

Le padding est une technique utilisée pour ajouter des pixels autour de l'image. Cela permet de contrôler la taille de la sortie de la convolution. Par exemple, sans padding, la taille de l'image diminue après chaque convolution. Avec padding, on peut garder la taille de l'image constante.

## 6. Pooling Layer (ou Couches de Pooling)

Le pooling est une opération qui réduit la taille de l'image et aide à extraire les caractéristiques les plus importantes. Le pooling le plus courant est le max pooling, où une fenêtre (par exemple, 2x2) glisse sur l'image et ne conserve que la valeur maximale de chaque fenêtre.

## 7. Dropout

Le dropout est une technique de régularisation utilisée pour éviter le surapprentissage. Pendant l'entraînement, il "éteint" (met à zéro) aléatoirement un certain pourcentage de neurones dans un réseau. Cela force le réseau à ne pas dépendre trop de certains neurones spécifiques et rend le modèle plus robuste.

## 8. Couches Convolutionnelles (Convolutional Layers)

Ce sont les couches principales des CNNs où les convolutions sont effectuées. Une couche convolutionnelle prend une image en entrée et applique plusieurs filtres pour produire des cartes de caractéristiques.

## 9. Couches de Pooling

Après une ou plusieurs couches convolutionnelles, on utilise souvent une couche de pooling pour réduire la taille des cartes de caractéristiques, rendant le réseau plus efficace et réduisant le risque de surapprentissage.

## Exemple Simplifié

Imaginons une image de 5x5 pixels et un filtre de 3x3 pixels :

```
Image (5x5) :        Filtre (3x3) :
1  1  1  0  0        1  0  1
0  1  1  0  0        0  1  0
0  0  1  1  1        1  0  1
1  1  1  1  1
0  0  0  1  0
```

En appliquant ce filtre sur l'image avec un stride de 1 et sans padding, nous calculons une nouvelle valeur à chaque position du filtre :

1. Position initiale :
   ```
   1*1 + 1*0 + 1*1 + 0*0 + 1*1 + 1*0 + 0*1 + 0*0 + 1*1 = 5
   ```

2. Déplacement du filtre d'un pas vers la droite et recalcul.

En répétant cette opération, nous obtenons une nouvelle image plus petite, une carte de caractéristiques.

# Partie 2 - Illustration des Concepts de CNNs avec un Exemple Complet

Pour illustrer les concepts de Flatten, Dense, etc., nous allons construire un exemple simple d'un CNN pour la reconnaissance d'images.

#### 1. Architecture du CNN

Imaginons que nous voulons créer un CNN pour classifier des images de vêtements (comme dans le dataset Fashion MNIST). Voici les étapes détaillées de l'architecture :

1. **Input Layer**: L'image d'entrée, par exemple, une image en niveaux de gris de 28x28 pixels.
2. **Convolutional Layer**: Une couche de convolution avec plusieurs filtres.
3. **Pooling Layer**: Une couche de pooling pour réduire la taille des cartes de caractéristiques.
4. **Flatten Layer**: Aplatir la sortie des couches précédentes pour créer un vecteur 1D.
5. **Dense (Fully Connected) Layer**: Une couche dense qui fait la classification finale.

#### 2. Étape par Étape

##### a. Convolutional Layer
La première couche du réseau est une couche de convolution qui applique plusieurs filtres sur l'image d'entrée.

**Image d'entrée :**
```
28 x 28 pixels
```

**Filtre (3x3) :**
```
1  0  1
0  1  0
1  0  1
```

Lorsque ce filtre est appliqué sur une partie de l'image, il extrait des caractéristiques spécifiques. Par exemple, en appliquant ce filtre sur une région 3x3 de l'image, nous obtenons une nouvelle valeur pour cette région.

##### b. Pooling Layer
Après la convolution, nous appliquons une couche de pooling pour réduire la taille de l'image.

**Max Pooling (2x2)** :
Nous prenons une fenêtre de 2x2 et conservons uniquement la valeur maximale.

**Image après Pooling** :
```
14 x 14 pixels
```

##### c. Flatten Layer
Ensuite, nous devons aplatir la sortie pour qu'elle puisse être utilisée par les couches denses. Le flattening transforme notre matrice 14x14 en un vecteur 1D.

**Image après Flatten** :
```
1 x 196 pixels
```

##### d. Dense Layer
Enfin, nous ajoutons des couches denses. Une couche dense (ou fully connected layer) est une couche où chaque neurone est connecté à tous les neurones de la couche précédente.

**Dense Layer** :
Si nous avons 128 neurones dans cette couche, cela signifie que chaque neurone reçoit une entrée de 196 neurones (après flatten).

#### 3. Exemple de Code

Voici un exemple de code en Python utilisant TensorFlow et Keras pour illustrer cette architecture :

```python
import tensorflow as tf
from tensorflow.keras import layers, models

# Charger le dataset Fashion MNIST
fashion_mnist = tf.keras.datasets.fashion_mnist
(train_images, train_labels), (test_images, test_labels) = fashion_mnist.load_data()

# Normaliser les images
train_images = train_images / 255.0
test_images = test_images / 255.0

# Créer le modèle CNN
model = models.Sequential()

# Ajouter une couche de convolution
model.add(layers.Conv2D(32, (3, 3), activation='relu', input_shape=(28, 28, 1)))

# Ajouter une couche de pooling
model.add(layers.MaxPooling2D((2, 2)))

# Ajouter une deuxième couche de convolution
model.add(layers.Conv2D(64, (3, 3), activation='relu'))

# Ajouter une deuxième couche de pooling
model.add(layers.MaxPooling2D((2, 2)))

# Ajouter une troisième couche de convolution
model.add(layers.Conv2D(64, (3, 3), activation='relu'))

# Aplatir la sortie
model.add(layers.Flatten())

# Ajouter une couche dense
model.add(layers.Dense(64, activation='relu'))

# Ajouter la couche de sortie
model.add(layers.Dense(10, activation='softmax'))

# Compiler le modèle
model.compile(optimizer='adam',
              loss='sparse_categorical_crossentropy',
              metrics=['accuracy'])

# Entraîner le modèle
model.fit(train_images, train_labels, epochs=5, validation_data=(test_images, test_labels))

# Résumé du modèle
model.summary()
```

#### 4. Explication des Couches Ajoutées

- **Conv2D**: Cette couche applique des filtres de convolution (32 filtres 3x3) à l'image d'entrée.
- **MaxPooling2D**: Cette couche réduit la taille des cartes de caractéristiques par pooling (2x2).
- **Flatten**: Cette couche transforme les données de 2D à 1D pour pouvoir être utilisées par les couches denses.
- **Dense**: Ces couches fully connected réalisent la classification. La première dense couche utilise 64 neurones avec l'activation ReLU, et la couche de sortie utilise 10 neurones avec l'activation softmax pour classifier les 10 classes de vêtements.




# Conclusion

- Les CNNs utilisent des couches de convolution, de pooling et d'autres techniques comme le dropout pour extraire et combiner des caractéristiques importantes des images. Ces modèles sont puissants pour la reconnaissance d'images et d'autres tâches de vision par ordinateur grâce à leur capacité à apprendre automatiquement des caractéristiques à partir des données.
- Les CNNs utilisent des couches de convolution pour extraire des caractéristiques des images, des couches de pooling pour réduire la taille des données, des couches de flatten pour aplatir les données, et des couches denses pour la classification. Ce modèle est particulièrement efficace pour la reconnaissance d'images, et il est essentiel de comprendre chaque étape pour optimiser l'architecture et obtenir les meilleurs résultats.

# Références très importantes (Partie 1)

- https://medium.com/@RaghavPrabhu/understanding-of-convolutional-neural-network-cnn-deep-learning-99760835f148
- https://openclassrooms.com/fr/courses/4470531-classez-et-segmentez-des-donnees-visuelles/5082166-quest-ce-quun-reseau-de-neurones-convolutif-ou-cnn
- https://medium.com/@deepeshdeepakdd2/cnn-visualization-techniques-feature-maps-gradient-ascent-aec4f4aaf5bd
- https://machinelearningmastery.com/how-to-develop-a-convolutional-neural-network-from-scratch-for-mnist-handwritten-digit-classification/

# Références très importantes (Partie 2)

- Allez au dossier PPT ci-joint
- https://drive.google.com/drive/folders/1nu3tZpzmdmJ5aqoHj93EaL3IMLaJCDZa?usp=sharing
- https://drive.google.com/drive/folders/1pzsSUGMK4QaWKslzAFug-fpcvmcYfu_-?usp=sharing
- https://drive.google.com/drive/folders/1KFSB4DweUvO1R2uvmRR6yWbxFTplgc4Z?usp=sharing
