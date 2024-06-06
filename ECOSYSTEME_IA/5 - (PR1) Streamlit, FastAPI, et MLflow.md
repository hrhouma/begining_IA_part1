# Projet de Machine Learning avec Streamlit, FastAPI et MLflow

Ce projet montre comment intégrer Streamlit pour le frontend, FastAPI pour le backend et MLflow pour la gestion du cycle de vie du Machine Learning (MLOps). 

## Table des matières
1. [Présentation](#présentation)
2. [Streamlit](#streamlit)
3. [FastAPI](#fastapi)
4. [MLflow](#mlflow)
5. [Architecture du projet](#architecture-du-projet)
6. [Installation](#installation)
7. [Utilisation](#utilisation)
8. [Conclusion](#conclusion)

## Présentation

Ce projet illustre une approche complète de développement de Machine Learning en utilisant :
- **Streamlit** pour créer des interfaces utilisateur interactives et intuitives.
- **FastAPI** pour gérer les requêtes HTTP et servir de point de contact entre l'interface utilisateur et les modèles de Machine Learning.
- **MLflow** pour gérer les expériences de Machine Learning, le suivi des modèles, et la gestion des déploiements.

## Streamlit

### Qu'est-ce que Streamlit ?

Streamlit est un framework open-source qui permet de créer des applications web interactives pour le Data Science et le Machine Learning avec peu de code. Il est particulièrement adapté pour créer des dashboards et des visualisations en temps réel.

### Utilisation de Streamlit

Pour utiliser Streamlit, il suffit de créer un fichier Python et d'y ajouter des éléments d'interface utilisateur avec des commandes simples.

```python
import streamlit as st

st.title("Application de Machine Learning")
st.write("Ceci est une application Streamlit pour visualiser des modèles de Machine Learning.")
```

Lancer l'application Streamlit avec :
```sh
streamlit run app.py
```

## FastAPI

### Qu'est-ce que FastAPI ?

FastAPI est un framework web moderne et rapide (haute performance) pour construire des APIs avec Python 3.7+ basé sur les annotations de type. Il est idéal pour créer des applications backend robustes.

### Utilisation de FastAPI

Créer un fichier Python pour définir une API avec FastAPI.

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"message": "Hello World"}
```

Lancer l'application FastAPI avec :
```sh
uvicorn main:app --reload
```

## MLflow

### Qu'est-ce que MLflow ?

MLflow est une plateforme open-source pour gérer le cycle de vie du Machine Learning, y compris le suivi des expérimentations, la reproductibilité, le déploiement des modèles et la gestion des registres de modèles.

### Utilisation de MLflow

Pour utiliser MLflow, vous devez configurer votre script d'entraînement pour enregistrer des métriques et des artefacts.

```python
import mlflow
import mlflow.sklearn

with mlflow.start_run():
    mlflow.log_param("param1", value1)
    mlflow.log_metric("metric1", value1)
    mlflow.sklearn.log_model(model, "model")
```

Lancer l'interface utilisateur MLflow avec :
```sh
mlflow ui
```

## Architecture du projet

1. **Frontend (Streamlit)** : Interface utilisateur pour interagir avec le modèle de Machine Learning.
2. **Backend (FastAPI)** : Serveur pour gérer les requêtes et répondre aux appels de l'interface utilisateur.
3. **MLOps (MLflow)** : Gestion et suivi des expérimentations, modèles et déploiements.

## Installation

Cloner le repository et installer les dépendances.

```sh
git clone https://github.com/votre-repository/projet-ml.git
cd projet-ml
pip install -r requirements.txt
```

## Utilisation

1. **Lancer Streamlit** :
    ```sh
    streamlit run app.py
    ```
2. **Lancer FastAPI** :
    ```sh
    uvicorn main:app --reload
    ```
3. **Lancer MLflow** :
    ```sh
    mlflow ui
    ```

## Conclusion

Ce projet montre comment intégrer Streamlit, FastAPI, et MLflow pour créer une application de Machine Learning complète, de la création d'une interface utilisateur interactive à la gestion du cycle de vie du modèle. En utilisant ces outils ensemble, vous pouvez développer, déployer et gérer efficacement vos projets de Machine Learning.