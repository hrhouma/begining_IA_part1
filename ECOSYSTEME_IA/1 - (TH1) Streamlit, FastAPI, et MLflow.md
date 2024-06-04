# Utilisation de Streamlit, FastAPI et MLflow dans un projet de Machine Learning 🚀

## Présentation

Pour développer une application de Machine Learning, nous pouvons utiliser trois outils principaux : Streamlit, FastAPI, et MLflow. Voici comment chacun de ces outils fonctionne et comment ils peuvent être utilisés ensemble dans un seul exemple : une banque qui évalue les comportements de paiement de ses clients.

## Streamlit (Frontend) 🖥️

### Rôle de Streamlit

**Streamlit** est l'interface utilisateur de votre application de Machine Learning. Imaginez que vous avez une application qui aide une banque à évaluer les comportements de paiement de ses clients. Avec Streamlit, vous pouvez créer une page web où les employés de la banque peuvent entrer des informations sur les clients (comme le revenu, l'historique de crédit, etc.) et voir la probabilité que ces clients payent à temps.

## FastAPI (Backend) 🍽️

### Rôle de FastAPI

**FastAPI** reçoit les données saisies dans Streamlit et traite les requêtes. Il utilise le modèle de Machine Learning pour faire des prédictions sur les comportements de paiement et renvoie les résultats à Streamlit.

## MLflow (MLOps) 🔬

### Rôle de MLflow

**MLflow** permet de gérer et de suivre les expérimentations de Machine Learning. Les data scientists utilisent MLflow pour tester différents modèles et hyperparamètres afin de trouver le modèle le plus précis pour prédire les comportements de paiement des clients.

## Workflow d'intégration 🔄

### Exemple de projet complet

Imaginons que vous développez une application qui aide une banque à évaluer les comportements de paiement de ses clients.

1. **Développement du modèle avec MLflow** :
   - Les data scientists testent plusieurs modèles de Machine Learning pour prédire la probabilité de paiement à temps des clients.
   - Ils utilisent MLflow pour enregistrer les résultats de chaque test, comme un journal de laboratoire.
   - Exemple : Tester différents algorithmes et paramètres pour trouver le modèle le plus précis.

2. **Déploiement du modèle avec FastAPI** :
   - Une fois le meilleur modèle trouvé, il est intégré dans FastAPI.
   - FastAPI reçoit les données des clients et utilise le modèle pour faire des prédictions.
   - Exemple : Recevoir les données des clients et prédire la probabilité de paiement à temps.

3. **Interface utilisateur avec Streamlit** :
   - Streamlit est utilisé pour créer une application web où les employés de la banque peuvent entrer les données des clients.
   - Les employés obtiennent des prédictions instantanées sur les comportements de paiement grâce à l'interface utilisateur.
   - Exemple : Une page web où les employés peuvent entrer des informations sur les clients et voir les prédictions de paiement.

## Conclusion 📊

En utilisant Streamlit pour l'interface utilisateur, FastAPI pour le traitement des données, et MLflow pour la gestion et le suivi des modèles de Machine Learning, vous pouvez créer une application de Machine Learning efficace et bien organisée. C'est comme avoir une interface interactive, un système de traitement des données performant, et un outil de gestion avancé travaillant ensemble pour offrir une solution complète.

# Annexe 1 📜

```
---------------------------------------------------------------------
|                      Utilisateur                                   |
|                  (Saisie de données)                               |
---------------------------------------------------------------------
                                    |
                                    v
---------------------------------------------------------------------
|                      Streamlit (Frontend)                         |
|         (Interface utilisateur interactive)                        |
---------------------------------------------------------------------
                                    |
                                    v
---------------------------------------------------------------------
|                       FastAPI (Backend)                            |
|      (Traitement des requêtes et exécution du modèle)              |
---------------------------------------------------------------------
                                    |
                                    v
---------------------------------------------------------------------
|                          MLflow (MLOps)                            |
|      (Gestion et suivi des expérimentations de ML)                 |
---------------------------------------------------------------------
                                    ^
                                    |
---------------------------------------------------------------------
|                       FastAPI (Backend)                            |
|         (Retourne les résultats des prédictions)                   |
---------------------------------------------------------------------
                                    |
                                    v
---------------------------------------------------------------------
|                      Streamlit (Frontend)                         |
|         (Affichage des résultats à l'utilisateur)                  |
---------------------------------------------------------------------
                                    |
                                    v
---------------------------------------------------------------------
|                      Utilisateur                                   |
|                  (Visualisation des résultats)                     |
---------------------------------------------------------------------
```

# Annexe 2 🌐

- [How to build complete end to end ML model backend RestAPI using FastAPI and frontend UI using Streamlit](https://medium.com/@goradbj/how-to-build-complete-end-to-end-ml-model-backend-restapi-using-fastapi-and-front-end-ui-using-22f64bf04476)

![How to build complete end to end ML model backend RestAPI using FastAPI and frontend UI using Streamlit](https://github.com/hrhouma/begining_IA_part1/assets/10111526/c261da4e-7fa2-460b-9d5f-31d5bf3a7426)

# Annexe 3 🌟

- [Serving models using Streamlit & FastAPI](https://medium.com/@publiciscommerce/serving-models-using-streamlit-fastapi-a73af8da5ade)

![Serving models using Streamlit & FastAPI](https://github.com/hrhouma/begining_IA_part1/assets/10111526/43bc6e5a-9940-40eb-b9cc-1bac19c3c525)

# Annexe 4 🧪

- [How to Build an Instant Machine Learning Web Application with Streamlit and FastAPI](https://developer.nvidia.com/blog/how-to-build-an-instant-machine-learning-web-application-with-streamlit-and-fastapi/)

# Autres 📚

- [Use Model in Real Use Case Including Backend and Frontend Apps](https://akpolatcem.medium.com/use-model-in-real-use-case-including-backend-and-frontend-apps-f4d8164cba8b)
- [HR Attrition MLOps](https://github.com/silverstone1903/hr-attrition-mlops)
- [Ultimate FastAPI Tutorial Pt. 12 - React.js Frontend](https://christophergs.com/tutorials/ultimate-fastapi-tutorial-pt-12-react-js-frontend/)
- [MLflow Tracking](https://www.mlflow.org/docs/2.5.0/tracking.html)

# Images et références 🖼️

- [HR Attrition MLOps](https://github.com/silverstone1903/hr-attrition-mlops)

![HR Attrition MLOps](https://github.com/hrhouma/begining_IA_part1/assets/10111526/c91e2558-ebf3-4ad8-9cbd-e3ab5431392f)

- [Ultimate FastAPI Tutorial Pt. 12 - React.js Frontend](https://christophergs.com/tutorials/ultimate-fastapi-tutorial-pt-12-react-js-frontend/)

![Ultimate FastAPI Tutorial Pt. 12 - React.js Frontend](https://github.com/hrhouma/begining_IA_part1/assets/10111526/9e050b9e-625a-408a-8e70-809bad619b7f)

- [Serving models using Streamlit & FastAPI](https://medium.com/@publiciscommerce/serving-models-using-streamlit-fastapi-a73af8da5ade)

![Serving models using Streamlit & FastAPI](https://github.com/hrhouma/begining_IA_part1/assets/10111526/29be32f7-c962-4684-8c7e-76c1094bcc9f)

- [How to build complete end to end ML model backend RestAPI using FastAPI and frontend UI using Streamlit](https://medium.com/@goradbj/how-to-build-complete-end-to-end-ml-model-backend-restapi-using-fastapi-and-front-end-ui-using-22f64bf04476)

![How to build complete end to end ML model backend RestAPI using FastAPI and frontend UI using Streamlit](https://github.com/hrhouma/begining_IA_part1/assets/10111526/e0b90506-7b69-4294-873b-22a6106aae12)
