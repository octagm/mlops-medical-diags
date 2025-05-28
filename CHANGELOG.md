# 📝 CHANGELOG - Propuesta Pipeline MLOps

## Comparación entre Propuesta Original (Semana 1) y Propuesta Rediseñada (Semana Final)

---

### 🚀 Nuevas Tecnologías Incorporadas

| Etapa                         | Propuesta Original                               | Propuesta Rediseñada                                                                 |
|------------------------------|--------------------------------------------------|--------------------------------------------------------------------------------------|
| Ingesta de Datos             | No especificado                                  | AWS Glue, Amazon S3                                                                 |
| Preprocesamiento             | General, manual                                  | SageMaker Processing, Pandas, Scikit-learn, NLTK                                    |
| Modelado                     | Random Forest, XGBoost, Redes Neuronales         | + Transfer Learning, Transformers, entrenamiento distribuido en SageMaker           |
| Evaluación                   | Métricas básicas (F1, AUC)                       | + Registro de experimentos con MLflow, SageMaker Experiments                        |
| Empaquetamiento              | Docker                                           | Docker + SageMaker Model Registry                                                   |
| Despliegue                   | Local con Docker y API                           | + SageMaker Endpoints / Batch Transform (para nube)                                 |
| Interfaz de usuario          | HTML básico                                      | React frontend o aplicación de escritorio con Flask API                             |
| Monitoreo del Modelo         | Métricas manuales                                | SageMaker Model Monitor, Prometheus, Grafana                                        |
| Reentrenamiento              | Manual o programado                              | Automatizado con AWS Step Functions o Apache Airflow                                |
| Control de versiones         | Git                                              | Git + DVC + SageMaker Model Registry                                                |
| Seguridad y privacidad       | Mención general a HIPAA y GDPR                   | IAM, cifrado en S3 y SageMaker, cumplimiento explícito de normas de privacidad      |

---

### ✅ Expansión y Detalle por Etapa

- Se añadieron supuestos explícitos al inicio del documento.
- Cada etapa ahora tiene:
  - Una imagen representativa o ícono.
  - Logos de herramientas sugeridas.
  - Justificación técnica para cada herramienta.
- El pipeline se alinea con buenas prácticas modernas de MLOps (automatización, monitoreo, reentrenamiento continuo).

---

### 🛠 Formato y Accesibilidad

- El nuevo pipeline está documentado en Markdown (`mlops_pipeline.md`) y puede ser renderizado directamente en GitHub.
- Se incluye este `CHANGELOG.md` para trazabilidad de evolución del proyecto.

---
