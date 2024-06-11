# Commandes IA
1. **SSH into the Ubuntu Server:**
   ```
   ssh eleve@192.168.50.3 -P
   ```

2. **Attempting to run xeyes and encountering an error:**
   ```
   xeyes
   xeye
   xeyes
   ```

3. **Logging out and re-SSHing:**
   ```
   exit
   ssh eleve@192.168.50.3 -P
   ```

4. **Switching to root user:**
   ```
   su
   ```

5. **Navigating directories and activating a Python virtual environment:**
   ```
   ls
   cd demo1/demo1-mlflow
   source mlflowenv1/bin/activate
   ```

6. **Running and editing Python scripts, starting MLflow UI:**
   ```
   cat train.py
   python3 train.py
   nano train.py
   python3 train.py
   mlflow ui
   ```

7. **Handling interruptions and deactivating the environment:**
   ```
   ^C
   deactivate
   cd ..
   cd ..
   ```

8. **Cloning Git repositories and setting up another environment:**
   ```
   git clone https://github.com/hrhouma/demo2-mlflow.git
   mkdir demo2
   cd demo2
   git clone https://github.com/hrhouma/demo2-mlflow.git
   cd demo2-mlflow
   ls
   python3 -m venv env
   source env/bin/activate
   pip install -r requirements.txt
   ```

9. **Running another Python script and managing MLflow UI:**
   ```
   python3 train_model.py
   mlflow ui
   bg
   fg
   mlflow ui &
   mlflow ui > /dev/null
   ```

10. **Background and foreground process management:**
   ```
   bg
   fg
   ```

11. **Client loop disconnection and reconnection:**
   ```
   client_loop: send disconnect: Connection reset
   ssh eleve@192.168.50.3 -P
   ```

These commands cover accessing the server, navigating directories, activating Python virtual environments, handling Python scripts with MLflow tracking, and managing MLflow UI sessions.
