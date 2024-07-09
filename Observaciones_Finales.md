# Trabajo Práctico Nº 2 - Redes Recurrentes y Transformers

## Problema 1 - Audio MNIST

#### Introducción

Utilizando el dataset proporcionado, formado por clips de audio con las locuciones correspondientes a los dígitos, el objetivo es construir un modelo de clasificación utilizando redes neuronales que pueda inferir con precisión el dígito en cuestión. 
Antes de entrenar y evaluar los modelos sugeridos por la catedra, se realizó un completo análisis exploratorio en el que evaluamos:
* La duración de los clips de audio
* Distribución de las duraciones de los clips
* Valores mínimos y máximos de las muestras de audio
* Balance de los clips por dígito en train y test
* Formas de onda de los clips
* Espectrogramas

#### **Modelos**

Para la ejecución de esta actividad se decidió entrenar dos modelos de distintas arquitecturas y comparar los resultados:
* CNN - Modelo Convolucional
* RNN - Modelo Rcurrente 

**CNN:** 
> Los clips de audio son interpretados como imágenes.
> Se convierten en espectrogramas, que son representaciones visuales de las frecuencias presentes en el audio a lo largo del tiempo.
> Estas imágenes de espectrogramas se procesan mediante el modelo CNN, que extrae características relevantes de manera similar a cómo procesaría imágenes tradicionales, permitiendo clasificar el contenido del audio en diferentes categorías como son, en este caso, los dígitos.

**RNN:**
> Los espectrogramas se tratan como secuencias de datos bidimensionales.
> La LSTM bidireccional permite capturar las dependencias temporales en ambas direcciones del espectrograma.
> Esto que es crucial para entender patrones temporales complejos en el audio y poder clasificarlos correctamente según sea el dígito correspondiente.


#### Métricas y conclusiones
En ambos modelos se obtienen métricas muy buenas con excelentes resultados en las inferencias, tal como se aprecia en ambas matrices de confusión. 

Para el modelo **CNN**:
```
Accuracy (CNN): 98.40%
Precision (CNN): 98.45%
Recall (CNN): 98.40%
F1-Score (CNN): 98.40%

Confusion Matrix (CNN):
 [[42  0  1  0  0  0  0  0  0  0]
 [ 0 40  0  0  0  0  0  0  0  0]
 [ 0  0 46  0  0  0  0  0  0  0]
 [ 0  0  1 54  0  0  0  0  0  0]
 [ 0  0  0  0 46  0  0  0  0  0]
 [ 0  0  0  1  0 54  0  0  0  0]
 [ 0  0  0  0  0  0 63  0  1  0]
 [ 0  0  1  0  0  0  1 49  0  0]
 [ 0  0  0  0  0  0  0  0 47  0]
 [ 0  0  0  0  0  2  0  0  0 51]]
```

Para el modelo **RNN**:
```
Accuracy (RNN): 98.60%
Precision (RNN): 98.61%
Recall (RNN): 98.60%
F1-Score (RNN): 98.60%

Confusion Matrix (RNN):
 [[53  0  0  0  0  0  0  0  0  0]
 [ 0 32  0  0  0  0  0  0  0  2]
 [ 0  0 53  0  0  0  0  0  0  0]
 [ 0  0  1 55  0  0  0  0  0  0]
 [ 0  1  0  0 57  0  0  0  0  0]
 [ 0  0  0  0  0 56  0  0  0  0]
 [ 0  0  0  0  0  0 51  0  1  0]
 [ 0  0  0  0  0  0  0 48  0  0]
 [ 0  0  0  0  0  0  1  0 44  0]
 [ 0  1  0  0  0  0  0  0  0 44]]
```

Puede observarse que ambos modelos tienen una performance excelente, por lo que podría emplearse cualquiera de los dos. 
También se evidencia que ambos se desempeñan muy bien con respecto al ajuste, siendo que no existe overfitting significativo en ninguno de ellos.
La única diferencia que puede mencionarse entre ellos tiene que ver con la complejidad del modelo y los tiempos de entrenamiento. 
En este sentido, el modelo RNN obtiene una clara ventaja por sobre el CNN.

#### Inferencia
Se hace notar que para la evaluación de los modelos se intentó hacer inferencia con clips propios de audio, tanto pregrabados como capturados en vivo en el notebook.
La idea era mostrar la  distribución de probabilidades y la asignación de una categoría para estos clips propios.
Pero en ninguno de los casos fue posible igualar la configuración de la grabación original de los clips del dataset, por lo que se descartó la idea y se evaluaron directamente sobre los datos de test.

#### Nota 
En algún momento del desarrollo de la actividad, estuvimos probando con un modelo RNN (CNN + LSTM) pero el rendimiento de los dos modelos anteriores, sumado a la necesidad de seguir depurando los errores obtenidos, hizo que esta linea de trabajo se descartara.
De todos modos, y a modo de testigo del trabajo realizado en este apartado, se optó por dejar en el notebook los bloques correspondientes y los resultados erróneos para cotejarlos con los satisfactorios.



---


## Problema 2 - Fake News

#### Introducción

Utilizando el dataset proporcionado, formado por artículos de noticias, el objetivo es construir modelos de generación de texto utilizando redes neuronales que puedan generar noticias ficticias. 
Antes de entrenar y evaluar los modelos sugeridos por la catedra, se realizó un completo análisis exploratorio en el que evaluamos:
* Cantidad de palabras y oraciones
* Frecuencia de las palabras y caracteres más comunes
* Longitudes de las palabras y oraciones
* Distribución de las longitudes
* Valores máximos de las longitudes de palabras y oraciones

#### **Modelos**

Para la ejecución de esta actividad se decidió construir dos modelos de distintas arquitecturas y comparar los resultados:
* Modelo "Caracter a Caracter"
* Modelo "Palabra a Palabra"

**Modelo "Caracter a Caracter":** 
> Utiliza una arquitectura que permite capturar dependencias temporales y contextuales en el texto generado, aprendiendo patrones de coherencia, puntuación y estilo lingüístico.

**Modelo "Palabra a Palabra":** 
> Utiliza una arquitectura que permite aprender la estructura compleja del lenguaje. Utiliza una estructura que alimenta secuencialmente palabras previamente generadas como entrada para predecir la siguiente palabra en la secuencia.


#### Ejemplos de generaciones de texto

* **Modelo "Caracter a Caracter":** 
> *"OpenAI launch a fechips complaying of the northern in three of service echnology vocit worts all-over for U.S. anyol, in Series St. Leapound."*

* **Modelo "Palabra a Palabra":** 
> *"Like the lash inspired the necessary aggressiveness to beat the world 39s first new era to traditional animated films pixar or a rare analyst used"*

#### Conclusiones
Puede observarse que los resultados del primer modelo, aunque evidencian "algo" de coherencia y respeto por la puntuación, son muy malos en términos de sentido y cohesión.
Por otro lado, el segundo modelo muestra resultados más convincentes en relación a la coherencia y fluidez del texto. 
Desarrolla frases con estructura y sentido gramatical correctos, pero pueden evidenciarse aún algunos errores menores y la precariedad en la creatividad con que genera el contenido, muy condicionado a la información suministrada como entrenamiento. 

#### Nota 
Se deja constancia que, debido a las limitaciones técnicas que tiene el entorno de trabajo de Google Colab, el apartado "b" de este segundo problema (*modelo palabra a palabra*) fue generado en un notebook independiente en Kaggle. 
Esta plataforma brinda algunos aspectos técnicos superadores frente al primero mencionado. Por este motivo es que el notebook presenta una estética ligeramente diferente y se omiten en él muchos de los procesos realizados previamente en el otro archivo.
