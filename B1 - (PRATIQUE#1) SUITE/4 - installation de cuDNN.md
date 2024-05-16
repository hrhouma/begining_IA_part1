# Prérequis :
Pour utiliser cuDNN (CUDA Deep Neural Network library) avec CUDA sur un système Windows, vous devez d'abord avoir installé CUDA. Si vous n'avez pas encore installé CUDA, veuillez vous référer au guide d'installation de CUDA. Une fois que vous avez confirmé que CUDA est correctement installé sur votre système, vous pouvez suivre ces étapes pour installer cuDNN.

# Guide d'Installation de cuDNN sur Windows

Ce guide suppose que vous avez déjà installé CUDA sur votre système Windows. Suivez ces étapes pour installer cuDNN et le configurer pour qu'il fonctionne avec CUDA.

## Étape 1 : Téléchargement de cuDNN

1. **Créez un compte NVIDIA ou connectez-vous** sur le [site NVIDIA Developer](https://developer.nvidia.com/).
2. **Visitez la page de téléchargement cuDNN** à l'adresse [cuDNN Download](https://developer.nvidia.com/cudnn).
3. **Sélectionnez la version de cuDNN** compatible avec votre version de CUDA. Assurez-vous de choisir la version de cuDNN qui correspond à la version de CUDA installée sur votre système.
4. **Téléchargez l'archive cuDNN pour Windows** (par exemple, `cudnn-x.x-windows-x64-v8.x.x.x.zip`). Le fichier exact variera en fonction de la version de cuDNN que vous choisissez de télécharger.

## Étape 2 : Extraction de cuDNN

1. **Localisez le fichier ZIP téléchargé** et extrayez-le. Vous pouvez utiliser l'explorateur de fichiers Windows pour cela, en cliquant avec le bouton droit sur le fichier ZIP et en sélectionnant `Extraire tout...`.
2. **Ouvrez le dossier extrait**. Vous devriez voir des dossiers comme `bin`, `include`, et `lib`.

## Étape 3 : Copie des Fichiers cuDNN

1. **Copiez les fichiers depuis le dossier extrait** vers l'emplacement d'installation de CUDA sur votre disque dur.
   - **Binaires** : Copiez le contenu du dossier `bin\` de cuDNN vers `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\vX.X\bin\`, où `X.X` est votre version de CUDA.
   - **En-têtes** : Copiez `include\cudnn.h` de cuDNN vers `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\vX.X\include\`.
   - **Librairies** : Copiez le contenu du dossier `lib\x64\` de cuDNN vers `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\vX.X\lib\x64\`.

## Étape 4 : Configuration des Variables d'Environnement

1. **Ouvrez les Paramètres de Système Avancés**. Appuyez sur les touches Windows + Pause, puis cliquez sur `Paramètres système avancés` sur le côté droit.
2. **Dans l'onglet `Paramètres système avancés`, cliquez sur `Variables d'environnement`**.
3. Sous `Variables système`, faites défiler jusqu'à trouver la variable `Path` et sélectionnez-la. Cliquez sur `Modifier...`.
4. **Ajoutez le chemin du dossier `bin` de CUDA** (si ce n'est pas déjà fait) en cliquant sur `Nouveau` et en tapant `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\vX.X\bin`.
5. **Faites de même pour le dossier `libnvvp`** : Ajoutez `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\vX.X\libnvvp`.

## Étape 5 : Vérification de l'Installation

Pour vérifier que cuDNN est correctement installé et configuré :

1. **Ouvrez une nouvelle invite de commande** (cmd).
2. Tapez `nvcc -V` pour vérifier que CUDA est bien installé. Vous devriez voir la version de CUDA s'afficher.
3. Il n'y a pas de commande directe pour vérifier cuDNN, mais vous pouvez tester son fonctionnement en exécutant un programme ou un script qui utilise cuDNN. Les exemples de code fournis dans les archives CUDA peuvent servir à cela.

## Conseils supplémentaires

- Assurez-vous que tous les chemins sont corrects et correspondent à votre version spécifique de CUDA.
- Redémarrez votre ordinateur après l'installation pour vous assurer que toutes les modifications prennent effet.
- Consultez la documentation spécifique de NVIDIA et les forums pour toute aide supplémentaire ou en cas de problèmes lors de l'installation.

