# LABORATOIRE 2 - Évaluation Pratique de Laboratoire sur Streamlit

# 1 - Objectif

- Créer une application Streamlit complète qui permet de télécharger et visualiser des données, d'effectuer des calculs simples, et de générer des graphiques interactifs.

# 2 - Instructions

1. **Installation et préparation :**
   - Assurez-vous que Streamlit est installé dans votre environnement. Utilisez la commande suivante pour installer Streamlit si ce n'est pas déjà fait :
     ```bash
     pip install streamlit
     ```

2. **Création du fichier principal :**
   - Créez un fichier nommé `lab_app.py` où vous allez écrire tout le code pour cette évaluation.

3. **Structure de l'application :**
   - Ajoutez un titre à votre application avec `st.title`.
   - Créez trois sections principales dans l'application : 
     1. Téléchargement et affichage de données
     2. Calculs simples
     3. Génération de graphiques

4. **Téléchargement et affichage de données :**
   - Utilisez `st.file_uploader` pour permettre à l'utilisateur de télécharger un fichier CSV.
   - Affichez le contenu du fichier CSV dans un tableau avec `st.dataframe`.

5. **Calculs simples :**
   - Créez des champs d'entrée pour permettre à l'utilisateur d'entrer deux nombres.
   - Ajoutez des boutons pour effectuer des opérations d'addition, de soustraction, de multiplication et de division.
   - Affichez le résultat de l'opération sélectionnée.

6. **Génération de graphiques :**
   - Permettez à l'utilisateur de sélectionner une colonne de données pour générer un graphique.
   - Utilisez `st.line_chart` ou `st.bar_chart` pour afficher le graphique basé sur la colonne sélectionnée.

7. **Test de l'application :**
   - Exécutez votre application avec la commande suivante :
     ```bash
     streamlit run lab_app.py
     ```
   - Testez toutes les fonctionnalités pour vous assurer qu'elles fonctionnent correctement.
   - Capturez des captures d'écran des différentes sections de l'application en fonctionnement.

# 3 - Consignes de soumission

1. Téléchargez votre fichier `lab_app.py`.
2. Capturez des captures d'écran des différentes sections de votre application en fonctionnement.
3. Soumettez le fichier `lab_app.py` et les captures d'écran comme preuve de votre travail.

# 4 - Critères d'évaluation

- **Correctitude** : Les fonctionnalités demandées fonctionnent comme prévu.
- **Organisation du code** : Le code est bien structuré et lisible.
- **Interactivité** : L'application est interactive et réactive aux entrées de l'utilisateur.
- **Présentation** : L'interface utilisateur est propre et bien organisée.

# 5 - Objectif : 
- Utiliser Streamlit pour créer des applications interactives, manipuler des données, et générer des graphiques.
