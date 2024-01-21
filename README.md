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

<h3>1.2. Preprocesamiento de los Datos</h3>
Esta esta etapa consistió en:
Analizar los datos
Eliminar duplicados
Tratar valores nulos
Reemplazar valores categóritos por numéricos

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/32267303/0e67a084-81b3-4887-897f-83b12e18d924)
![image](https://github.com/pabloing93/credit-scoring-prediction/assets/32267303/a9b20248-a543-4aa8-883a-330e62949cb2)



<h3>1.3. EDA: Análisis exploratorio de los datos</h3>

Aplicamos técnicas de Feature Engineering
Agrupamos los datos para su análisis 
Realizamos un análisis exploratorio
Prescindimos de columnas que no aportaban información

<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/668713bf-ec30-4e6a-8b5a-48378db69178)

<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/4929b68f-1c0b-4706-90ab-c13f37a7c97e)

<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/cf005d92-30ff-41b1-a052-b28f840adbc8)

<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/32cee3d2-e5b6-433d-8077-81e8b5e5370e)


![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/e8249962-3c51-41ad-bff1-d1c6887abead)

<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/b3323c2a-b8d4-4af2-8a44-e2f7fec31745)


<br>

Observamos un desbalanceamiento en la columna objetiva por lo que aplicamos SMOTE para balanceralos

<br>

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/130804905/f59b30f7-9ba6-4fd4-9677-de552ef3164c)

<br>


![image](https://github.com/pabloing93/credit-scoring-prediction/assets/32267303/f1ac8d80-3b15-487f-b453-a41755adc462)


<h2>2. Modelos</h2>
<h3>2.2. Implementación de los modelos</h3>

Pusimos a prueba 5 modelos de aprendizaje automático y evaluamos por cada modelo 
6 métricas distintas para tomar una decisión...

Árboles de decisiones
KNN
Regresión Logística
Naive Bayes
Random Forest

<h3>2.3. Optimización de los modelos</h3>

Optimizamos los modelos para obtener las mejores combinaciones de parámetros

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

![image](https://github.com/pabloing93/credit-scoring-prediction/assets/32267303/e70ec9f2-a083-46b5-a8b9-f41ea28bc006)














