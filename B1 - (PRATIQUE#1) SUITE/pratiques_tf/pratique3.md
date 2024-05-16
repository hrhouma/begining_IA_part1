D'accord, voici quelques exercices et leurs corrections portant sur des opérations de base avec TensorFlow, sans se limiter uniquement au machine learning :

Exercice 1: Calculer la somme de deux matrices.

Question:
Écrivez une fonction TensorFlow pour calculer la somme de deux matrices.

Correction:
```python
import tensorflow as tf

# Définir deux matrices
matrix1 = tf.constant([[1, 2], [3, 4]])
matrix2 = tf.constant([[5, 6], [7, 8]])

# Calculer la somme des matrices
result = tf.add(matrix1, matrix2)

# Exécuter une session pour obtenir le résultat
with tf.Session() as sess:
    print(sess.run(result))
```

Exercice 2: Concaténation de deux tenseurs.

Question:
Concaténez deux tenseurs le long de l'axe des colonnes.

Correction:
```python
import tensorflow as tf

# Définir deux tenseurs
tensor1 = tf.constant([[1, 2], [3, 4]])
tensor2 = tf.constant([[5, 6], [7, 8]])

# Concaténer les tenseurs le long de l'axe des colonnes
result = tf.concat([tensor1, tensor2], axis=1)

# Exécuter une session pour obtenir le résultat
with tf.Session() as sess:
    print(sess.run(result))
```

Exercice 3: Produit scalaire de deux vecteurs.

Question:
Calculez le produit scalaire de deux vecteurs.

Correction:
```python
import tensorflow as tf

# Définir deux vecteurs
vector1 = tf.constant([1, 2, 3])
vector2 = tf.constant([4, 5, 6])

# Calculer le produit scalaire
result = tf.tensordot(vector1, vector2, axes=1)

# Exécuter une session pour obtenir le résultat
with tf.Session() as sess:
    print(sess.run(result))
```

Exercice 4: Transposition d'une matrice.

Question:
Transposez une matrice donnée.

Correction:
```python
import tensorflow as tf

# Définir une matrice
matrix = tf.constant([[1, 2, 3], [4, 5, 6]])

# Transposer la matrice
result = tf.transpose(matrix)

# Exécuter une session pour obtenir le résultat
with tf.Session() as sess:
    print(sess.run(result))
```

Exercice 5: Calcul de la norme L2 d'un vecteur.

Question:
Calculez la norme L2 d'un vecteur donné.

Correction:
```python
import tensorflow as tf

# Définir un vecteur
vector = tf.constant([1, 2, 3, 4])

# Calculer la norme L2
result = tf.norm(vector, ord='euclidean')

# Exécuter une session pour obtenir le résultat
with tf.Session() as sess:
    print(sess.run(result))
```

Ces exercices fournissent une pratique pour des opérations de base avec TensorFlow, comme l'addition de matrices, la concaténation de tenseurs, le produit scalaire de vecteurs, la transposition de matrices et le calcul de normes.
