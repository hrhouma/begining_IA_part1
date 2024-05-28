### Méthode 1 : Utiliser `venv` avec PowerShell (Windows)

```powershell
# Naviguez vers le répertoire de votre projet
cd C:\Users\Haythem\Desktop\fastapi\fastapi-the-complete-course\

# Créez un environnement virtuel
python3 -m venv .monenv

# Activez l'environnement virtuel
cd .\.monenv\Scripts\
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
.\Activate.ps1

# Pour désactiver l'environnement virtuel
deactivate
```

### Méthode 2 : Utiliser `conda` (Windows/Linux)

```bash
# Créez un environnement virtuel
conda create --name monenv python=3.x

# Activez l'environnement virtuel
conda activate monenv

# Pour désactiver l'environnement virtuel
conda deactivate
```

### Méthode 3 : Utiliser `venv` avec Bash (Linux)

```bash
# Naviguez vers le répertoire de votre projet
cd /chemin/vers/votre/projet

# Créez un environnement virtuel
python3 -m venv kafka_env

# Activez l'environnement virtuel
source kafka_env/bin/activate

# Pour désactiver l'environnement virtuel
deactivate
```
# Résumé
### Méthode 1 : Utiliser `venv` avec PowerShell (Windows)

```powershell
cd C:\Users\Haythem\Desktop\fastapi\fastapi-the-complete-course\
python3 -m venv .monenv
cd .\.monenv\Scripts\
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
.\Activate.ps1
deactivate
```

### Méthode 2 : Utiliser `conda` (Windows/Linux)

```bash
conda create --name monenv python=3.x
conda activate monenv
conda deactivate
```

### Méthode 3 : Utiliser `venv` avec Bash (Linux)

```bash
cd /chemin/vers/votre/projet
python3 -m venv kafka_env
source kafka_env/bin/activate
deactivate
```
