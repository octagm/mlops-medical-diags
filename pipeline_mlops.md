# Propuesta Rediseñada del Pipeline de MLOps - Diagnóstico de Enfermedades Comunes y Huérfanas
![Header](/assets/ml_pipeline_header.png)

## Objetivo

Diseñar un pipeline de Machine Learning capaz de predecir, a partir de los síntomas y datos clínicos de un paciente, si este podría estar afectado por una enfermedad común o una enfermedad huérfana. Este pipeline debe cubrir desde la ingesta de datos hasta el monitoreo en producción, incluyendo despliegue tanto local como en la nube.

---

## 📌 Supuestos

- El modelo debe ejecutarse localmente o en la nube.
- Los datos clínicos incluyen texto, imágenes y tablas.
- Se espera privacidad (HIPAA/GDPR).
- Los datos nuevos se integran frecuentemente.

---

## 🔄 Pipeline Rediseñado

---

### 1. Ingesta de Datos

![Ingesta](/assets/data_ingestion.png)

**Herramientas:**

![AWS Glue](/assets/aws-glue.png) ![Amazon S3](/assets/s3.png)

- **AWS Glue**: automatiza la extracción y limpieza de datos desde fuentes clínicas.
- **Amazon S3**: almacenamiento escalable para todos los datos recolectados.

---

### 2. Preprocesamiento

![Preprocessing](/assets/preprocessing.png)

**Herramientas:**

![SageMaker](/assets/sagemaker.png) ![Pandas](/assets/pandas.png) ![Scikit-learn](/assets/sklearn.png) ![NLTK](/assets/nltk.png)

- Imputación, codificación, normalización.
- Embeddings para texto y resize de imágenes médicas.
- Procesamiento reproducible vía SageMaker Processing Jobs.

---

### 3. División del Dataset

**Técnica:**
- `StratifiedKFold` para respetar proporción de clases.

---

### 4. Selección y Entrenamiento del Modelo

![Model Training](/assets/training.png)

**Modelos candidatos:**

![XGBoost](/assets/xgboost.png) ![Random Forest](/assets/randomforest.png) ![Neural Networks](/assets/nn.png) ![Transformers](/assets/transformers.png)

**Framework:**

![SageMaker](/assets/sagemaker.png)

- Entrenamiento automático y distribuido.
- El modelo con mejor **F1 Score + Recall** se selecciona.
- Soporte para **transfer learning** y **few-shot learning** para enfermedades raras.

---

### 5. Evaluación del Modelo

![Evaluation](/assets/evaluation.png)

**Herramientas:**

![SageMaker Experiments](/assets/experiments.png) ![MLflow](/assets/mlflow.png)

- F1 Score, AUC-ROC, Recall.
- Comparación de modelos y registro de resultados.

---

### 6. Empaquetamiento

![Packaging](/assets/packaging.png)

**Herramientas:**

![Docker](/assets/docker.png) ![SageMaker Registry](/assets/model-registry.png)

- Modelos versionados y empaquetados como imágenes.
- Preparación para despliegue local o en la nube.

---

### 7. Despliegue

![Deployment](/assets/deployment.png)

**Opciones:**
- **Local**: contenedor Docker.
- **Cloud**: SageMaker Endpoint (tiempo real) o Batch Transform.

---

### 8. Interfaz para Médicos

![User Interface](/assets/interface.png)

**Tecnologías:**

![React](/assets/react.png) ![Flask](/assets/flask.png)

- Web simple o aplicación de escritorio.
- Formulario para ingresar síntomas y obtener predicción.

---

### 9. Monitoreo del Modelo

![Monitoring](/assets/monitoring.png)

**Herramientas:**

![SageMaker Monitor](/assets/sagemaker-monitor.png) ![Grafana](/assets/grafana.png)

- Monitoreo de métricas de desempeño.
- Detección de desviaciones (data drift).
- Registro para retraining.

---

### 10. Reentrenamiento

![Retraining](/assets/retraining.png)

**Herramientas:**

![Airflow](/assets/airflow.png) ![Step Functions](/assets/stepfunctions.png)

- Reentrenamiento automático por condición o programación.
- Flujo orquestado en AWS o local.

---

### 11. Control de Versiones

![Version Control](/assets/versioning.png)

**Herramientas:**

![Git](/assets/git.png) ![DVC](/assets/dvc.png)

- Git para código.
- DVC para datos y modelos.
- Model Registry en SageMaker para trazabilidad.

---

### 12. Privacidad y Seguridad

![Security](/assets/security.png)

**Medidas:**
- Cifrado en tránsito y en reposo.
- IAM para controlar accesos.
- Arquitectura compatible con HIPAA.

---

## 🧭 Diagrama del Pipeline

_Agregar aquí imagen tipo diagrama (`pipeline_diagram.png`)_

---

## 🧾 CHANGELOG

Ver archivo [`CHANGELOG.md`](./CHANGELOG.md)

