# installation de cuda sur Windows 10 et 11

### Étape 1 : Vérification de la compatibilité de votre GPU
Avant tout, vérifiez si votre carte graphique NVIDIA supporte CUDA. Vous pouvez le faire en cherchant les spécifications de votre modèle de carte graphique sur le site de NVIDIA ou en consultant la liste des GPU compatibles CUDA sur le site de NVIDIA.

### Étape 2 : Mise à jour du pilote de votre carte graphique
Il est crucial que le pilote de votre carte graphique soit à jour. Voici comment le faire :

1. **Visitez le site NVIDIA** : Allez sur [www.nvidia.com](http://www.nvidia.com) et cliquez sur "Pilotes" (ou "Drivers") dans le menu.
2. **Recherche de pilote** : Utilisez l'outil de recherche pour trouver le pilote correspondant à votre modèle de carte graphique et votre version de Windows.
3. **Téléchargez et installez le pilote** : Téléchargez le pilote et suivez les instructions d'installation.

### Étape 3 : Téléchargement du CUDA Toolkit
1. **Accédez à la page de téléchargement du CUDA Toolkit** sur le site de NVIDIA : [CUDA Toolkit Download](https://developer.nvidia.com/cuda-downloads).
2. **Sélectionnez votre système d'exploitation** : Choisissez "Windows".
3. **Sélectionnez votre version de Windows**, votre type de kit (ex : exécutable pour Windows) et la version de CUDA que vous souhaitez installer.
4. **Téléchargez l'installateur** en cliquant sur le bouton de téléchargement.

### Étape 4 : Installation du CUDA Toolkit
1. **Ouvrez l'installateur** que vous avez téléchargé.
2. **Acceptez l'accord de licence** après l'avoir lu.
3. **Choisissez le type d'installation** : Vous pouvez choisir l'installation Express (recommandée pour la plupart des utilisateurs) ou l'installation Personnalisée pour sélectionner manuellement les composants à installer.
4. **Suivez les instructions** jusqu'à la fin de l'installation.

### Étape 5 : Vérification de l'installation
Pour confirmer que CUDA est correctement installé :

1. **Ouvrez l'invite de commande** : Appuyez sur les touches Windows + R, tapez `cmd` et appuyez sur Entrée.
2. **Tapez la commande suivante et appuyez sur Entrée** :
   ```
   nvcc --version
   ```
   Si CUDA est correctement installé, cette commande affichera la version de CUDA installée.

### Étape 6 : Tester CUDA (Optionnel)
Si vous avez choisi d'installer les exemples de code pendant l'installation de CUDA, vous pouvez les utiliser pour tester si CUDA fonctionne correctement sur votre système.

1. **Naviguez vers le répertoire des exemples de code CUDA** (habituellement `C:\ProgramData\NVIDIA Corporation\CUDA Samples\v<version>\`) dans l'explorateur de fichiers.
2. **Ouvrez l'exemple de projet Visual Studio** correspondant à un exemple simple, tel que `0_Simple/vectorAdd`.
3. **Compilez et exécutez l'exemple** selon les instructions spécifiques à celui-ci, généralement disponibles dans le fichier README associé.

Si l'exemple s'exécute et se termine correctement, cela indique que CUDA est opérationnel sur votre système.
