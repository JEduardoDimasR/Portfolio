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

## Análisis de Pronóstico de Transacciones: Modelos y Evaluación 

El principal objetivo del proyecto fue crear un modelo de pronóstico eficiente para predecir el número de transacciones del próximo mes basándose en su historial. Para lograrlo, se visualizaron todas las componentes de la serie temporal correspondientes a las transacciones de la cadena minorista, lo que permitió identificar su comportamiento y el tipo de modelo estadístico a utilizar.

Posteriormente, se procedió al cálculo de las autocorrelaciones para los rezagos de la serie temporal, lo que ayudó a determinar si la serie era estacionaria o no. Luego, se creó un modelo y se evaluó su precisión mediante una métrica para medir el desempeño del modelo.

Finalmente, se desarrolló un segundo modelo más robusto para establecer un pronóstico más confiable y preciso, con el que se evaluó su precisión.

## Resolución del problema

Para resolver este problema, se emplearon dos enfoques distintos: el modelo estadístico clásico para series temporales, ARIMA, y un modelo de aprendizaje profundo, las Redes Neuronales Recurrentes (RNN). ARIMA se enfoca en pronosticar valores futuros basados en patrones históricos, combinando componentes autoregresivos, de media móvil y de diferenciación para modelar tendencias, estacionalidades y ciclos.
Por otro lado, las RNN tienen como objetivo capturar complejas dependencias temporales en secuencias de datos, donde la información previa es crucial para predecir el siguiente paso en la secuencia. 
La implementación de estos algoritmos se realizó mediante la utilización de la librería 'statsmodels' para ARIMA y el framework 'Keras' para las RNN.

## SARIMAX Results

|                          |                     |
|--------------------------|---------------------|
| **Dep. Variable**        | Transactions        |
| **No. Observations**     | 103                 |
| **Model**                | ARIMA(1, 1, 1)      |
| **Log Likelihood**       | -265.961            |
| **Date**                 | Thu, 28 Dec 2023    |
| **AIC**                  | 537.922             |
| **Time**                 | 02:32:05            |
| **BIC**                  | 545.797             |
| **Sample**               | 10-01-2014          |
|                          | - 01-11-2015        |
| **Covariance Type**      | opg                 |
|--------------------------|---------------------|
|                          |                     |
| **coef**                 | std err             |
|--------------------------|---------------------|
| ar.L1                    | 0.4975              |
| ma.L1                    | -0.7803             |
| sigma2                   | 10.7476             |
|--------------------------|---------------------|
|                          |                     |
| **Ljung-Box (L1) (Q)**   | 0.05                |
| **Prob(Q)**              | 0.82                |
| **Jarque-Bera (JB)**     | 65.16               |
| **Prob(JB)**             | 0.00                |
| **Heteroskedasticity (H)**| 0.91               |
| **Skew**                 | -0.76               |
| **Prob(H) (two-sided)**  | 0.78                |
| **Kurtosis**             | 6.61                |


