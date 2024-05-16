# Pratique 2
1. **Installation de TensorFlow** :
```python
pip install tensorflow
```

2. **Importation de TensorFlow** :
```python
import tensorflow as tf
```

3. **Vérification de la version installée** :
```python
print(tf.__version__)
```

4. **Création de tenseurs** :
```python
tensor1 = tf.constant([[1, 2, 3], [4, 5, 6]])
tensor2 = tf.ones((3, 3)) # Crée un tenseur de dimensions 3x3 avec toutes les valeurs à 1
tensor3 = tf.zeros((2, 2)) # Crée un tenseur de dimensions 2x2 avec toutes les valeurs à 0
```

5. **Opérations de base sur les tenseurs** :
```python
addition = tf.add(tensor1, tensor2)
multiplication = tf.multiply(tensor1, tensor3)
```

6. **Exécution de sessions pour évaluer les tenseurs** :
```python
with tf.Session() as sess:
    result1 = sess.run(addition)
    result2 = sess.run(multiplication)
    print("Addition result:", result1)
    print("Multiplication result:", result2)
```

7. **Placeholder et Variables** :
```python
# Placeholder pour les données en entrée
x = tf.placeholder(tf.float32, shape=(None, 3))
# Variable pour les poids du modèle
W = tf.Variable(tf.random_normal([3, 2]))
```

8. **Initialisation des variables dans une session** :
```python
init = tf.global_variables_initializer()
with tf.Session() as sess:
    sess.run(init)
```

9. **Opérations de réduction** :
```python
tensor = tf.constant([[1, 2, 3], [4, 5, 6]])
sum_tensor = tf.reduce_sum(tensor) # Somme de tous les éléments
max_tensor = tf.reduce_max(tensor) # Maximum de tous les éléments
mean_tensor = tf.reduce_mean(tensor) # Moyenne de tous les éléments
```

10. **Opérations de transformation** :
```python
tensor = tf.constant([[1, 2, 3], [4, 5, 6]])
reshaped_tensor = tf.reshape(tensor, [3, 2]) # Redimensionner le tenseur
flattened_tensor = tf.reshape(tensor, [-1]) # Aplatir le tenseur en un vecteur
```
