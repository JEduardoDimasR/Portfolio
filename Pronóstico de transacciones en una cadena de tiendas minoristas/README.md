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

## Resultados 

### ARIMA

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


**El modelo de predicción para el modelo ARIMA(1,1,1) obtuvo un margen de error del 22.70%**

### RNN

- Durante el entrenamiento (Epochs 96-100), la pérdida o error de entrenamiento osciló entre aproximadamente 0.3842 y 0.3926, lo que indica cómo el modelo se desempeñó durante las iteraciones finales de ajuste con los datos de entrenamiento.

- Después de entrenar el modelo, se evaluó con datos de entrenamiento y prueba independientes. El error cuadrático medio (RMSE) del conjunto de entrenamiento fue de aproximadamente 3.22, mientras que para el conjunto de prueba fue de aproximadamente 4.68. Esto indica cómo se comportó el modelo al hacer predicciones con datos que no había visto durante el entrenamiento.

![](https://github.com/JEduardoDimasR/Portfolio/blob/main/Pron%C3%B3stico%20de%20transacciones%20en%20una%20cadena%20de%20tiendas%20minoristas/SERIE%20RNN.png)

## Resumen

Se realizaron dos enfoques para predecir las transacciones en una cadena minorista. En un análisis de series temporales, se exploraron 115 observaciones, se verificó la estacionariedad y se ajustó un modelo ARIMA (1,1,1). Este modelo obtuvo un error porcentual medio del 22.70%, brindando un entendimiento del comportamiento de las transacciones y ofreciendo una forma de predecir su tendencia. 
Además, se empleó una red neuronal recurrente del tipo GRU para modelar datos secuenciales, logrando errores de entrenamiento y prueba de 3.22 y 4.68, respectivamente. Estos resultados indican que ambos enfoques proporcionaron modelos aceptables para predecir las transacciones, con la red neuronal recurrente mostrando una tendencia a generalizar bien a nuevos datos.


## Conclusiones

1. Enfoques de Modelado: Se emplearon dos enfoques distintos, ARIMA y RNN (específicamente GRU), para predecir las transacciones en la cadena de tiendas minoristas. ARIMA ofreció un error porcentual medio del 22.70%, proporcionando una comprensión del comportamiento de las transacciones y tendencias. Mientras tanto, la red neuronal recurrente GRU demostró resultados más precisos con errores de entrenamiento y prueba de 3.22 y 4.68, respectivamente.

2. Precisión del Modelo: La RNN (GRU) mostró una tendencia a generalizar mejor a nuevos datos, reflejada en su capacidad para predecir las transacciones con un error de prueba relativamente bajo en comparación con ARIMA. Esto sugiere que las RNN podrían ser más adecuadas para capturar las complejas dependencias temporales en datos secuenciales como las transacciones minoristas.

3. Uso Estratégico: Ambos modelos ofrecen herramientas valiosas para la cadena minorista. ARIMA proporciona una comprensión general y una tendencia de las transacciones, mientras que la RNN (GRU) podría ser más útil para predicciones más precisas y adaptadas a nuevas circunstancias.

4. Toma de Decisiones: Estos modelos pueden ser vitales para la toma de decisiones estratégicas y la optimización operativa en sucursales minoristas. ARIMA ofrece una visión general del comportamiento histórico, mientras que la RNN (GRU) brinda una herramienta más precisa para anticipar y responder a cambios en las transacciones futuras.

5. Generalización y Adaptabilidad: La capacidad de la RNN para generalizar a nuevos datos señala su adaptabilidad a patrones cambiantes, lo que la convierte en una opción prometedora para pronósticos continuos y adaptativos en entornos comerciales dinámicos.

Estas conclusiones destacan las fortalezas de cada modelo y su aplicabilidad potencial para respaldar decisiones estratégicas y operativas en el contexto de la cadena minorista.


