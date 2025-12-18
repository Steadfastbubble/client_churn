# Predicción de Churn: Estrategia de Retención para Interconnect

![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-232F3E?style=for-the-badge&logo=databricks&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)

## Objetivo del Proyecto

El operador de telecomunicaciones **Interconnect** busca evolucionar hacia un modelo de negocio basado en datos. El objetivo de este proyecto es desarrollar un modelo de Machine Learning de clasificación para **pronosticar la tasa de cancelación (churn)**. 

Al identificar proactivamente a los usuarios con mayor probabilidad de abandonar el servicio, la empresa puede implementar estrategias de retención personalizadas, como códigos promocionales y planes exclusivos, optimizando así el Customer Lifetime Value (CLV).

## Contexto de Negocio

Interconnect ofrece una infraestructura robusta de servicios digitales que incluye:

* **Conectividad:** Telefonía fija multilínea e Internet (DSL y Fibra Óptica).
* **Servicios de Valor Agregado:** Seguridad en línea, antivirus, soporte técnico y almacenamiento en la nube.
* **Entretenimiento:** Streaming de TV y catálogos de películas.

El modelo analiza cómo las preferencias del cliente, el tipo de contrato (mensual, anual o bianual) y los métodos de facturación electrónica impactan en la fidelidad a largo plazo.

## Tecnologías y Metodología

Para este proyecto, se implementó un pipeline de Data Science completo:

1.  **Ingeniería de Características:** Consolidación de datos de múltiples fuentes y creación de nuevas variables para capturar patrones de comportamiento.
2.  **Análisis Exploratorio (EDA):** Visualización de tendencias temporales y correlaciones entre servicios contratados y deserción.
3.  **Modelado Predictivo:** Evaluación y ajuste de hiperparámetros de diversos algoritmos:
    * Regresión Logística
    * Random Forest
    * **XGBoost / LightGBM** (Modelos de alto rendimiento)
4.  **Métricas de Evaluación:** Enfoque principal en **AUC-ROC (0.88)** y Accuracy para garantizar un equilibrio entre precisión y sensibilidad.

## 📂 Descripción de los Datos

El análisis se basa en cuatro fuentes de datos principales vinculadas por el `customerID`:

* `contract.csv`: Información sobre el tipo de contrato, fechas de inicio/fin, métodos de pago y cargos mensuales.
* `personal.csv`: Datos demográficos del cliente (género, estado civil, dependencia).
* `internet.csv`: Detalles sobre los servicios de red y seguridad adicionales.
* `phone.csv`: Información sobre el uso de líneas telefónicas múltiples.

*Nota: La información del contrato es válida a partir del 1 de febrero de 2020.*

## 🚀 Logros del Proyecto

* **Precisión de Predicción:** Se alcanzó un **AUC-ROC de 0.88**, superando los umbrales de éxito establecidos.
* **Insights Críticos:** Identificación de variables clave como el tipo de conexión (Fibra Óptica) y el método de pago como principales predictores del churn.
* **Estrategia:** Generación de una base sólida para que el equipo de marketing tome decisiones basadas en evidencia.

---

### 👤 Contacto
Si tienes interés en discutir este modelo o explorar colaboraciones en Data Science y Logística Analítica, ¡conectemos!

* **LinkedIn:** [https://www.linkedin.com/in/fernando-garza-trevino/]
* **Email:** ferngarzau@gmail.com
