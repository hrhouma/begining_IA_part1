# Utilisation de Streamlit, FastAPI et MLflow dans un projet de Machine Learning

## Présentation

Ce document explique comment utiliser ensemble Streamlit, FastAPI, et MLflow pour développer une application de Machine Learning. Voici un diagramme illustrant l'architecture du projet et le rôle de chaque composant.

## Architecture du projet

![Architecture Diagram](https://i.imgur.com/OG3v5j4.png)

## Description des composants

### 1. Streamlit (Frontend)

**Rôle**: Créer une interface utilisateur interactive.

**Utilisation**: Streamlit est utilisé pour créer des applications web interactives qui permettent aux utilisateurs de visualiser les résultats des modèles de Machine Learning, d'entrer des données et de déclencher des prédictions.

**Exemple de code**:
```python
import streamlit as st
import requests

st.title("Application de Machine Learning")

# Entrée utilisateur
user_input = st.text_input("Entrez une valeur:")

# Envoi de la requête au backend FastAPI
if st.button("Prédire"):
    response = requests.post("http://127.0.0.1:8000/predict", json={"input": user_input})
    prediction = response.json()["prediction"]
    st.write(f"Prédiction: {prediction}")
```

### 2. FastAPI (Backend)

**Rôle**: Gérer les requêtes HTTP et servir de point de contact entre l'interface utilisateur (Streamlit) et les modèles de Machine Learning.

**Utilisation**: FastAPI est utilisé pour créer des endpoints qui reçoivent les données de Streamlit, traitent ces données avec les modèles de Machine Learning et renvoient les résultats à Streamlit.

**Exemple de code**:
```python
from fastapi import FastAPI
from pydantic import BaseModel
import joblib

app = FastAPI()

# Chargement du modèle de Machine Learning
model = joblib.load("model.pkl")

class InputData(BaseModel):
    input: str

@app.post("/predict")
def predict(data: InputData):
    prediction = model.predict([data.input])
    return {"prediction": prediction[0]}
```

### 3. MLflow (MLOps)

**Rôle**: Gérer le cycle de vie du Machine Learning, y compris le suivi des expérimentations, la reproductibilité, le déploiement des modèles et la gestion des registres de modèles.

**Utilisation**: MLflow est utilisé pour suivre les expériences de Machine Learning, enregistrer les paramètres et les métriques des modèles, et gérer les versions des modèles.

**Exemple de code**:
```python
import mlflow
import mlflow.sklearn
from sklearn.ensemble import RandomForestClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score

# Chargement des données
X, y = load_data()

# Séparation des données en train et test
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Définition du modèle
model = RandomForestClassifier()

# Démarrage de l'expérience MLflow
with mlflow.start_run():
    # Entraînement du modèle
    model.fit(X_train, y_train)

    # Prédiction et évaluation
    predictions = model.predict(X_test)
    accuracy = accuracy_score(y_test, predictions)
    
    # Enregistrement des paramètres, métriques et du modèle
    mlflow.log_param("random_state", 42)
    mlflow.log_metric("accuracy", accuracy)
    mlflow.sklearn.log_model(model, "model")
```

## Workflow d'intégration

1. **Développement du modèle avec MLflow**: Utiliser MLflow pour suivre et enregistrer les expérimentations et les modèles.
2. **Déploiement du modèle avec FastAPI**: Créer une API avec FastAPI pour servir le modèle de Machine Learning.
3. **Interface utilisateur avec Streamlit**: Créer une interface utilisateur avec Streamlit qui communique avec l'API FastAPI pour obtenir des prédictions et afficher les résultats.

## Conclusion

En utilisant Streamlit pour le frontend, FastAPI pour le backend, et MLflow pour la gestion du cycle de vie du Machine Learning, vous pouvez créer une application de Machine Learning complète, interactive et facilement maintenable.

---

Ce document vous donne une vue d'ensemble sur comment intégrer ces technologies dans un projet de Machine Learning. Vous pouvez ajuster et personnaliser ces composants selon les besoins spécifiques de votre projet.
