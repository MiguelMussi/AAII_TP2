# TUIA - Aprendizaje Automático II

## Trabajo Práctico Nº 2 - Redes Recurrentes y Transformers

### Problema 1 - Audio MNIST

#### Descripción 

En este problema, se presenta un conjunto de datos que contiene clips de audio correspondientes a dígitos hablados del 0 al 9.

#### Dataset

El dataset proporcionado incluye un total de 2500 clips de audio correspondientes a 5 locutores distintos, 50 clips por dígito por locutor.
https://www.tensorflow.org/datasets/catalog/spoken_digit


#### Objetivo

Utilizando el dataset proporcionado, el objetivo es construir un modelo de clasificación utilizando redes neuronales que pueda inferir con precisión el dígito correspondiente dado un clip de audio. Se deben entrenar y evaluar modelos utilizando técnicas adecuadas de validación y métricas de evaluación de clasificación.

Se solicita entrenar dos modelos de distintas arquitecturas y comparar los resultados:

* Modelo convolucional sobre los espectrogramas de los clips.
* Modelo recurrente sobre los espectrogramas de los clips.

Ver 
https://colab.research.google.com/github/FCEIA-AAII/lab11/blob/master/lab11-a.ipynb 
como ejemplo de obtención de espectrogramas a partir de clips de audio.

#### Entrega

La entrega debe incluir:
Código fuente de la solución implementada en Google Colab, que incluya:
* Análisis previo y preprocesamiento del set de datos.
* Definición y entrenamiento del modelo.
* Resultados de la evaluación del modelo, incluyendo métricas de desempeño y visualizaciones relevantes.

*Nota*: el código debe estar debidamente documentado con comentarios explicativos para que el trabajo sea fácilmente comprensible para otros revisores.

---

### Problema 2 - Fake News

#### Descripción

En el siguiente problema, se presenta un conjunto de datos correspondientes a resúmenes de artículos de noticias. El objetivo del problema es crear un modelo capaz de generar resúmenes ficticios de forma aleatoria.

#### Dataset

El dataset proporcionado incluye 120000 artículos correspondientes a 4 categorías distintas. En este caso, la categoría no es relevante, sólo utilizaremos el dataset como un cuerpo de texto para entrenar un modelo recurrente de generación de texto.
https://www.tensorflow.org/datasets/catalog/ag_news_subset

#### Objetivo

Utilizando el dataset construido, el objetivo es construir modelos de generación de texto utilizando redes neuronales que puedan generar noticias ficticias. Consultar el siguiente lab como referencia para la implementación:
https://colab.research.google.com/github/FCEIA-AAII/lab10/blob/master/lab10-b.ipynb

Se solicita experimentar con los siguientes tipos de modelos:

* Caracter a caracter: entrenar un modelo de generación de texto a nivel de caracteres como el correspondiente al Lab10 mencionado anteriormente.
* Palabra a palabra: entrenar un modelo de generación de texto a nivel de palabras, adecuando los procesos de entrenamiento e inferencia según sea necesario.

Generar artículos al azar y seleccionar 5 para cada modelo que resulten de interés. Comparar cualitativamente el tipo de resultado que se obtiene para cada tipo de modelo.

*No se requiere un análisis de métricas para este problema, se espera un análisis cualitativo de los resultados obtenidos.*


#### Entrega

La entrega debe incluir:
Código fuente de la solución implementada en Google Colab, que incluya:
* Análisis previo y preprocesamiento del set de datos.
* Definición y entrenamiento del modelo.
* Análisis y comparación de los resultados obtenidos para los diferentes modelos.

*Nota*: el código debe estar debidamente documentado con comentarios explicativos para que el trabajo sea fácilmente comprensible para otros revisores.

---

### Problema 3 *[Omitido por la cátedra]*

#### Descripción

*TBD: Problema basado en transformers*

#### Dataset

#### Objetivo

#### Entrega




