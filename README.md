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


## Algunas preguntas y desafíos que enfrenté
**¿Qué pasos del plan se realizaron y qué pasos se omitieron (explica por qué)?**
Limpieza: Primero me dedique a la limpieza de los datos esto incluye cambiar los tipos de datos de las columnas a los correctos y eliminar posibles columnas que no son necesarias para el entrenamiento del mismo. De igual manera uni de una manera optima todos los dataframes en uno mismo utilizando el customerID() como indice para luego ya que este todo junto, eliminar dicha columna.  

Exploracion extra: Despues de tener los tipos de datos corregidos, pude hacer un analisis mas extenso y profundo basado en las fechas, valores objetivo y observacion del dataframe general ya junto y limpio, esto incluye analisis de abandonos por fechas, churn rate, graficas que muestran las fechas imoprtantes de abandono y observacion de variables ausentes.

Preparacion del modelo: Utilizamos 4 distintos modelos para explorar la mejora de rendimientos y cual es el tipo de opcion a tomar correcto. En este paso hicimos varias pruebas para determinar el funcionamiento mas optimo de los modelos y como ir mejorandolos.

Resultados: Los resultados mostraron con claridad cual es el modelo con mejor rendimiento y mis recomendaciones a futuro y el mejoramiento de modelos futuros.

Al principio tuve problemas al unir los datos usando el parametro "inner", esto no causó tanto problema por que logré identificar rapido el problema y lo solucione al cambiar al tipo de unión a "outer" que es el correcto para no perder los datos importantes pero ausentes. Otra dificultad que encontré fué al momento de crear los modelos, inicialmente daban un rendimiento muy bajo, es decir, la curva AUC-ROC no daba los resultados esperados ya que no subia de 0.82 de precisión. La solucion que implemente para esto fué experimentar con los parámetros iniciales de cada modelo para luego decidir añadir mejores columnas mediante la práctica de ingenieria de caracterisiticas y asi de tal manera ayudar a los modelos a centrarse en una linea mas coherente a la hora de producir resultados y nuevas predicciones.

**Pasos Clave**
En mi opinión lo que ayudó a que los modelos funcionaran muy bien y mejorarán su rendimiento fué definitivamente transformar correctamente los datos mediante técnicas como OHE, transformacion de columnas binarias, escalacion estandar (para no afectar los datos de entrenamiento y pulir los sesgos del modelo) y la mas importante, creación de columnas extras que ayudaron exponencialmente a los modelos a identificar de una manera mas eficaz todas las clases a predecir.

**¿Cuál es tu modelo final y qué nivel de calidad tiene?**
Al final fueron 4 modelos: Regresión logística LightGBM Bosque clasificatorio Arbol de decision, el mejor siendo la simple regresion logistica con AUC-ROC de 0.9308 en la prueba y exactitud de 0.8883.
