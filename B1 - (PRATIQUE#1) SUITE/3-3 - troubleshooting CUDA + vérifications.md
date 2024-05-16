# Vérifier la Présence d'un GPU sur Windows 11

Ce guide vous montre comment utiliser la ligne de commande pour vérifier si votre ordinateur portable dispose d'un GPU (Graphical Processing Unit) sous Windows 11.

## Ouvrir l'Invite de Commande

1. Utilisez le bouton de recherche dans la barre des tâches.
2. Tapez `cmd`.
3. Cliquez sur `Invite de commandes` dans les résultats.

## Utiliser la Commande `dxdiag`

1. Dans l'invite de commande, tapez `dxdiag` et appuyez sur Entrée.
    - L'outil de diagnostic DirectX s'ouvrira.
2. Si c'est la première utilisation, une fenêtre peut demander si vous voulez vérifier la signature numérique des pilotes. Choisissez `Oui` ou `Non`, selon votre préférence.
3. Attendez que la barre de progression en bas termine.

## Vérifier les Informations du GPU

1. Dans l'outil de diagnostic DirectX, sélectionnez l'onglet `Affichage` ou `Écran`.
    - Vous y trouverez les informations sur votre GPU, comme le fabricant (ex. NVIDIA, AMD, Intel) et le modèle de la carte graphique.

**Note :** Si vous trouvez des informations concernant NVIDIA ou AMD sous cet onglet, cela signifie que votre ordinateur dispose d'un GPU dédié. Des informations sur Intel ou AMD intégré indiquent l'absence de GPU dédié.

Ce guide rapide vous aide à identifier la configuration matérielle graphique de votre ordinateur portable sans nécessité de démontage ou recherche de spécifications en ligne.

Ce fichier README.md vous guide étape par étape pour vérifier la présence et le type de GPU dans votre ordinateur portable Windows 11, en utilisant uniquement des outils intégrés au système d'exploitation.
