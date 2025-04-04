﻿# **DeepSeek con Ollama**
 
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

Este proyecto integra el modelo DeepSeek en Ollama, permitiendo su carga y ejecución de manera sencilla. A continuación, se detallan los pasos para instalar las dependencias, configurar y ejecutar el modelo.

## **Requisitos**

Antes de comenzar, asegúrate de tener Python 3.7 o superior instalado. Además, necesitarás algunas bibliotecas para interactuar con el modelo DeepSeek en Ollama.

# **Hugging Face Env**
```bash
pip install -U "huggingface_hub[cli]"
huggingface-cli login
```

### **Instalar Dependencias**

Para instalar las dependencias básicas, usa el siguiente comando:
```bash
pip install ollama huggingface_hub transformers
```

Si planeas usar aceleración en GPU, también necesitarás instalar los siguientes paquetes de PyTorch:

```bash
pip install torch torchvision torchaudio
```
Crear el modelo en Ollama a partir del archivo Modelfile:
```bash
ollama create velas-assistant -f ollama.modelfile
```

Ejecutar el modelo:
```bash
ollama run velas-assistant
```

Descargar el modelo (en caso de que ya esté disponible en Ollama):
```bash
ollama pull velas-assistant
```

Ejecutar el modelo descargado:
```bash
ollama run velas-assistant
```

Crear el modelo a partir de un directorio local (si tienes el modelo en una carpeta específica):
```bash
ollama create velas-assistant ./velas_model
```

El archivo DownloadHuggingFace.py descarga el modelo DeepSeek desde Hugging Face y lo guarda localmente en la carpeta ./velas_model.
```bash
python DownloadHuggingFace.py
```

El archivo SaveHuggingFace.py guarda el modelo y el tokenizador en la carpeta local ./velas_model y sube el modelo a tu repositorio en Hugging Face.
```bash
python SaveHuggingFace.py
```

El archivo Trainning.py realiza el entrenamiento del modelo DeepSeek con un conjunto de datos personalizado utilizando la clase Trainer de Hugging Face.
```bash
python Trainning.py
```

El archivo UploadHuggingFace.py sube el modelo entrenado a Hugging Face, en el repositorio especificado.
```bash
python UploadHuggingFace.py
```

python -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate
pip install -r requirements.txt
