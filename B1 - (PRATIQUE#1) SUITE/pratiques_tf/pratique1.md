# pratique 1


# Les constantes

```python
!pip list

import tensorflow as tf

import os

os.environ['TF_CPP_MIN_LOG_LEVEL'] = '2'

a = tf.constant(10.)

print(type(b))

b = tf.constant(10.)

print(f" a + b = {a+b}")

!python --version

result = tf.add(a,b)
print(result)

c= tf.constant(5.)
d = tf.constant(3.)
print("Type de données de 'c' ", c.dtype)
print("Type de données de 'd' ", d.dtype)
print(f"c + d = {c + d}")
somme=c+d
print("Type de données de 'd' ", somme.dtype)

e = tf.constant (10., dtype="float64")
print(type(e))
print("Type de données de 'e' ", e.dtype)

tarek = tf.constant(5.,dtype=tf.float64)
print(tarek)

b = tf.constant(10.)
c = tf.constant(6., dtype="float64")

print(f"b+c = {b+c} ")

print(f"b+c = {b+tf.cast(c,tf.float32)} ")
```

# Les matrices


```python
tensor_3 = tf.zeros((3,3))

print(f"tensor_3= \n {tensor_3}")

tensor_4 = tf.random.uniform((3,3))
print(tensor_4)

tensor_4 = tf.random.uniform((3,3),minval=1,maxval=10)
print(tensor_4)

tensor_5 = tf.random.uniform((3,3),seed=2)
print(f"tensor_5= \n {tensor_5}")

tensor_5 = tf.random.uniform((3,3),seed=tf.random.set_seed(2))
print(f"tensor_5= \n {tensor_5}")

import tensorflow as tf

# Fixer la graine pour obtenir des résultats reproductibles
tf.random.set_seed(2)

# Générer une matrice 3x3 de nombres pseudo-aléatoires
tensor_5 = tf.random.uniform((3,3))

# Afficher la matrice
print("Matrice aléatoire avec seed 2:")
print(tensor_5.numpy())

import tensorflow as tf

# Générer une matrice 3x3 de nombres aléatoires à partir d'une distribution normale
tensor_normal = tf.random.normal((3, 3), mean=0, stddev=20)

# Afficher la matrice
print("Matrice aléatoire à partir d'une distribution normale:")
print(tensor_normal.numpy())

"""# 1 - Créez un tenseur de forme (5,3) avec des valeurs aléatoires uniformes.
# 2 - Créez un tenseur de forme (8,8) avec des valeurs aléatoires normales et une déviation standard de 20. C'est quoi la signification de déviation standard de 20 ?
"""

import numpy as np
tenseur = np.random.rand(5,3)
print(tenseur)

import tensorflow as tf

# Fixer la graine pour obtenir des résultats reproductibles
tf.random.set_seed(2)

# Générer une matrice 3x3 de nombres pseudo-aléatoires
mytensor = tf.random.uniform((5,3))

# Afficher la matrice
print("Matrice aléatoire avec seed 2:")
print(mytensor.numpy())

import tensorflow as tf

# Fixer la graine pour obtenir des résultats reproductibles
tf.random.set_seed(2)

# Générer une matrice 3x3 de nombres pseudo-aléatoires
mytensornormal = tf.random.normal((8,8), mean=0, stddev=10)

# Afficher la matrice
print("Matrice aléatoire avec seed 2:")
print(mytensornormal.numpy())

import tensorflow as tf

# Fixer la graine pour obtenir des résultats reproductibles
tf.random.set_seed(2)

# Générer une matrice 3x3 de nombres pseudo-aléatoires
mytensornormal = tf.random.normal((8,8), mean=10, stddev=20)

# Afficher la matrice
print("Matrice aléatoire avec seed 2:")
print(mytensornormal.numpy())

# Affichez le version de tensorflow
import tensorflow as tf
print(tf.__version__)

```


