### Introduction aux Réseaux de Neurones Convolutionnels (CNNs)

Les réseaux de neurones convolutionnels (CNNs) sont des modèles d'apprentissage automatique particulièrement efficaces pour traiter les images. Voici une explication simplifiée des principaux concepts associés aux CNNs.

#### 1. Qu'est-ce qu'une image couleur ?

Une image couleur est composée de pixels, et chaque pixel est représenté par trois valeurs correspondant aux trois couleurs primaires de la lumière : rouge (Red), vert (Green), et bleu (Blue). Ces valeurs sont souvent abrégées en RGB. Par exemple, un pixel avec des valeurs (255, 0, 0) sera rouge vif, tandis qu'un pixel avec des valeurs (0, 255, 0) sera vert vif.

#### 2. La Convolution

La convolution est une opération mathématique qui permet d'extraire des caractéristiques de l'image. Imaginez que vous avez une petite fenêtre, appelée filtre ou noyau, que vous faites glisser sur l'image. Chaque fois que vous placez le filtre sur une partie de l'image, vous effectuez une multiplication élément par élément entre les valeurs du filtre et les valeurs de l'image sous la fenêtre, puis vous additionnez ces valeurs. Le résultat de cette opération est un seul nombre, et en répétant cette opération pour chaque position du filtre, vous obtenez une nouvelle image, appelée carte de caractéristiques.

#### 3. Les Filtres (ou Noyaux)

Les filtres sont des petits tableaux de nombres (souvent 3x3 ou 5x5) qui détectent certaines caractéristiques de l'image, comme les bords ou les textures. Par exemple, un filtre peut être conçu pour détecter les contours verticaux, tandis qu'un autre peut détecter les contours horizontaux.

#### 4. Strides

Les strides (ou pas en français) déterminent de combien de pixels vous déplacez le filtre à chaque fois. Par exemple, un stride de 1 signifie que vous déplacez le filtre d'un pixel à la fois, tandis qu'un stride de 2 signifie que vous le déplacez de deux pixels à la fois.

#### 5. Padding

Le padding est une technique utilisée pour ajouter des pixels autour de l'image. Cela permet de contrôler la taille de la sortie de la convolution. Par exemple, sans padding, la taille de l'image diminue après chaque convolution. Avec padding, on peut garder la taille de l'image constante.

#### 6. Pooling Layer (ou Couches de Pooling)

Le pooling est une opération qui réduit la taille de l'image et aide à extraire les caractéristiques les plus importantes. Le pooling le plus courant est le max pooling, où une fenêtre (par exemple, 2x2) glisse sur l'image et ne conserve que la valeur maximale de chaque fenêtre.

#### 7. Dropout

Le dropout est une technique de régularisation utilisée pour éviter le surapprentissage. Pendant l'entraînement, il "éteint" (met à zéro) aléatoirement un certain pourcentage de neurones dans un réseau. Cela force le réseau à ne pas dépendre trop de certains neurones spécifiques et rend le modèle plus robuste.

#### 8. Couches Convolutionnelles (Convolutional Layers)

Ce sont les couches principales des CNNs où les convolutions sont effectuées. Une couche convolutionnelle prend une image en entrée et applique plusieurs filtres pour produire des cartes de caractéristiques.

#### 9. Couches de Pooling

Après une ou plusieurs couches convolutionnelles, on utilise souvent une couche de pooling pour réduire la taille des cartes de caractéristiques, rendant le réseau plus efficace et réduisant le risque de surapprentissage.

#### Exemple Simplifié

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

### Conclusion

Les CNNs utilisent des couches de convolution, de pooling et d'autres techniques comme le dropout pour extraire et combiner des caractéristiques importantes des images. Ces modèles sont puissants pour la reconnaissance d'images et d'autres tâches de vision par ordinateur grâce à leur capacité à apprendre automatiquement des caractéristiques à partir des données.

# Références très importantes

- https://medium.com/@RaghavPrabhu/understanding-of-convolutional-neural-network-cnn-deep-learning-99760835f148
- https://openclassrooms.com/fr/courses/4470531-classez-et-segmentez-des-donnees-visuelles/5082166-quest-ce-quun-reseau-de-neurones-convolutif-ou-cnn
- https://medium.com/@deepeshdeepakdd2/cnn-visualization-techniques-feature-maps-gradient-ascent-aec4f4aaf5bd
- https://machinelearningmastery.com/how-to-develop-a-convolutional-neural-network-from-scratch-for-mnist-handwritten-digit-classification/
