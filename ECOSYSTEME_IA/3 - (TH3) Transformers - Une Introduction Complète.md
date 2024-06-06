# Transformers - Une Introduction Complète

## Table des Matières
1. [Introduction](#introduction)
2. [Origine et Contexte](#origine-et-contexte)
3. [Architecture des Transformers](#architecture-des-transformers)
   - [Mécanisme d'Attention](#mécanisme-dattention)
   - [Encodeurs et Décodeurs](#encodeurs-et-décodeurs)
4. [Modèles Préentraînés](#modèles-préentraînés)
   - [BERT](#bert)
   - [GPT](#gpt)
   - [T5](#t5)
5. [Applications des Transformers](#applications-des-transformers)
   - [Traitement du Langage Naturel (NLP)](#traitement-du-langage-naturel-nlp)
   - [Vision par Ordinateur](#vision-par-ordinateur)
   - [Autres Applications](#autres-applications)
6. [Bibliothèques et Outils](#bibliothèques-et-outils)
   - [Hugging Face](#hugging-face)
   - [TensorFlow et PyTorch](#tensorflow-et-pytorch)
7. [Exemples de Code](#exemples-de-code)
   - [Installation](#installation)
   - [Utilisation de base](#utilisation-de-base)
8. [Conclusion](#conclusion)
9. [Ressources Supplémentaires](#ressources-supplémentaires)

## Introduction
Les Transformers sont une architecture de réseau neuronal introduite pour la première fois par Vaswani et al. dans l'article "Attention is All You Need" en 2017. Cette architecture a révolutionné le domaine du traitement du langage naturel (NLP) et a trouvé des applications dans divers autres domaines de l'intelligence artificielle.

## Origine et Contexte
Avant les Transformers, les architectures récurrentes (RNN) et les LSTM étaient largement utilisées pour traiter les données séquentielles. Cependant, elles avaient des limitations en termes de parallélisation et de capacité à gérer de longues dépendances. Les Transformers ont surmonté ces limitations en utilisant un mécanisme d'attention qui permet de traiter les séquences en parallèle et de capturer des relations à long terme plus efficacement.

## Architecture des Transformers
L'architecture des Transformers repose principalement sur deux composants : les encodeurs et les décodeurs.

### Mécanisme d'Attention
Le mécanisme d'attention est au cœur des Transformers. Il permet au modèle de pondérer différemment les différentes parties de la séquence d'entrée, en se concentrant sur les parties les plus pertinentes pour la tâche en cours.

#### Formule de l'Attention
L'attention peut être calculée à l'aide de la formule suivante :

![image](https://github.com/hrhouma/begining_IA_part1/assets/10111526/9a52c7c9-9846-4160-b881-4ed5671db958)


### Encodeurs et Décodeurs
Les Transformers utilisent une pile d'encodeurs et de décodeurs. Chaque encodeur et décodeur est composé de couches d'attention suivies de couches de feed-forward.

#### Encodeur
Chaque encodeur dans le Transformer est composé de :
1. Une couche d'attention multi-têtes.
2. Une couche de réseau feed-forward entièrement connectée.

#### Décodeur
Chaque décodeur a une structure similaire à l'encodeur, mais avec une couche d'attention supplémentaire qui reçoit des informations des couches d'encodeurs correspondantes.

## Modèles Préentraînés
Les Transformers ont été utilisés pour créer plusieurs modèles préentraînés populaires qui ont repoussé les limites du NLP.

### BERT
BERT (Bidirectional Encoder Representations from Transformers) est un modèle de Transformer bidirectionnel préentraîné sur de vastes corpus de texte, permettant de capturer les relations contextuelles dans les deux sens.

### GPT
GPT (Generative Pre-trained Transformer) est un modèle de Transformer autoregressif développé par OpenAI, connu pour sa capacité à générer du texte de manière cohérente et contextuellement pertinente.

### T5
T5 (Text-to-Text Transfer Transformer) traite toutes les tâches NLP sous une même forme de conversion texte-à-texte, ce qui le rend très flexible et efficace pour une variété de tâches linguistiques.

## Applications des Transformers
Les Transformers ont de nombreuses applications dans divers domaines :

### Traitement du Langage Naturel (NLP)
- Traduction automatique
- Résumé de texte
- Réponse à des questions
- Analyse des sentiments

### Vision par Ordinateur
- Classification d'images
- Détection d'objets
- Segmentation d'images

### Autres Applications
- Modélisation de protéines
- Prédiction des structures chimiques
- Jeux et simulations

## Bibliothèques et Outils
Il existe plusieurs bibliothèques et outils pour travailler avec les Transformers :

### Hugging Face
Hugging Face propose la bibliothèque `transformers`, qui permet d'accéder facilement à une variété de modèles préentraînés et de les intégrer dans des applications.

### TensorFlow et PyTorch
Les frameworks populaires TensorFlow et PyTorch prennent en charge les Transformers et offrent des outils pour construire et entraîner ces modèles.

## Exemples de Code

### Installation
Pour installer la bibliothèque `transformers` de Hugging Face :
```bash
pip install transformers
```

### Utilisation de base
Voici un exemple simple d'utilisation de BERT pour l'inférence :
```python
from transformers import BertTokenizer, BertModel

# Charger le tokenizer et le modèle préentraîné
tokenizer = BertTokenizer.from_pretrained('bert-base-uncased')
model = BertModel.from_pretrained('bert-base-uncased')

# Prétraiter le texte d'entrée
input_text = "Hello, how are you?"
inputs = tokenizer(input_text, return_tensors="pt")

# Effectuer une inférence
outputs = model(**inputs)
last_hidden_states = outputs.last_hidden_state

print(last_hidden_states)
```

## Conclusion
Les Transformers ont révolutionné le domaine de l'intelligence artificielle, en particulier le traitement du langage naturel. Leur architecture efficace et polyvalente continue de trouver des applications dans divers domaines, et les outils comme Hugging Face rendent ces technologies accessibles à tous.

## Ressources Supplémentaires
- [Article original "Attention is All You Need"](https://arxiv.org/abs/1706.03762)
- [Documentation de Hugging Face Transformers](https://huggingface.co/transformers/)
- [Tutoriels TensorFlow sur les Transformers](https://www.tensorflow.org/tutorials/text/transformer)
- [Tutoriels PyTorch sur les Transformers](https://pytorch.org/tutorials/beginner/transformer_tutorial.html)
