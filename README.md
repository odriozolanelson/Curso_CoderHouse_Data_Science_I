# Análisis inicial del dataset SAML-D

## Descripción del proyecto

Este proyecto explora transacciones financieras ficticias relacionadas con el monitoreo y la prevención del lavado de activos. El objetivo general es analizar las características de las operaciones y, en etapas posteriores, estudiar si pueden utilizarse para priorizar transacciones marcadas como sospechosas por el dataset.

Los datos son ficticios: no representan operaciones de clientes reales y los resultados no deben interpretarse como detecciones de casos reales.

## Entregables

- `Entregable 1.docx`: selección y validación del dataset, contexto del problema y variables principales.
- `Entregable 2.ipynb`: ingesta de datos, revisión de dimensiones y tipos, diagnóstico de valores faltantes y funciones de transformación.

## Dataset

- Fuente original: [Synthetic transaction monitoring dataset for AML (SAML-D) en Kaggle](https://www.kaggle.com/datasets/berkanoztas/synthetic-transaction-monitoring-dataset-aml)
- Archivo utilizado: `SAML-D.csv`
- Tamaño revisado: 9.504.852 filas y 12 columnas.
- El CSV ocupa aproximadamente 996 MB y no se incluye en este repositorio.

Para reproducir el notebook, el CSV se descarga desde [este enlace de Google Drive](https://drive.google.com/file/d/1uRs7ojeWVmAB0U5fgeUNBCAh4jqLl8O0/view?usp=sharing). También se puede obtener desde la fuente original de Kaggle.

## Requisitos y ejecución

El notebook utiliza Python, JupyterLab, `pandas` y `gdown`. La primera celda instala las bibliotecas y otra celda descarga el CSV desde Google Drive. Se necesita conexión a Internet, espacio libre suficiente para el archivo y memoria disponible para procesar el dataset completo.

Abrir `Entregable 2.ipynb` en JupyterLab y ejecutar las celdas en orden, desde el comienzo. El procesamiento de millones de filas puede demorar.

## Alcance de las transformaciones

El notebook agrega una clasificación descriptiva del corredor según la ubicación bancaria y las monedas de envío y recepción. También crea categorías de monto mediante rangos definidos para esta exploración. Estas reglas sirven para describir y explorar los datos; no determinan por sí solas que una transacción sea ilícita.
