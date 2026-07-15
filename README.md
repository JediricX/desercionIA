# desercionIA
En este repositorio se almacena el proyecto de tesis de grado para la maestría en IA. Contiene el modelo IA para la predicción temprana de abandono universitario en modeldidad online
# Sistema de Alerta Temprana con IA para la Predicción de la Deserción Universitaria

Este proyecto implementa un modelo de **aprendizaje automático supervisado** para predecir el riesgo de abandono en programas universitarios a distancia, utilizando el dataset **OULAD (Open University Learning Analytics Dataset)**.  
El objetivo es ofrecer a las instituciones educativas una herramienta preventiva para la **retención estudiantil**.

---

## 🚀 Objetivo
Diseñar e implementar un **Sistema de Alerta Temprana (SAT)** basado en Inteligencia Artificial que compare el rendimiento de algoritmos de clasificación supervisada:
- Random Forest  
- Árboles de Decisión  
- XGBoost  
- Regresión Logística  

---

## 🧩 Estructura del proyecto

├── data/
│   ├── raw/
│   │   ├── assessments.csv
│   │   ├── courses.csv
│   │   ├── studentAssessment.csv
│   │   ├── studentInfo.csv
│   │   ├── studentRegistration.csv
│   │   ├── vle.csv
│   │   └── studentVle.csv
│   └── processed/
│       └── student_data_clean.csv
├── notebooks/
│   ├── 01_EDA.ipynb
│   ├── 02_FeatureEngineering.ipynb
│   ├── 03_ModelTraining.ipynb
│   └── 04_Evaluation.ipynb
├── src/
│   ├── preprocessing.py
│   ├── modeling.py
│   ├── evaluation.py
│   └── utils.py
├── requirements.txt
└── README.md


---

## ⚙️ Instalación

1. Clona el repositorio:
   
	git clone https://github.com/JediricX/desercionIA.git
   	cd desercionIA

2. Crea y activa el entorno virtual:

	python -m venv venv
	source venv/bin/activate  # Linux/Mac
	venv\Scripts\activate     # Windows

3. Instala las dependencias:

	pip install -r requirements.txt

## 🧠 Ejecución del modelo
1. Descarga los datos OULAD desde Kaggle:

import kagglehub
from kagglehub import KaggleDatasetAdapter

dataset = kagglehub.load_dataset(
    KaggleDatasetAdapter.PANDAS,
    "anlgrbz/student-demographics-online-education-dataoulad",
    "studentInfo.csv"
)

2. Ejecuta el pipeline principal:

	python src/modeling.py

3. Los resultados se guardan en:

	/data/processed/student_data_clean.csv
	/results/model_metrics.json

🧮 Reproducibilidad
Para garantizar resultados consistentes, se fijan las siguientes seeds:

import numpy as np
import random
import torch

SEED = 42
np.random.seed(SEED)
random.seed(SEED)
torch.manual_seed(SEED)

📊 Métricas de evaluación

Accuracy
F1-Score
ROC-AUC
Matriz de confusión

🧰 Herramientas utilizadas

Python 3.10+
Scikit-learn
Imbalanced-learn
Pandas / NumPy
Matplotlib / Seaborn
KaggleHub
XGBoost

📂 Rutas de acceso a los datos OULAD

| Dataset 			                | Ruta local 				                    | Descripción 		                                    |
| --- 				                  | --- 				    	                    | ---                                                 |
| ``assessments.csv`` 		      | ``data/raw/assessments.csv`` 		      | Evaluaciones y pesos 			                          |
| ``courses.csv`` 		          | ``data/raw/courses.csv`` 		          | Información de módulos 		                          |
| ``studentAssessment.csv`` 	  | ``data/raw/studentAssessment.csv`` 	  | Resultados individuales 		                        |
| ``studentInfo.csv`` 		      | ``data/raw/studentInfo.csv`` 		      | Datos demográficos y resultado final 	              |
| ``studentRegistration.csv`` 	| ``data/raw/studentRegistration.csv`` 	| Fechas de registro y baja 		                      |
| ``vle.csv`` 			            | ``data/raw/vle.csv`` 			            | Tipos de actividad virtual 		                      |
| ``studentVle.csv`` 		        | ``data/raw/studentVle.csv`` 		      | Interacciones del estudiante en el entorno virtual  |

👥 Autores
Richard Humberto Campos Ballesteros
José Enrique Andía Tello
