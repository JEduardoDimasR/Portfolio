# Pronóstico de transacciones en una cadena de tiendas minoristas

## Descripción
Este proyecto se enfoca en una cadena minorista con múltiples ubicaciones, buscando implementar modelos predictivos para estimar el volumen de transacciones en cada sucursal. Durante un cuatrimestre, se han recopilado datos detallados de las transacciones diarias en cada ubicación. El objetivo principal es proporcionar a la cadena de tiendas minoristas una herramienta de pronóstico robusta y confiable, ofreciendo predicciones precisas que respalden la toma de decisiones estratégicas y la optimización operativa en sus sucursales.

## Estructura del repositorio
- `Pronóstico_de_transacciones_en_una_cadena_de_tiendas_minoristas.ipynb`: Jupyter Notebook que contiene el código y el análisis del modelo.
- `Store.xls`: Conjunto de datos de transacciones diarías utilizado en el proyecto.
- `requirements.txt`: Archivo de requisitos que lista las dependencias necesarias para ejecutar el código. 

## Requisitos
Asegúrate de tener instaladas las siguientes librerías de Python:
- Scikit-learn
- Pandas
- Numpy
- Matplotlib
- Statsmodels
- Keras
- TensorFlow

## Descripción de los datos

| **Nombre**   | **Descripción** | **Dtype**|
| :--------: | :----:| :------: |
| **Date**     | Fechas diarias  | datetime64[ns] |
| **Transactions**    | Transacciones de la cadena de tiendas minoristas   | int 64 |

**Análisis de Pronóstico de Transacciones: Modelos y Evaluación **

El principal objetivo del proyecto fue crear un modelo de pronóstico eficiente para predecir el número de transacciones del próximo mes basándose en su historial. Para lograrlo, se visualizaron todas las componentes de la serie temporal correspondientes a las transacciones de la cadena minorista, lo que permitió identificar su comportamiento y el tipo de modelo estadístico a utilizar.

Posteriormente, se procedió al cálculo de las autocorrelaciones para los rezagos de la serie temporal, lo que ayudó a determinar si la serie era estacionaria o no. Luego, se creó un modelo y se evaluó su precisión mediante una métrica para medir el desempeño del modelo.

Finalmente, se desarrolló un segundo modelo más robusto para establecer un pronóstico más confiable y preciso, con el que se evaluó su precisión.
