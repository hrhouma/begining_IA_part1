# Utilisation de Streamlit, FastAPI et MLflow dans un projet de Machine Learning 🚀

## Présentation

Pour développer une application de Machine Learning, nous pouvons utiliser trois outils principaux : Streamlit, FastAPI, et MLflow. Voici comment chacun de ces outils fonctionne et comment ils peuvent être utilisés ensemble.

## Streamlit (Frontend) 🖥️

### Rôle de Streamlit

**Streamlit** est comme une vitrine de magasin. C'est l'interface où les utilisateurs viennent interagir avec votre application de Machine Learning. Imaginez que vous avez une application qui prédit les rendements des cultures. Avec Streamlit, vous pouvez créer une page web où les utilisateurs peuvent entrer des informations sur leurs champs (comme la taille, le type de sol, etc.) et voir le rendement prédit par le modèle.

### Exemple de la vie réelle

Pensez à Streamlit comme un kiosque interactif dans un centre commercial. Les clients (utilisateurs) peuvent toucher l'écran, entrer des informations, et voir les résultats instantanément.

## FastAPI (Backend) 🍽️

### Rôle de FastAPI

**FastAPI** est comme la cuisine d'un restaurant. C'est là où toutes les commandes des clients (données des utilisateurs) sont envoyées pour être traitées. FastAPI reçoit les données de Streamlit, utilise le modèle de Machine Learning pour faire des prédictions, et renvoie les résultats à Streamlit.

### Exemple de la vie réelle

Imaginez que Streamlit est le serveur de restaurant qui prend les commandes des clients. Le serveur envoie ces commandes à la cuisine (FastAPI) où les plats (prédictions) sont préparés et ensuite renvoyés au serveur pour être servis aux clients.

## MLflow (MLOps) 🔬

### Rôle de MLflow

**MLflow** est comme le laboratoire de recherche et développement d'une entreprise de cosmétiques. C'est l'endroit où les scientifiques (data scientists) expérimentent avec différentes formules (modèles de Machine Learning) pour trouver celle qui fonctionne le mieux. MLflow garde une trace de toutes ces expériences, des ingrédients (paramètres) utilisés, et des résultats obtenus.

### Exemple de la vie réelle

Imaginez une entreprise de cosmétiques qui teste plusieurs formules pour créer une nouvelle crème anti-âge. Chaque formule est testée sur plusieurs volontaires, et les résultats sont soigneusement notés. MLflow fait la même chose pour les modèles de Machine Learning : il suit les différentes versions des modèles, les paramètres utilisés, et les performances obtenues.

## Workflow d'intégration 🔄

### Exemple de projet complet

Imaginons que vous développez une application qui aide les agriculteurs à prévoir les rendements de leurs cultures.

1. **Développement du modèle avec MLflow** :
   - Les data scientists testent plusieurs modèles de Machine Learning pour prédire les rendements.
   - Ils utilisent MLflow pour enregistrer les résultats de chaque test, comme un journal de laboratoire.
   - Exemple : Tester différents types de sol, quantités d'eau, et types de graines pour trouver la meilleure combinaison.

2. **Déploiement du modèle avec FastAPI** :
   - Une fois le meilleur modèle trouvé, il est intégré dans FastAPI.
   - FastAPI sert de cuisine où les nouvelles données des agriculteurs sont envoyées pour prédiction.
   - Exemple : Recevoir les données des champs des agriculteurs et prédire le rendement attendu.

3. **Interface utilisateur avec Streamlit** :
   - Streamlit est utilisé pour créer une application web où les agriculteurs peuvent entrer les données de leurs champs.
   - Les agriculteurs obtiennent des prédictions instantanées sur leurs rendements grâce à l'interface utilisateur.
   - Exemple : Une page web où les agriculteurs peuvent entrer des informations sur leurs champs et voir les prédictions de rendement.

## Conclusion 📊

En utilisant Streamlit pour l'interface utilisateur, FastAPI pour le traitement des données, et MLflow pour la gestion et le suivi des modèles de Machine Learning, vous pouvez créer une application de Machine Learning efficace et bien organisée. C'est comme avoir une vitrine interactive, une cuisine efficace, et un laboratoire de recherche avancé travaillant ensemble pour offrir une solution complète.

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
