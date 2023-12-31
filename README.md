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

## Data Analyst and Visualization
Una vez hechos los cambios en el DataFrame (df_banco) se graficaron los campos obtenidos junto a la variable a predecir, para esto hicimos <br>
uso de una función llamada analisis_exploratorio, la cual se encarga de graficar estas variables

<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/668713bf-ec30-4e6a-8b5a-48378db69178)

<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/4929b68f-1c0b-4706-90ab-c13f37a7c97e)

<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/cf005d92-30ff-41b1-a052-b28f840adbc8)

<br>

Al notar que las gráficas de histograma de rango_plazos_credito y rango_edad tienen una sexta columna con muy pocos datos, se tomó la <br>
decisión de unir el espectro de datos de las últimas columnas con la penúltima para así reducir ese espectro de datos a 5 columnas, <br>
ya que esas últimas columna (la sexta columna en ambos histogramas) tenían muy pocos datos

<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/32cee3d2-e5b6-433d-8077-81e8b5e5370e)


![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/e8249962-3c51-41ad-bff1-d1c6887abead)

<br>

Luego del análisis de unir esos espectros de datos y gracias a la función analisis_exploratorio vimos la Matrix de correlación, la cual al <br>
analizarla notamos que las variables que se pueden explicar mejor la una ala otra son sexo con estado_civil y además de esas <br>
rango_plazos_credito con rango_valor_credito

<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/b3323c2a-b8d4-4af2-8a44-e2f7fec31745)

<br>

Se tomó la decisión de eliminar los campos de sexo y rango_valor_credito, esto se hizo de esta forma pues en el caso de sexo, tiene una <br>
correlación más alta con otras variables que estado_civil, del mismo modo al observar la Matrix de correlación pasa exactamente lo mismo con<br>
rango_valor_credito y rango_plazos_credito, rango_valor_credito tiene mucha más correlación con otras variables.

<br>

Del mismo modo usamos la matrix de correlación para buscar las variables con indice de correlación despreciables para el análisis de los <br>
datos, una vez hecho este procedimiento decidimos borrar low_corr_columns pues esta no tenia mucha relavancia para el análisis

<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/239b03e5-9f51-48f4-a9d7-acb5222ba6fe)

<br>






