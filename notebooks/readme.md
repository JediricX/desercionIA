# Sistema de Alerta Temprana con Inteligencia Artificial para la Predicción de la Deserción en Educación Superior a Distancia

Repositorio oficial del Trabajo Fin de Estudios (TFE) del Máster Universitario en Inteligencia Artificial de la UNIR.

## Descripción del Proyecto
Este proyecto implementa un Sistema de Alerta Temprana (SAT) basado en Machine Learning (Random Forest) para predecir el riesgo de abandono escolar en programas universitarios a distancia. Utiliza como entorno empírico el repositorio público OULAD (*Open University Learning Analytics Dataset*), analizando la huella digital y el rendimiento temprano en la ventana de las primeras 4 semanas ($t \le 28$ días).

## Estructura del Repositorio
* `Modelo_Predictivo_Alerta_Temprana_Final.ipynb`: Cuaderno interactivo unificado que ejecuta la cadena de valor completa del proyecto en orden secuencial (Ingesta, EDA, Ingeniería de Características con ventana de 28 días, balanceo SMOTE confinado al entrenamiento, modelado comparativo y explicabilidad con SHAP).
* `random_forest_tuned_model.joblib`: Artefacto binario que almacena el modelo Random Forest optimizado y calibrado para inferencias en producción.
* `data/`: Directorio reservado para las fuentes de datos crudas (`data/raw`).
* `src/`: Scripts ejecutables de soporte técnico y pruebas unitarias.
* `requirements.txt`: Archivo de dependencias y librerías necesarias para la ejecución de los experimentos.

## Requisitos e Instalación
Para replicar el entorno de desarrollo y ejecutar el cuaderno interactivo, asegúrese de instalar las dependencias ejecutando el siguiente comando en su terminal:

```bash
pip install -r requirements.txt