# pratique 5 - réponses

1. **Manipulation de données** :

Question: Comment charger un ensemble de données MNIST avec TensorFlow ?
Réponse: Utilisez `tf.keras.datasets.mnist.load_data()` pour charger l'ensemble de données MNIST.

Code complet exhaustif :

```python
import tensorflow as tf

# Charger l'ensemble de données MNIST
(x_train, y_train), (x_test, y_test) = tf.keras.datasets.mnist.load_data()

# Normaliser les valeurs des pixels entre 0 et 1
x_train, x_test = x_train / 255.0, x_test / 255.0
```

2. **Construction d'un modèle simple** :

Question: Comment définir un modèle de réseau de neurones avec une couche cachée ?
Réponse: Utilisez l'API séquentielle de Keras pour définir un modèle.

Code complet exhaustif :

```python
# Définir le modèle
model = tf.keras.Sequential([
    tf.keras.layers.Flatten(input_shape=(28, 28)),
    tf.keras.layers.Dense(128, activation='relu'),
    tf.keras.layers.Dropout(0.2),
    tf.keras.layers.Dense(10)
])
```

3. **Entraînement du modèle** :

Question: Comment compiler et entraîner un modèle avec TensorFlow ?
Réponse: Utilisez la méthode `compile()` pour définir la fonction de perte et l'optimiseur, puis appelez `fit()` pour l'entraînement.

Code complet exhaustif :

```python
# Compiler le modèle
model.compile(optimizer='adam',
              loss=tf.keras.losses.SparseCategoricalCrossentropy(from_logits=True),
              metrics=['accuracy'])

# Entraîner le modèle
model.fit(x_train, y_train, epochs=5, validation_data=(x_test, y_test))
```

4. **Évaluation du modèle** :

Question: Comment évaluer la performance d'un modèle sur l'ensemble de test ?
Réponse: Utilisez la méthode `evaluate()`.

Code complet exhaustif :

```python
# Évaluer le modèle
test_loss, test_acc = model.evaluate(x_test, y_test, verbose=2)
print('\nTest accuracy:', test_acc)
```

5. **Régularisation** :

Question: Comment ajouter une régularisation L2 aux poids du modèle ?
Réponse: Utilisez le paramètre `kernel_regularizer` lors de la définition des couches.

Code complet exhaustif :

```python
# Définir le modèle avec régularisation L2
model = tf.keras.Sequential([
    tf.keras.layers.Flatten(input_shape=(28, 28)),
    tf.keras.layers.Dense(128, activation='relu', kernel_regularizer=tf.keras.regularizers.l2(0.01)),
    tf.keras.layers.Dropout(0.2),
    tf.keras.layers.Dense(10)
])
```

6. **Validation croisée** :

Question: Comment implémenter la validation croisée k-fold avec TensorFlow ?
Réponse: Utilisez `sklearn.model_selection.KFold` pour diviser les données et entraîner/valider le modèle pour chaque pli.

Code complet exhaustif :

```python
from sklearn.model_selection import KFold

# Définir le nombre de plis
k = 5
kf = KFold(n_splits=k)

# Boucle sur les plis
for train_index, test_index in kf.split(x_train):
    train_data, val_data = x_train[train_index], x_train[test_index]
    train_labels, val_labels = y_train[train_index], y_train[test_index]
    
    # Définir, compiler et entraîner le modèle pour chaque pli
    model = tf.keras.Sequential([
        tf.keras.layers.Flatten(input_shape=(28, 28)),
        tf.keras.layers.Dense(128, activation='relu'),
        tf.keras.layers.Dropout(0.2),
        tf.keras.layers.Dense(10)
    ])
    model.compile(optimizer='adam',
                  loss=tf.keras.losses.SparseCategoricalCrossentropy(from_logits=True),
                  metrics=['accuracy'])
    model.fit(train_data, train_labels, epochs=5, validation_data=(val_data, val_labels))
```

7. **Utilisation de TensorBoard** :

Question: Comment ajouter des journaux pour TensorBoard dans un modèle TensorFlow ?
Réponse: Utilisez `tf.keras.callbacks.TensorBoard()` lors de l'entraînement.

Code complet exhaustif :

```python
# Définir le callback TensorBoard
tensorboard_callback = tf.keras.callbacks.TensorBoard(log_dir="logs")

# Entraîner le modèle avec le callback TensorBoard
model.fit(x_train, y_train, epochs=5, validation_data=(x_test, y_test), callbacks=[tensorboard_callback])
```

8. **Utilisation de GPU** :

Question: Comment exécuter le calcul sur une carte graphique (GPU) avec TensorFlow ?
Réponse: Assurez-vous que TensorFlow est installé avec la prise en charge GPU (`pip install tensorflow-gpu`) et que les pilotes GPU appropriés sont installés sur le système.

Code complet exhaustif :

```python
# Vérifier si TensorFlow utilise le GPU
import tensorflow as tf
print("GPU available: ", tf.test.is_gpu_available())

# Si TensorFlow utilise le GPU, cela devrait imprimer True
```

9. **Transfert d'apprentissage** :

Question: Comment charger un modèle pré-entraîné et l'adapter à un nouvel ensemble de données ?
Réponse: Chargez le modèle avec `tf.keras.models.load_model()` et ajustez la dernière couche ou quelques couches supérieures pour s'adapter à votre nouvel ensemble de données.

Code complet exhaustif :

```python
# Charger un modèle pré-entraîné comme VGG16
base_model = tf.keras.applications.VGG16(weights='imagenet', include_top=False, input_shape=(224, 224, 3))

# Ajouter des couches supplémentaires pour adapter le modèle à un nouvel ensemble de données
x = base_model.output
x = tf.keras.layers.GlobalAveragePooling2D()(x)
x = tf.keras.layers.Dense(1024, activation='relu')(x)
predictions = tf.keras.layers.Dense(NUM_CLASSES, activation='softmax')(x)

# Définir le nouveau modèle
model = tf.keras.Model(inputs=base_model.input, outputs=predictions)

# Compiler le modèle
model.compile(optimizer='adam', loss='categorical_crossentropy', metrics=['accuracy'])

# Entraîner le modèle avec les nouvelles données
model.fit(new_x_train, new_y_train, epochs=10, batch_size=32, validation_data=(val_x, val_y))
```

10. **Expérimentation hyperparamétrique** :

Question: Comment faire varier les hyperparamètres et observer leur impact sur les performances du modèle ?
Réponse: Utilisez des boucles pour essayer différentes valeurs des hyperparamètres et tracez les performances du modèle en fonction de ces valeurs pour déterminer les meilleurs hyperparamètres.

Code complet exhaustif :

```python
# Exemple de boucle pour l'expérimentation hyperparamétrique
for learning_rate in [0.

001, 0.01, 0.1]:
    for batch_size in [32, 64, 128]:
        # Définir et compiler le modèle avec les hyperparamètres actuels
        model = tf.keras.Sequential([
            tf.keras.layers.Flatten(input_shape=(28, 28)),
            tf.keras.layers.Dense(128, activation='relu'),
            tf.keras.layers.Dense(10)
        ])
        model.compile(optimizer=tf.keras.optimizers.Adam(learning_rate=learning_rate),
                      loss=tf.keras.losses.SparseCategoricalCrossentropy(from_logits=True),
                      metrics=['accuracy'])
        
        # Entraîner le modèle
        model.fit(x_train, y_train, epochs=5, batch_size=batch_size)
        
        # Évaluer le modèle
        loss, accuracy = model.evaluate(x_test, y_test)
        
        print("Learning rate:", learning_rate, "Batch size:", batch_size, "Accuracy:", accuracy)
```

