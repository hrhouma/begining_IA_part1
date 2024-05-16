
==> IMPORTANT 1 - Référence : https://stackoverflow.com/questions/59823283/could-not-load-dynamic-library-cudart64-101-dll-on-tensorflow-cpu-only-install
==> IMPORTANT 2 - Pour vérifier les compatbilités des outils que nous allons installer, il est obligatoire de consulter ces deux liens : 
https://medium.com/@omkardalvi2001/gpu-for-machine-learning-cuda-cudnn-and-tensorflow-cb5f3ee4b5ac
https://stackoverflow.com/questions/50622525/which-tensorflow-and-cuda-version-combinations-are-compatible
==> IMPORTANT 3 - En se basant sur les références ci-haut, nous avons opté pour les choix suivants: 

**********************************************************************
*******************ÉTAPE 1 - DRIVER + CUDA ***************************
**********************************************************************

1 - Cuda 		-  version 10.1
2 - Tenserflow 	-  version tensorflow_gpu-2.1.0
3 - Python 		- environnement virtuel avec la version de python 3.6 (de 3.5 à 3.7)
4 - Ouvrir le navigateur anaconda (création d'un nouvel env nom : tensorflow-gpu-1 , version de python 3.6.x)
	Démarrer avec openterminal depuis le navigateur anaconda

1 - Vérifier votre version de carte graphique : 
		1.1 - Clique droit -> Device manager -> Display adapters
		Exemple : NVIDIA Geforce RTX 4060 LAptop GPU
2 - Installer les GPU Driver (du cas par cas) : 
		2.1 - Allez au site download GPU driver et remplir le formulaire selon votre config.
		2.2 - Ouvrir la ligne de commande et tester : **** nvidia-smi ****
		REF: https://medium.com/@totokk/nv-how-to-check-cuda-and-cudnn-version-e05aa21daf6c
3 - Installer CUDA (Absoulement - version 10.1 compatible avec une version spécifique de tensorflow)
		3.2 - Ouvrir la ligne de commande et tester : **** nvcc -version ****
		REF:https://medium.com/@totokk/nv-how-to-check-cuda-and-cudnn-version-e05aa21daf6c

FÉLICITATIONS !!!!!!!!!!!!!! CUDA est installé - version 10.1 


**********************************************************************
*******************ÉTAPE 2 - ANACONDA - PYTHON - TENSORFLOW **********
**********************************************************************

2.1 - Python - environnement virtuel avec la version de python 3.6 (de 3.5 à 3.7)
2.2 - Ouvrir le navigateur anaconda 
2.3 - création d'un nouvel env nom : tensorflow-gpu-1 , version de python 3.6.x)
2.4 - Démarrer avec openterminal depuis le navigateur anaconda
2.5 - Ouvrir le terminal et exécutez les commandes suivantes sur notre environnement virtuel

	1. python --version
	2. conda install tensorflow-gpu
	3. tester :  Cherchez les fichiers test ci-joint (ignorez le code en bas)
	
		
		3.1 (soit directement)
		python -c "import tensorflow as tf; print('GPU available:' if tf.test.is_gpu_available() else 'GPU not available')"
		3.2. écrire python pour rentrer dans python
			 >>> import tensorflow as tf
			 >>> print(tf.__version__)
	
		3.3. écrire python pour rentrer dans python
			 >>> import tensorflow as tf
			 >>> if tf.test.is_gpu_available(cuda_only=False, min_cuda_compute_capability=None):
					print("GPU is available")
				 else:
					print("GPU not available")

		3.4. écrire python pour rentrer dans python
			 >>> import tensorflow as tf
			 >>> print("Num GPUs Available: ", len(tf.config.experimental.list_physical_devices('GPU')))
	
		3.5. python 
		
			import tensorflow as tf

			# This line attempts to create a simple TensorFlow tensor specifically on the GPU.
			# If no GPU is available, TensorFlow will either throw an error or automatically use the CPU.
			try:
				with tf.device('/device:GPU:0'):
					a = tf.constant([[1.0, 2.0, 3.0], [4.0, 5.0, 6.0]])
					b = tf.constant([[1.0, 2.0], [3.0, 4.0], [5.0, 6.0]])
					c = tf.matmul(a, b)
				print("GPU is available and used for computation")
			except RuntimeError as e:
				print("GPU is not available: ", e)
		3.6. python 
		
			import tensorflow as tf
			gpus = tf.config.list_physical_devices('GPU')
			if gpus:
				try:
					# Currently, memory growth needs to be the same across GPUs
					for gpu in gpus:
						tf.config.experimental.set_memory_growth(gpu, True)
					logical_gpus = tf.config.experimental.list_logical_devices('GPU')
					print(len(gpus), "Physical GPUs,", len(logical_gpus), "Logical GPUs")
				except RuntimeError as e:
					# Memory growth must be set before GPUs have been initialized
					print(e)

			with tf.device('/GPU:0'):
				a = tf.constant([[1.0, 2.0, 3.0], [4.0, 5.0, 6.0]])
				b = tf.constant([[1.0, 2.0], [3.0, 4.0], [5.0, 6.0]])
				c = tf.matmul(a, b)
			print(c)


**********************************************************************
*******************ÉTAPE 3 - Installer CUDNN *************************
**********************************************************************


1 - Juste télécharger CUDNN et copier coller le contenu de (lib, include, bin) dans celui de cuda :
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\bin 
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\lib\x64
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\include

Vérifier svp qu'on a dans le path : 
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\bin
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.1\binjdhdjfhjqqchose voir larticle 

Référence : https://www.lavivienpost.com/install-tensorflow-gpu-on-windows-complete-guide/
2- Tester avant et apres les programmes test5.py au test8.py (ci-joint)
	
	

**********************************************************************
*******************ÉTAPE 4 - Visual studio env virtuel *************************
**********************************************************************

	
	python
	==> Si vous vlouez voir l'historique : doskey /history


https://medium.com/@sardiirfan27/how-to-install-tensorflow-with-gpu-support-on-windows-10-2022-8b9bf0fb2bda
https://medium.com/@vermavinay982/installing-tensorflow-603c7cd073da



**********************************************************************
*******************ÉTAPE 4 - TENSOR FLOW CPU SIMLEMENT *************************
**********************************************************************
https://medium.com/@teavanist/install-tensorflow-cpu-on-windows-10-4acbec6a71b7
https://medium.com/setup-pc-for-tensorflow/setup-pc-for-tensorflow-17a8ea6c629
https://www.youtube.com/watch?v=QpdjS9MrQNI&ab_channel=TheCodeCity





