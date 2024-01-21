<h1>Credit Scoring Prediction</h1>

<h2>Cómo leer este proyecto 📝</h2>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/32267303/294c6665-7037-49d3-864f-9897f475cb79)

<h2>Presentación corporativa</h2>

<a href="https://www.linkedin.com/posts/pabloing_machine-learning-credit-scoring-activity-7154233394342592512-Alj6/">Link a la publicación de Linkedin</a>


<h2>Tecnologías utilizadas </h2>

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white) ![Matplotlib](https://img.shields.io/badge/Matplotlib-blue.svg?style=for-the-badge&logo=Matplotlib&logoColor=white) ![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)


<h2>Escenario 📝</h2>
"Credit Scoring Prediction" es un proyecto de machine learning centrado en predecir la elegibilidad de los usuarios para recibir préstamos <br>
basándose en sus métricas y datos. El objetivo principal es utilizar algoritmos de aprendizaje automático para evaluar la probabilidad de  <br>
que un usuario sea capaz de pagar un préstamo, utilizando información histórica y métricas financieras.<br>

<h2>1. Limpieza</h2>

<h3>1.2. Procesamiento de los Datos</h3>
Los datos utilizados en este proyecto fueron obtenidos mediante la lectura de un archivo CSV denominado "german_credit.csv". <br>
Este archivo almacena un extenso historial de una base de datos perteneciente a un banco alemán que ofrece servicios de entrega de préstamos.
Una vez obtenidos los datos y almacenados en una variable del tipo DataFrame (df_banco) se procedió a examinar los datos, lo que se buscaba
era encontrar datos duplicados y nulos y retirarlos del DataFrame para trabajarlos de mejor manera, nos valimos de métodos de la librería
pandas para encontrar este grupo de datos no deseados, alguno de los métodos usados fueron .drop(), drop_duplicates(), dropna() entre otros.

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/5ba4733c-70d6-4dce-b883-731240dea1cb)

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/bbee679d-5f08-42d4-924b-eec8543c0789)



<h3>1.3. EDA: Análisis exploratorio de los datos</h3>

Al analizar el DataFrame obtenido después de la limpieza de los datos (df_banco) se procedió a realizar algunos cambios en sus campos, para <br>
decidir dichos cambios se accedió a "german_dataset-dictionary.txt" el cual es un documento de texto que contiene categorizado los campos <br>
del dataset de la base de datos (german_credit.csv) con este documento de apoyo y a partir de personal_status_sex se crearon dos campos más<br>
los cuales fueron sexo y estado_civil, a partir de age se creó el rango_edad, a partir de duration_in_month se creó rango_plazos_creditos y a<br>
partir de credit_amount se creó rango_valor_credito, una vez hechos estos cambios se borraron los campos que fueron base para crear nuevos <br>
campos,todo esto se realizó a partir de la función feature_engineering.


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

Una vez teniendo todas las gráficas se realizó el análisis de balanceo de datos pues esto nos ayudara en los siguientes procesos, para esto<br>
se usó el algoritmo de SMOTE de la librería de imblearn con la cual nos ayudara para crear más datos virtuales para un correcto<br>
entrenamiento en los modelos a aplicar en los siguientes pasos

<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/f59b30f7-9ba6-4fd4-9677-de552ef3164c)

<br>

Al utilizar la librería vemos los cambios en los datos

<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/32267303/f1ac8d80-3b15-487f-b453-a41755adc462)


<h2>2. Modelos</h2>
<h3>2.2. Implementación de los modelos</h3>
Una vez tenemos los datos balanceados procederemos a la creación y optimización de los diferentes modelos de Machine Learning. <br>
Para esto usaremos las librerías de Numpy, matplotlib.pyplot y SkLearn las cuales de esta última dependiendo del modelo así será la importación<br>
de la instancia de esta librería, en el siguiente ejemplo lo tenemos para el modelo de Naive Bayes con el algoritmo de BernulliNB

<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/dd995c48-4727-48b6-add3-904435c1cce2)

<br>

Los datos fueron separados en "y" para la variable a calcular y "x" para todas las demas variables dependientes. <br>
Se normalizaron los datos y a partir de esta normalización y el algoritmo de train_test_split se obtuvieron los datos de "x" e <br>
"y" de prueba y entrenamiento

<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/d16ed79a-7ac3-45f6-ae31-b83f929100c0)

<br>

Una vez obtenidos las variables de entrenamiento y prueba se implementará el modelo y tomaremos sus métricas para un análisis posterior

<br>
Una vez realizado la separación de las variables de entrenamiento y prueba, se utilizó el algoritmo de Kfolds con <br>
Cross Validation y RandomizedSearchCV para encontrar los mejores parámetros para nuestro modelo (Cabe recalcar que para el ejemplo  <br>
estamos usando Naive Bayes con BernulliNB y como este modelo solo funciona con datos binarizados las variables x_test y x_train han sido <br>
binarizadas, esto solo ocurrirá para este modelo)

<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/1a4775a8-3b68-41b8-92fb-910d30e09785)

<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/030c5f93-1f1d-48ce-819d-3f3a4eae8bcc)

<br>

Una vez optenidos los mejores parametros los usaremos para la implementación del modelo en condiciones optimas (optimización del modelo)

<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/0ce63630-452d-406e-8b0d-b2fd200464a2)

<br>

Una vez implementado, se obtendrán las métricas del modelo, y se compararán con las métricas del modelo sin optimización, para eso se hará<br>
en torno a la Matrix de confusión

<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/804a6973-e48d-49d5-bea1-623f457ecae7)

<br>

<h2>3. Evaluación</h2>

Una vez obtenidas todas las métricas de todos los modelos procederemos a compararlas entre si para la selección del mejor método. <br>
Para el caso de estudio la métrica mas representativa sera la Specificity pues esta trabaja con los verdaderos negativos y por <br>
la naturaleza del ejercicio (la variable a predecir) estamos buscando los 0 verdaderos sobre los 0 falsos pues según el <br>
archivo "german_dataset_dictionary.txt" cuando el valor de la variable a predecir es 0 significa que el cliente es muy probable <br>
que pague.

<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/514c9d26-259a-4e35-9747-f4e39815f853)

<br>

En conclusión el mejor modelo para este caso sera RandomForestClassifier

<h2>4. Predicción</h2>







# Evaluación y Selección del Modelo














