# Telecom X — Predicción de Cancelación de Clientes (Churn)

## Descripción del Proyecto

La cancelación de clientes (churn) representa uno de los principales desafíos para las empresas de telecomunicaciones. Identificar clientes con alta probabilidad de cancelar permite implementar estrategias de retención y mejorar la estabilidad del negocio.

Este proyecto desarrolla un modelo de Machine Learning capaz de predecir la probabilidad de cancelación de clientes utilizando información demográfica, servicios contratados y datos de facturación.

El análisis fue realizado como parte del Challenge Telecom X del programa Oracle Next Education (ONE).

## Objetivo

- Construir un modelo predictivo que permita identificar clientes con mayor riesgo de cancelar el servicio, utilizando técnicas de preprocesamiento de datos, ingeniería de variables y algoritmos de clasificación

## Estructura del Proyecto

telecomx-churn-prediction
│
├── data
│   └── datos_tratados.csv
│
├── notebooks
│   └── telecomX_churn_analysis.ipynb
│
├── images
│   ├── churn_distribution.png
│   ├── confusion_matrix.png
│   └── feature_importance.png
│
└── README.md

## Dataset
El dataset contiene información sobre clientes de una empresa de telecomunicaciones, incluyendo:

características demográficas

servicios contratados

tipo de contrato

cargos mensuales y totales

comportamiento de cancelación (Churn)

Cantidad de registros analizados: 7267 clientes

## Preparación de Datos

Se realizaron los siguientes pasos de limpieza y transformación:

### Expansión de columnas estructuradas

El dataset contenía columnas con datos en formato diccionario que fueron normalizadas utilizando:

pd.json_normalize()
Eliminación de variables irrelevantes

Se eliminó el identificador único del cliente:

customerID

ya que no aporta valor predictivo al modelo.

### Tratamiento de valores nulos

eliminación de registros sin información de churn

conversión de variables numéricas

### Codificación de variables categóricas

Se aplicó One-Hot Encoding utilizando:

pd.get_dummies()

para convertir variables categóricas a formato numérico.

## Modelos Utilizados

### 1. Logistic Regression

Modelo base utilizado para establecer una línea de referencia en el desempeño predictivo.

### 2. Random Forest

Modelo basado en árboles de decisión que permite capturar relaciones no lineales y mejorar la capacidad predictiva.

## Resultados

### Logistic Regression

Accuracy aproximado:

80%

El modelo logró una buena capacidad general de clasificación, aunque presentó limitaciones para detectar algunos casos de churn.

### Random Forest

El modelo Random Forest mostró un mejor desempeño general, especialmente en la identificación de clientes con mayor probabilidad de cancelación.

## Visualizaciones

### Distribución de clientes churn

El análisis muestra un ligero desbalance de clases, con una mayor proporción de clientes activos frente a clientes que cancelan.

### Matriz de Confusión

La matriz de confusión permite evaluar la capacidad del modelo para identificar correctamente clientes que cancelarán el servicio.

### Importancia de Variables

El modelo Random Forest permite identificar las variables más influyentes en la predicción de churn.

Entre los factores más relevantes destacan:

- tipo de contrato

- cargos mensuales

- tiempo de permanencia del cliente

- servicios adicionales contratados

## Insights del Análisis

Los resultados sugieren que la cancelación de clientes está asociada principalmente a:

- contratos mensuales, que presentan mayor riesgo de churn

- clientes con menor antigüedad

- cargos mensuales elevados

- menor contratación de servicios adicionales

Estos insights pueden ayudar a la empresa a diseñar estrategias de retención más efectivas.

## Tecnologías Utilizadas

- Python

- Pandas

- NumPy

- Scikit-learn

- Matplotlib

- Seaborn

## Autor
###Verónica Apolaya
Proyecto desarrollado como parte del programa Oracle Next Education — Data Science Track.
