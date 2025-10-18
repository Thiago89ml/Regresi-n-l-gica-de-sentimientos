# Regresi-n-l-gica-de-sentimientos

IMPORTACIÓN Y LECTURA DE DATOS

Primero que todo, se importó pandas para posteriormente crear una variable asociada a la lectura del archivo CSV.

Para asegurarse de trabajar con los datos en buenas condiciones, se decidió utilizar el método isnull() para descartar posibles valores nulos, pero se comprobó que no había ninguno.

DIVISIÓN DE DATOS

Una vez “limpiados” los datos, se procedió a dividirlos por medio de train_test_split.
En un principio se pensó en trabajar únicamente con las columnas text y sentiment, tal como lo pedía la consigna, pero con el fin de obtener resultados con mayores posibilidades, se incluyó también la columna emotion en la división, teniendo así dos variables independientes.

Para tomar ambas variables independientes dentro del split, se realizó una concatenación con comillas simples vacías y el signo “+”, logrando crear una única variable combinada.

En cuanto a la división, se estableció un 25% de los datos para la prueba y el 75% restante para el entrenamiento.

TRANSFORMACIÓN DE DATOS

Como se quería trabajar con datos de tipo objeto y analizar el contenido textual sin necesidad de convertirlos a valores numéricos, se decidió emplear el CountVectorizer, que cuenta la frecuencia de las palabras que se repiten dentro del texto.

Para ello, se creó una variable asociada al CountVectorizer, y mediante esta se procedió a vectorizar tanto los datos de entrenamiento como los de prueba.

SELECCIÓN DEL MODELO

Para esta actividad se decidió trabajar con el modelo de Regresión Logística, por lo que se importó LogisticRegression.

Como en trabajos anteriores, se creó una variable para guardar el modelo asociado, y posteriormente se ajustó el modelo mediante el método fit() con los datos de entrenamiento.

MEDICIÓN DE LA EXACTITUD

Para medir la exactitud del modelo se importó accuracy_score, con el fin de obtener un resultado porcentual.

Se creó una variable asociada al modelo de regresión junto con los datos X de prueba.
Luego, se aplicó accuracy_score y se almacenó el resultado en una variable destinada a guardar la exactitud del modelo.
Finalmente, se imprimió el valor de accuracy, que reflejaba el nivel de precisión obtenido.

SEGUNDA PARTE

En esta segunda parte se utilizó nuevamente el método read_csv y se volvió a importar CountVectorizer.

Para el segundo CSV se creó una variable denominada “nueva”, encargada de guardar los datos de text y emotion mediante una concatenación, tal como se había hecho anteriormente en el split.

Posteriormente, se creó una variable X_nueva, encargada de vectorizar la variable “nueva”.

Luego, se generó una variable llamada resultado, que contenía las predicciones del modelo aplicadas sobre X_nueva.
Después, se creó una columna llamada 'etiqueta', destinada a guardar los resultados de la predicción realizada.

Finalmente, mediante el comando output, y utilizando las columnas id y etiqueta (recién creada), se generó un nuevo archivo CSV listo para subir al ranking del profesor.
