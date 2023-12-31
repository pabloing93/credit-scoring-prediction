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
Una vez obtenidos los datos y almacenados en una variable del tipo DataFrame (df_banco) se procedió a examinar los datos, lo que se buscaba <br>
era encontrar datos duplicados y nulos y retirarlos del DataFrame para trabajarlos de mejor manera, nos valimos de métodos de la librería   <br>
pandas para encontrar este grupo de datos no deseados, alguno de los métodos usados fueron  .drop(), drop_duplicates(), dropna() entre otros,<br>
una vez limpios los datos verificamos el contenido del DataFrame resultante y notamos que contamos con 1000 registros.
<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/bbee679d-5f08-42d4-924b-eec8543c0789)

<br>

# Exploración de Datos
## EDA
Al analizar el DataFrame obtenido después de la limpieza de los datos (df_banco) se procedió a realizar algunos cambios en sus campos, para <br>
decidir dichos cambios se accedió a "german_dataset-dictionary.txt" el cual es un documento de texto que contiene categorizado los campos <br>
del dataset de la base de datos (german_credit.csv) con este documento de apoyo y a partir de personal_status_sex se crearon dos campos más<br>
los cuales fueron sexo y estado_civil, a partir de age se creó el rango_edad, a partir de duration_in_month se creó rango_plazos_creditos y a<br>
partir de credit_amount se creó rango_valor_credito, una vez hechos estos cambios se borraron los campos que fueron base para crear nuevos <br>
campos,todo esto se realizó a partir de la función feature_engineering.

<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/4d7f896f-52b5-4a7a-b8b8-bf45c9cf525d)

<br>





