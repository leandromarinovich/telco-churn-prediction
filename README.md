# 📡 Predicción de Churn en Telecomunicaciones

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/Library-Scikit--Learn-orange)
![Status](https://img.shields.io/badge/Status-Listo--para--Producción-green)

## 📖 Resumen Ejecutivo

En la industria de las telecomunicaciones, retener clientes es crítico. Este proyecto no solo construye un modelo de machine learning, sino que desarrolla una **estrategia de retención** basada en datos.

En lugar de buscar una "alta exactitud" genérica, esta solución está optimizada para **Recall (Sensibilidad)**. ¿Por qué? Porque desde una perspectiva de negocio, el costo de no detectar a un cliente que se va (Falso Negativo) es significativamente mayor que el costo de ofrecer un incentivo a un cliente leal (Falso Positivo).

## 🚀 Características Principales

*   **Pipeline Listo para Producción**: Encapsulación completa de los pasos de preprocesamiento (OneHotEncoding, Escalado) usando Pipelines de Scikit-Learn para prevenir data leakage y asegurar reproducibilidad.
*   **Validación Rigurosa**: División de datos en **Train (70%)**, **Validación (15%)** y **Test (15%)** con estratificación, simulando condiciones reales de despliegue.
*   **Feature Engineering Orientado a Negocio**: Creación de variables de alto valor como `HighRisk_Combo` (Fibra Óptica + Mes-a-Mes) y `TotalServices`.
*   **Insights Accionables**: Traducción de los resultados del modelo en acciones concretas de retención.

## 🛠️ Stack Tecnológico

*   **EDA**: Pandas, Seaborn, Matplotlib
*   **Preprocesamiento**: Scikit-Learn (ColumnTransformer, StandardScaler, OneHotEncoder)
*   **Modelado**: Random Forest Classifier (optimizado para desbalance de clases)
*   **Evaluación**: Recall, Curva Precision-Recall, Matriz de Confusión

## 📊 Resultados

El modelo de Random Forest fue seleccionado sobre Regresión Logística por su capacidad superior para capturar relaciones no lineales.

| Métrica | Score (Set de Prueba) | Implicación de Negocio |
| :--- | :--- | :--- |
| **Recall** | **~71%** | Detectamos 7 de cada 10 clientes en riesgo de irse. |
| **Accuracy** | ~77% | Rendimiento general robusto sin sobreajuste. |

## 💡 Propuesta de Estrategia de Retención

Basado en el análisis de importancia de variables del modelo, se propone el siguiente plan de intervención segmentado:

| Segmento | Perfil de Riesgo | Acción Recomendada |
| :--- | :--- | :--- |
| **🚨 Crítico** | Prob Alta (>70%) | **Oferta Agresiva**: 2 meses gratis al cambiar a contrato de 1 año. Objetivo: Romper la combinación de "Alto Riesgo". |
| **⚠️ En Riesgo** | Prob Media (40-70%) | **Generación de Valor**: Cross-sell de Streaming/Seguridad al 50% de descuento para aumentar adherencia (`TotalServices`). |
| **✅ Seguro** | Prob Baja (<40%) | **Retención Pasiva**: Mantener calidad de servicio. Evitar descuentos innecesarios. |

## 📂 Estructura del Proyecto

```
├── data/                        # Dataset de telecomunicaciones
├── prediccion_churn_telco.ipynb # Notebook principal con análisis y modelado
├── modelo_churn_rf_final.pkl    # Modelo serializado para deployment
├── README.md                    # Documentación del proyecto
└── requirements.txt             # Dependencias de Python
```

## 🔧 Cómo Ejecutar

1.  Clonar el repositorio:
    ```bash
    git clone https://github.com/leandromarinovich/proyecto-churn-telco.git
    ```
2.  Instalar dependencias:
    ```bash
    pip install -r requirements.txt
    ```
3.  Ejecutar el notebook:
    ```bash
    jupyter notebook prediccion_churn_telco.ipynb
    ```

## 🤝 Contribuciones

Comentarios y sugerencias son bienvenidos. Por favor, abrí un issue o enviá un pull request.

## 👤 Autor

**Leandro Marinovich**
- GitHub: [@leandromarinovich](https://github.com/leandromarinovich)
- LinkedIn: [Leandro Marinovich](https://linkedin.com/in/leandromarinovich)

---
*Proyecto desarrollado con foco en buenas prácticas de data science y ROI de negocio.*
