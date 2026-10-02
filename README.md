# Proyecto de Ciencia de Datos: SAML-D

**Alumno:** Nelson Odriozola  
**Tema:** análisis exploratorio de transacciones para la prevención del lavado de activos.

## Entregables

- `Entregable 1.docx`: selección y validación del dataset, contexto del problema y variables principales.
- `Entregable 2.ipynb`: ingesta, revisión inicial de los datos, diagnóstico de valores faltantes y aplicación de funciones de transformación.

## Dataset

Se utiliza el dataset sintético **SAML-D**, que contiene **9.504.852 filas y 12 columnas**. 
Los datos son ficticios: no representan operaciones de clientes reales y los resultados no deben interpretarse como detecciones de casos reales.

- [Fuente original en Kaggle](https://www.kaggle.com/datasets/berkanoztas/synthetic-transaction-monitoring-dataset-aml)
- [Archivo SAML-D.csv en Google Drive](https://drive.google.com/file/d/1uRs7ojeWVmAB0U5fgeUNBCAh4jqLl8O0/view?usp=sharing)

El CSV ocupa aproximadamente **996 MB** y no está incluido en el repositorio por su tamaño. El notebook lo descarga desde Google Drive (https://drive.google.com/file/d/1uRs7ojeWVmAB0U5fgeUNBCAh4jqLl8O0/view?usp=sharing). También se puede obtener desde la fuente original de Kaggle.

## Trabajo realizado en la preentrega 2

Se instala las bibliotecas y se descarga el CSV desde Google Drive. Se carga el dataset SAML-D y realicé una revisión inicial de su estructura: cantidad de filas y columnas, tipos de datos, estadísticos descriptivos y valores faltantes. También analicé algunas características de las variables, como el hecho de que las cuentas son identificadores y que Is_laundering contiene etiquetas binarias asignadas por el dataset sintético.

Luego creé dos transformaciones: una función que clasifica las operaciones según la ubicación bancaria y las monedas de envío y recepción, y una función lambda que agrupa los montos en categorías baja, media y alta utilizando rangos definidos para esta exploración.

Esta entrega es exploratoria: las categorías creadas ayudan a resumir los datos, pero no determinan por sí solas que una transacción sea sospechosa ni representan detecciones de casos reales.

