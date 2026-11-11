# Proyecto de Ciencia de Datos: SAML-D

**Alumno:** Nelson Odriozola  
**Tema:** análisis exploratorio de transacciones para la prevención del lavado de activos.

## Entregables

- `Entregable 1.docx`: selección y validación del dataset, contexto del problema y variables principales.
- `Entregable 2.ipynb`: ingesta, revisión inicial de los datos, diagnóstico de valores faltantes y aplicación de funciones de transformación.
- `Entregable 3.pdf`: análisis de valores atípicos en Amount, uso de memoria y tipos de datos, revisión de cuentas y aplicación de filtros.
- `Entregable 4.pdf`: análisis exploratorio visual con histogramas, gráficos de barras, boxplots y un mapa de correlación, acompañados de sus interpretaciones.

## Dataset

Se utiliza el dataset sintético **SAML-D**, que contiene **9.504.852 filas y 12 columnas**. Sus registros no representan operaciones de clientes reales, por lo que los resultados no deben interpretarse como detecciones de casos reales.

- [Fuente original en Kaggle](https://www.kaggle.com/datasets/berkanoztas/synthetic-transaction-monitoring-dataset-aml)
- [Archivo SAML-D.csv en Google Drive](https://drive.google.com/file/d/1uRs7ojeWVmAB0U5fgeUNBCAh4jqLl8O0/view?usp=sharing)

El CSV ocupa aproximadamente **996 MB** y no está incluido en el repositorio debido a su tamaño. El notebook descarga el archivo desde Google Drive.

## Trabajo realizado en la preentrega 1

Se eligió el tema de finanzas y prevención del lavado de activos. La pregunta inicial del proyecto es si se puede predecir si una transacción será etiquetada como sospechosa a partir de su monto, tipo de pago, monedas, ubicación de las entidades financieras y momento de realización.

Por tratarse de una pregunta con dos posibles etiquetas —sospechosa o no sospechosa—, el problema se plantea como uno de clasificación binaria supervisada. El objetivo es explorar si un modelo podría ayudar a priorizar transacciones para su posterior análisis, no reemplazar la revisión de especialistas.

## Trabajo realizado en la preentrega 2

En el notebook se instalan las bibliotecas necesarias y se descarga y carga el CSV. Luego se revisan las dimensiones del dataset, los tipos de datos, los estadísticos descriptivos y los valores faltantes.

También se analizan algunas características de las variables: las cuentas son identificadores y `Is_laundering` contiene etiquetas binarias asignadas por el dataset sintético.

Por último, se crean dos transformaciones: una función que clasifica las operaciones según la ubicación bancaria y las monedas de envío y recepción, y una función `lambda` que agrupa los montos en categorías baja, media y alta mediante rangos definidos para esta exploración.

Estas transformaciones son descriptivas: ayudan a resumir los datos, pero no determinan por sí solas que una transacción sea sospechosa.

➡️ [Abrir Entregable 2: Ingesta y radiografía del dataset](./Entregable%202.ipynb)

## Trabajo realizado en la preentrega 3

Se profundizó la inspección de la columna `Amount` mediante el criterio IQR para identificar y contar posibles valores atípicos. También se midió la memoria estimada por columna y se comparó luego de convertir columnas de baja cardinalidad a tipos más eficientes.

Las columnas `Date` y `Time` se convirtieron a tipos temporales; la conversión no produjo valores inválidos. Además, se analizaron la cantidad de cuentas distintas y la frecuencia con que aparecen como emisoras o receptoras.

Se aplicaron filtros booleanos para explorar operaciones internacionales de monto alto y montos por encima del límite superior del IQR. `Laundering_type` se excluyó de la vista preliminar de predictores porque podría contener información relacionada con la etiqueta `Is_laundering`.

Los posibles valores atípicos son inusuales según un criterio estadístico, pero no indican por sí solos que una transacción sea sospechosa.

➡️ [Entregable 3 (PDF)](https://github.com/odriozolanelson/Curso_CoderHouse_Data_Science_I/blob/main/Entregable%203_Odriozola_Nelson.pdf)

## Trabajo realizado en la preentrega 4

Se realizó un análisis exploratorio visual del conjunto de datos SAML-D utilizando gráficos de Seaborn y Matplotlib. Se incluyeron histogramas de Amount con el rango completo y hasta el percentil 99, un gráfico de transacciones por tipo de pago, boxplots de montos según el tipo de pago, una comparación entre tipo de pago y ubicación bancaria, y un mapa de correlación entre el monto, la ubicación y la moneda.

En los gráficos se observa una fuerte concentración de transacciones en montos bajos y una cola de valores altos. La vista hasta el percentil 99 permite apreciar mejor la distribución central, mientras que los boxplots muestran diferencias entre los montos según el tipo de pago. También se observa que las operaciones Cross-border aparecen asociadas a ubicaciones bancarias distintas. En el mapa de correlación, la asociación entre ubicación distinta y moneda distinta es de 0,91; la correlación del monto con esos indicadores es de 0,02.

Los gráficos y sus interpretaciones son descriptivos. Como SAML-D es sintético, los patrones observados no representan operaciones reales ni detecciones de lavado de activos.

➡️ [Entregable 4 (PDF)](https://github.com/odriozolanelson/Curso_CoderHouse_Data_Science_I/blob/main/Entregable%204_Odriozola_Nelson.pdf)
