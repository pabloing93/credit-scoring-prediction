# credit-scoring-prediction
"Credit Scoring Prediction" es un proyecto de machine learning centrado en predecir la elegibilidad de los usuarios para recibir préstamos <br>
basándose en sus métricas y datos. El objetivo principal es utilizar algoritmos de aprendizaje automático para evaluar la probabilidad de  <br>
que un usuario sea capaz de pagar un préstamo, utilizando información histórica y métricas financieras. <br>
<br>
# Configuración del ambiente
<br>

La configuración del entorno para el proyecto de machine learning es esencial para asegurar un desarrollo suave y efectivo. En este caso, se <br>
están utilizando algunas bibliotecas clave, como pandas, seaborn, matplotlib.pyplot y sklearn <br>
<br>
![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/fd8af9b8-8e03-449f-b482-2f200ef19b9e)

<br>

# Procesamiento de los Datos
## Obtención de los Datos
Los datos utilizados en este proyecto fueron obtenidos mediante la lectura de un archivo CSV denominado "german_credit.csv". <br>
Este archivo almacena un extenso historial de una base de datos perteneciente a un banco alemán que ofrece servicios de entrega de préstamos. 

El archivo "german_credit.csv" cuenta con informacion relavante como, sexo, cantidad prestada, estado civil, el plazo de pago entre otros, <br>
se uso el metodo de pandas read_csv para la lectura de los datos del archivo texto
<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/5ba4733c-70d6-4dce-b883-731240dea1cb)

<br>

## DataCleaning
Una vez obtenidos los datos y almacenados en una variable del tipo DataFrame (df_banco) se procedió a examinar los datos, lo que se buscaba era<br>
encontrar datos duplicados y nulos y retirarlos del DataFrame para trabajarlos de mejor manera, nos valimos de métodos de la librería pandas   <br>
para encontrar este grupo de datos no deseados, alguno de los métodos usados fueron  .drop(), drop_duplicates(), dropna() entre otros, una vez <br>
limpios los datos verificamos el contenido del DataFrame resultante y notamos que contamos con 1000 registros.
<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/bbee679d-5f08-42d4-924b-eec8543c0789)

<br>
