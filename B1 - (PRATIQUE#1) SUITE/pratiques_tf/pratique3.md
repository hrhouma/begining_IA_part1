# Exercice 1: Calculer la somme de deux matrices.

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

# Exercice 2: Concaténation de deux tenseurs.

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

# Exercice 3: Produit scalaire de deux vecteurs.

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

# Exercice 4: Transposition d'une matrice.

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

# Exercice 5: Calcul de la norme L2 d'un vecteur.

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

# Exercice 6: Multiplication de deux matrices.

Question:
Calculez le produit de deux matrices.

Correction:
```python
import tensorflow as tf

# Définir deux matrices
matrix1 = tf.constant([[1, 2], [3, 4]])
matrix2 = tf.constant([[5, 6], [7, 8]])

# Calculer le produit des matrices
result = tf.matmul(matrix1, matrix2)

# Exécuter une session pour obtenir le résultat
with tf.Session() as sess:
    print(sess.run(result))
```

# Exercice 7: Création d'une séquence de nombres.

Question:
Créez une séquence de nombres de 1 à 10.

Correction:
```python
import tensorflow as tf

# Créer une séquence de nombres de 1 à 10
sequence = tf.range(1, 11)

# Exécuter une session pour obtenir la séquence
with tf.Session() as sess:
    print(sess.run(sequence))
```

# Exercice 8: Exécution conditionnelle.

Question:
Implémentez une opération conditionnelle qui retourne "Pair" si un nombre est pair et "Impair" sinon.

Correction:
```python
import tensorflow as tf

# Définir un placeholder pour le nombre
number = tf.placeholder(tf.int32)

# Vérifier si le nombre est pair ou impair
result = tf.cond(tf.equal(tf.mod(number, 2), 0),
                 lambda: "Pair",
                 lambda: "Impair")

# Exécuter une session pour obtenir le résultat
with tf.Session() as sess:
    print(sess.run(result, feed_dict={number: 5}))  # Changez le nombre ici
```

# Exercice 9: Répétition d'un tenseur.

Question:
Répétez un tenseur donné 3 fois le long de l'axe des colonnes.

Correction:
```python
import tensorflow as tf

# Définir un tenseur
tensor = tf.constant([[1, 2], [3, 4]])

# Répéter le tenseur le long de l'axe des colonnes
result = tf.tile(tensor, [1, 3])

# Exécuter une session pour obtenir le résultat
with tf.Session() as sess:
    print(sess.run(result))
```

# Exercice 10: Calcul de la moyenne.

Question:
Calculez la moyenne d'un tableau de nombres.

Correction:
```python
import tensorflow as tf

# Définir un tableau de nombres
numbers = tf.constant([1, 2, 3, 4, 5], dtype=tf.float32)

# Calculer la moyenne
result = tf.reduce_mean(numbers)

# Exécuter une session pour obtenir la moyenne
with tf.Session() as sess:
    print(sess.run(result))
```


# Exercice 11: Addition de deux tenseurs.

Question:
Calculez la somme de deux tenseurs.

Correction:
```python
import tensorflow as tf

# Définir deux tenseurs
tensor1 = tf.constant([[1, 2], [3, 4]])
tensor2 = tf.constant([[5, 6], [7, 8]])

# Calculer la somme des tenseurs
result = tf.add(tensor1, tensor2)

# Exécuter une session pour obtenir le résultat
with tf.Session() as sess:
    print(sess.run(result))
```

# Exercice 12: Multiplication de deux tenseurs.

Question:
Calculez le produit de deux tenseurs.

Correction:
```python
import tensorflow as tf

# Définir deux tenseurs
tensor1 = tf.constant([[1, 2], [3, 4]])
tensor2 = tf.constant([[5, 6], [7, 8]])

# Calculer le produit des tenseurs
result = tf.multiply(tensor1, tensor2)

# Exécuter une session pour obtenir le résultat
with tf.Session() as sess:
    print(sess.run(result))
```

# Exercice 13: Soustraction de deux tenseurs.

Question:
Calculez la différence de deux tenseurs.

Correction:
```python
import tensorflow as tf

# Définir deux tenseurs
tensor1 = tf.constant([[1, 2], [3, 4]])
tensor2 = tf.constant([[5, 6], [7, 8]])

# Calculer la différence des tenseurs
result = tf.subtract(tensor1, tensor2)

# Exécuter une session pour obtenir le résultat
with tf.Session() as sess:
    print(sess.run(result))
```

# Exercice 14: Addition des éléments d'un tenseur.

Question:
Calculez la somme de tous les éléments d'un tenseur.

Correction:
```python
import tensorflow as tf

# Définir un tenseur
tensor = tf.constant([[1, 2], [3, 4]])

# Calculer la somme des éléments du tenseur
result = tf.reduce_sum(tensor)

# Exécuter une session pour obtenir le résultat
with tf.Session() as sess:
    print(sess.run(result))
```

# Exercice 15: Produit scalaire de deux vecteurs.

Question:
Calculez le produit scalaire de deux vecteurs.

Correction:
```python
import tensorflow as tf

# Définir deux vecteurs
vector1 = tf.constant([1, 2, 3])
vector2 = tf.constant([4, 5, 6])

# Calculer le produit scalaire des vecteurs
result = tf.tensordot(vector1, vector2, axes=1)

# Exécuter une session pour obtenir le résultat
with tf.Session() as sess:
    print(sess.run(result))
```


# Exercice 18: Différence entre "type" et "dtype".

Question:
Expliquez la différence entre "type" et "dtype" dans TensorFlow.

Correction:
```python
import tensorflow as tf

# Créer un tenseur avec un type de données spécifique (dtype)
tensor_float32 = tf.constant([1.5, 2.5, 3.5], dtype=tf.float32)

# Obtenir le type Python du tenseur
tensor_type = type(tensor_float32)

# Obtenir le type de données (dtype) du tenseur
tensor_dtype = tensor_float32.dtype

# Exécuter une session pour obtenir les résultats
with tf.Session() as sess:
    type_result, dtype_result = sess.run([tensor_type, tensor_dtype])
    print("Type Python du tenseur:", type_result)
    print("Type de données (dtype) du tenseur:", dtype_result)
```

Dans cet exercice, "type" se réfère au type Python du tenseur (par exemple, `<class 'tensorflow.python.framework.ops.Tensor'>`), tandis que "dtype" se réfère au type de données du tenseur dans TensorFlow (par exemple, `tf.float32`).
