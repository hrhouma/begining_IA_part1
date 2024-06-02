# Table des Matières

## 00.md - Introduction et Configuration de MLflow
- Guide d'installation de MLflow sur une VM Ubuntu 22.04
- Préparation de l'environnement
- Téléchargement des données

## 01.md - Entraînement de Modèle de Base avec ElasticNet
- Code pour l'entraînement d'un modèle ElasticNet simple
- Enregistrement des paramètres, métriques, et modèles

## 02.md - Introduction de MLflow pour le Suivi des Expériences
- Utilisation de MLflow pour enregistrer des expériences
- Enregistrement des paramètres et métriques avec MLflow

## 03.md - Configuration de l'URI de Suivi MLflow
- Configuration de l'URI de suivi avec `mlflow.set_tracking_uri`
- Vérification de l'URI de suivi avec `mlflow.get_tracking_uri`

## 04.md - Création d'une Expérience MLflow
- Création d'une expérience avec `mlflow.create_experiment`
- Ajout de métadonnées et d'emplacement d'artefact

## 05.md - Gestion des Exécutions Actives
- Démarrage et fin des exécutions avec `mlflow.start_run` et `mlflow.end_run`
- Obtention de la dernière exécution active avec `mlflow.last_active_run`

## 06.md - Enregistrement des Artefacts
- Enregistrement des artefacts avec `mlflow.log_artifacts`
- Organisation des fichiers de données associés à l'expérience

## 07.md - Utilisation de `mlflow.set_tags`
- Ajout de tags aux exécutions avec `mlflow.set_tags`
- Organisation et gestion des métadonnées supplémentaires

## 08.md - Lancement de Plusieurs Exécutions
- Lancement de plusieurs exécutions dans un même script
- Comparaison des résultats de différents réglages de paramètres

## 09.md - Lancement de Plusieurs Expériences
- Lancement de plusieurs expériences distinctes (ElasticNet, Ridge, Lasso)
- Comparaison des résultats de différents algorithmes de régression

## 10.md - Utilisation de `mlflow.autolog`
- Automatisation de l'enregistrement des paramètres, métriques et modèles avec `mlflow.autolog`
- Simplification du suivi des expériences de machine learning

