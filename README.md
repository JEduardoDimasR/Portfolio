# Proyecto de Clasificación de Datos con Regresión Logística 

## Descripción
Este proyecto utiliza un modelo de regresión logística en Python para clasificar a los clientes como buenos o malos en función de un conjunto de datos que contiene información sobre créditos. El objetivo
principal es predecir la capacidad de pago de los clientes y ayudar en la toma de decisiones crediticias.

## Estructura del repositorio
- `Clasificación_de_créditos.ipynb`: Jupyter Notebook que contiene el código y el análisis del modelo de regresión logística.
- `Credit.csv`: Conjunto de datos de clientes utilizado en el proyecto.
- `requirements.txt`: Archivo de requisitos que lista las dependencias necesarias para ejecutar el código.

## Instrucciones de Uso
1. Clona este repositorio en tu entorno local:

```bash
git clone https://github.com/JEduardoDimasR/Proyecto-personal.git
```
2. Abre el notebook `Clasificación_de_créditos.ipynb` para ver el código y análisis detallado del modelo.
3. Ejecuta el notebook en un entorno de Jupyter para explorar y ejecutar el código.

## Requisitos
Asegúrate de tener instaladas las siguientes librerías de Python:
- scikit-learn
- pandas
- numpy
- matplotlib
- seaborn
- statsmodels

## Descripción de los datos

| **Nombre**   | **Descripción** | **Dtype**|
| :--------: | :----:| :------: |
| **checkin_acc**     | Estado de la cuenta corriente existente  | object |
| **duration**    | Duración del crédito otorgado en meses   | int 64 |
| **credit_history**  | Historial de crédito  | object |
| **amount**  | Monto del crédito/préstamo| int 64 |
| **savings_acc**  | Saldo en cuenta de ahorro   | object |
| **present_emp_since**  | Empleo en años  | object |
| **inst_rate**  |Tasa de pago a plazos  | int 64 |
| **personal_status**  | Estado civil  | object |
| **residing_since**  | Residencia en años   | int 64 |
| **age**  | Edad en años  | int 64 |
| **inst_plans**  | Otros planes de pago a plazos del solicitante| object |
| **num_credits**  | Número de créditos existentes en este banco | int 64 |
| **job**  | Trabajo | object |
| **status**  | Estado de crédito  | int 64 |

Para una descripción detallada de las categorías del dataset ingresar a [Dataset original](https://archive.ics.uci.edu/dataset/144/statlog+german+credit+data)

## Proceso de toma de decisiones

El objetivo principal del proyecto era crear un modelo de clasificación eficiente para determinar si un cliente era considerado "bueno" (0) o "malo" (1) en función de su historial crediticio. Para lograrlo, se utilizó la codificación de variables categóricas y se construyó un modelo que consideraba todas las características de cada cliente, lo que permitió identificar las variables que tenían una influencia estadísticamente significativa en el modelo.

Posteriormente, se desarrolló un segundo modelo que ayudó a determinar cuáles características tenían un mayor impacto en la decisión de si se trataba de un buen o mal crédito. Luego, se aplicaron tres criterios de clasificación basados en la probabilidad predicha por el modelo entrenado.

Se evaluaron las tres clasificaciones realizadas con métricas, lo que permitió determinar qué técnica o técnicas fueron las más efectivas.


## Resolviendo el problema

Para abordar este problema, se utilizó uno de los algoritmos más frecuentemente empleados en el aprendizaje supervisado: la regresión logística. Este algoritmo se utilizó para modelar el conjunto de datos. La regresión logística tiene como objetivo predecir la probabilidad de que un evento pertenezca a una categoría específica. Es comúnmente utilizada en problemas de clasificación binaria, donde se busca determinar si un evento pertenece a una de dos clases posibles (por ejemplo, "sí" o "no", "bueno" o "malo", "positivo" o "negativo", etc.).

Para implementar el algoritmo, se hizo uso de la librería statsmodels, ya que tiene un desglose más detallado en función de sus medidas estadísticas.

### Mejores resultados del modelo

|      | Precision | Recall | F1-Score | Support |
|------|-----------|--------|----------|---------|
| 0    | 0.90      | 0.60   | 0.72     | 209     |
| 1    | 0.48      | 0.85   | 0.61     | 91      |
| Accuracy  |         |         | 0.68  | 300  |
| Macro Avg | 0.69    | 0.72   | 0.67     | 300    |
| Weighted Avg | 0.77  | 0.68   | 0.69     | 300     |

### Resultados del mejor Modelo de Regresión Logística

- **Modelo**: Logit
- **Método**: MLE (Estimación de Máxima Verosimilitud)
- **Variable Dependiente**: status
- **Pseudo R-squared**: 0.161
- **Fecha**: 2023-10-24 20:11
- **AIC (Criterio de Información de Akaike)**: 733.8898
- **Número de Observaciones**: 700
- **BIC (Criterio de Información Bayesiana)**: 774.8495
- **Grados de Libertad del Modelo**: 8
- **Log-Likelihood (Logaritmo de la Verosimilitud)**: -357.94
- **Grados de Libertad Residuales**: 691
- **LL-Null (Logaritmo de la Verosimilitud Nula)**: -426.75
- **Convergencia del Modelo**: 1.0000
- **Valor p de LLR (Razón de Verosimilitud)**: 7.4185e-26
- **Número de Iteraciones**: 6.0000
- **Escala**: 1.0000

### Coeficientes del Modelo

| Variable             | Coeficiente | Error Estándar | Estadística Z | Valor p  | Intervalo de Confianza (95%) |
|----------------------|:-------------:|:----------------:|:---------------:|:-----------------:|:------------------------------:|
| const                | -0.8969     | 0.4364         | -2.0551       | 0.0399          | [-1.7523, -0.0415]           |
| duration             | 0.0197      | 0.0098         | 2.0033        | 0.0451          | [0.0004, 0.0390]              |
| amount               | 0.0001      | 0.0000         | 2.3205        | 0.0203          | [0.0000, 0.0002]              |
| inst_rate            | 0.2811      | 0.0929         | 3.0264        | 0.0025          | [0.0991, 0.4632]              |
| age                  | -0.0216     | 0.0089         | -2.4207       | 0.0155          | [-0.0392, -0.0041]            |
| checkin_acc_A13      | -0.8038     | 0.4081         | -1.9697       | 0.0489          | [-1.6037, -0.0040]            |
| checkin_acc_A14      | -1.5452     | 0.2187         | -7.0649       | 0.0000          | [-1.9738, -1.1165]            |
| credit_history_A34   | -0.8781     | 0.2319         | -3.7858       | 0.0002          | [-1.3327, -0.4235]            |
| savings_acc_A65      | -0.5448     | 0.2581         | -2.1108       | 0.0348          | [-1.0507, -0.0389]            |

### Matriz de confusión del mejor resultado de clasificación del modelo

![](https://github.com/JEduardoDimasR/Proyecto-personal/blob/main/Matriz%201.png)

## Resultados

El modelo final logró un AUC de 0.72, lo cual indica su precisión. Un valor de AUC superior a 0.7 se considera generalmente aceptable.

El rendimiento del modelo se evaluó utilizando varias métricas. Para la clase 0 (clientes buenos), la precisión es del 90%, lo que significa que el 90% de las predicciones de clientes buenos son correctas. Para la clase 1 (clientes malos), la precisión es del 48%, lo que significa que el 48% de las predicciones de clientes malos son correctas. En cuanto al recall, para la clase 0, es del 60%, lo que significa que el modelo identificó correctamente el 60% de todos los clientes buenos. Para la clase 1, el recall es del 85%, lo que significa que el modelo identificó correctamente el 85% de todos los clientes malos. El puntaje F1 para la clase 0 es 0.72, lo que es una medida equilibrada de precisión y recall. Para la clase 1, el puntaje F1 es 0.61. La exactitud general del modelo es del 68%, lo que significa que el 68% de las predicciones son correctas en general.

En cuanto a los coeficientes del modelo, se pueden obtener las siguientes conclusiones:

1. La probabilidad de tener mal crédito aumenta a medida que se incrementa la duración, el monto y la tasa de instalación. Por ejemplo, un cambio de una unidad en la duración resulta en un cambio de 0.0197 unidades en la probabilidad.

2. La probabilidad de tener mal crédito disminuye a medida que aumenta la edad. Esto implica que las personas mayores tienden a pagar sus créditos a tiempo en comparación con las personas más jóvenes.

## Resumen

En este proyecto, se abordó el objetivo de crear un modelo de clasificación eficiente para determinar si un cliente era "bueno" o "malo" según su historial crediticio. El proceso se dividió en varias etapas, comenzando con la codificación de variables categóricas y la construcción de un modelo que considerara todas las características de cada cliente. Posteriormente, se desarrolló un segundo modelo para identificar las características más influyentes en la decisión de crédito y se aplicaron tres criterios de clasificación basados en la probabilidad predicha.

El rendimiento del modelo se evaluó utilizando métricas, revelando que el modelo final tuvo un AUC de 0.72, que se considera aceptable. Se analizaron métricas específicas para las clases de clientes "buenos" y "malos". La precisión fue del 90% para la clase de "clientes buenos" y del 48% para "clientes malos". El recall para "clientes buenos" fue del 60%, mientras que para "clientes malos" fue del 85%. Los puntajes F1 se situaron en 0.72 y 0.61 respectivamente. La exactitud general del modelo fue del 68%.

## Conclusiones:

1. El modelo logró un AUC de 0.72, indicando que es un modelo preciso, ya que supera el umbral de 0.7, que se considera aceptable.

2. Para los "clientes buenos", el modelo demostró una alta precisión del 90%, lo que significa que es efectivo en predecir cuándo un cliente es bueno.

3. Aunque la precisión para los "clientes malos" fue del 48%, el alto recall del 85% indica que el modelo es bueno para identificar a los "clientes malos" cuando realmente lo son.

4. Los coeficientes del modelo revelaron que la duración, el monto y la tasa de instalación aumentan la probabilidad de tener un mal crédito, mientras que la edad disminuye esta probabilidad. Las personas mayores tienden a pagar sus créditos a tiempo en comparación con las personas más jóvenes.

En resumen, el modelo demostró ser eficaz en la clasificación de clientes como "buenos" o "malos" basándose en su historial crediticio, con un AUC sólido y métricas que respaldan su desempeño. Los coeficientes del modelo proporcionan información adicional sobre cómo influyen las características específicas en la decisión de crédito.


## Recursos Adicionales
- [Dataset original](https://archive.ics.uci.edu/dataset/144/statlog+german+credit+data) utilizado en el proyecto.

     

