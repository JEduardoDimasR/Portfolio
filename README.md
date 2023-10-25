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

| **Nombre**   | **Descripción** | **Categorías** | 
| :--------: | :----:| :----------: |
| **checkin_acc**     | Estado de la cuenta corriente existente  | * A11: ... < 0 DM

* A12: 0 <= ... < 200 DM
* A13 : ... >= 200 MD / asignaciones salariales durante al menos 1 año
* A14: sin cuenta corriente |
| **duration**    | Duración del crédito otorgado en meses   | 
| **credit_history**  | Historial de crédito  |
| **amount**  | Monto del crédito/préstamo|
| **savings_acc**  | Saldo en cuenta de ahorro   |
| **present_emp_since**  | Empleo en años  |
| **inst_rate**  |Tasa de pago a plazos  |
| **personal_status**  | Estado civil  |
| **residing_since**  | Residencia en años   |
| **age**  | Edad en años  |
| **inst_plans**  | Otros planes de pago a plazos del solicitante|
| **num_credits**  | Número de créditos existentes en este banco |
| **job**  | Trabajo |
| **status**  | Estado de crédito  |




## Recursos Adicionales
- [Dataset original](https://archive.ics.uci.edu/dataset/144/statlog+german+credit+data) utilizado en el proyecto.

     

