# 1 - Librairies Python les plus utilisés en 2023  (CPU) ?

**Requêtes HTTP et Développement Web :**
- Requests: Pour les requêtes HTTP simplifiées.
- FastAPI: Cadre moderne pour le développement rapide d'APIs.
- aiohttp: Client/serveur HTTP asynchrone.

**Programmation Asynchrone :**
- Asyncio: Pour l'écriture de code asynchrone avec la syntaxe async/await.

**Interfaces Graphiques Utilisateur (GUI) :**
- Tkinter: Outil standard pour créer des applications GUI en Python.

**Manipulation de Données :**
- Pandas: Pour la manipulation et l'analyse des données.

**Visualisation de Données :**
- Matplotlib: Pour créer des visualisations statiques, interactives et animées.
- Seaborn: Pour des visualisations statistiques attrayantes basées sur Matplotlib.
- Plotly: Pour des visualisations de données interactives.

**Apprentissage Automatique (Machine Learning) :**
- Scikit-Learn: Outils simples et efficaces pour l'analyse prédictive des données.
- LightGBM, XGBoost, CatBoost: Bibliothèques pour le boosting de gradient.

**Modélisation Statistique :**
- Statsmodels: Pour estimer divers modèles statistiques et réaliser des tests statistiques.

Cette liste n'est pas exhaustive.

# 2 - Les bibliothèques Python prenant en charge le GPU (GPU) ?

Les bibliothèques Python prenant en charge le GPU sont souvent utilisées pour des calculs intensifs, comme le traitement de données volumineuses ou l'apprentissage automatique. Voici un tableau résumant quelques-unes de ces bibliothèques et leurs équivalents standard en CPU :

| CPU             | GPU              | Utilisation                                        |
|-----------------|------------------|----------------------------------------------------|
| NumPy           | CuPy             | Calcul numérique généraliste                       |
| SciPy           | CuPy/PyCUDA      | Algorithmes scientifiques et techniques            |
| Pandas          | cuDF             | Manipulation et analyse de données                 |
| Scikit-Learn    | cuML             | Apprentissage automatique                          |
| Matplotlib      | ---              | Visualisation de données (pas d'équivalent direct) |
| Seaborn         | ---              | Visualisation de données (pas d'équivalent direct) |
| Plotly          | ---              | Visualisation interactive (supporte le GPU indirectement via Dask) |
| LightGBM        | LightGBM avec support GPU | Boosting de gradient                          |
| XGBoost         | XGBoost avec support GPU  | Boosting de gradient                          |
| CatBoost        | CatBoost avec support GPU | Boosting de gradient                          |
| Statsmodels     | ---              | Modélisation statistique (pas d'équivalent direct) |
| TensorFlow      | TensorFlow avec support GPU | Réseaux de neurones profonds                  |
| PyTorch         | PyTorch avec support GPU   | Réseaux de neurones profonds                  |

Il est important de noter que certaines bibliothèques comme Matplotlib, Seaborn et Statsmodels n'ont pas d'équivalents directs en GPU car elles ne sont pas axées sur des calculs lourds où le GPU offrirait un avantage significatif. Cependant, pour les tâches de visualisation de données, le calcul des données peut être accéléré avec le GPU avant la visualisation.

Pour la visualisation interactive, Plotly peut utiliser le GPU indirectement à travers Dask pour gérer de gros volumes de données, mais le rendu final est généralement effectué sur le CPU.

Les bibliothèques d'apprentissage automatique comme LightGBM, XGBoost, et CatBoost offrent des options pour utiliser le GPU afin d'accélérer l'entraînement des modèles.

TensorFlow et PyTorch sont des bibliothèques de réseaux de neurones profonds qui ont une intégration native avec le GPU, permettant un traitement et un entraînement des modèles beaucoup plus rapides sur des données de grande taille.
