# Proyecto-personal
Proyecto de Clasificación de Datos con Regresión Logística 

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
Asegúrate de tener instaladas las siguientes bibliotecas de Python:
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

## Proceso de decesición de toma de desiciones

## Recursos Adicionales
- [Dataset original](https://archive.ics.uci.edu/dataset/144/statlog+german+credit+data) utilizado en el proyecto.

     

