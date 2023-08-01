
# Proyecto final - Deep Learning

Reconocimiento de imágenes: Modelo de aprendizaje profundo usando redes convolucionales para la detección de daños estructurales en obras civiles.

## Descripción del problema

Comúnmente se realiza la evaluación de afectaciones estructurales en los edificios de forma manual mediante la toma de varias fotografías para evaluar si estas tendrán relevancia en el futuro en caso de que suceda una catástrofe natural que afecte a la estructura del edificio y a los habitantes del mismo. 

Para realizar esta evaluación se toman muchos recursos de forma manual en las inspecciones realizadas.

## Importancia de Detectar Grietas en Concreto

El concreto es uno de los materiales más utilizados en construcción y con el tiempo las estructuras de concreto pueden desarrollar grietas debido a ello es de vital importancia de detectar y clasificar estas grietas para garantizar la seguridad.

- Seguridad: Las grietas pueden llevar al fallo estructural.
- Economía: Prevencion de costos asociados con reparaciones de emergencia.
- Durabilidad: Prolongar la vida útil de las estructuras.

## Objetivo del proyecto

Mediante la toma de imágenes y el uso del aprendizaje profundo a través de redes neuronales es posible automatizar la categorización de las muestras obtenidas durante inspecciones permitiendo discernir si una estructura está dañada y facilitando la toma de decisiones a nivel técnico.

Una red neuronal podría categorizar con precisión las fotos de estructuras de concreto en "Positivo" y "Negativo". 

Dicha red se entrenaría para reconocer aspectos claves en las imágenes tales como texturas, patrones y formas luego estos detalles se usan para determinar si hay fisuras presentes.


## Clientes o consumidores potenciales

- Gobierno (Ministerio de Vivienda y Obras públicas), 
Constructoras, 
- Empresas de insumos estructurales (Por ejemplo: Holcim, UCEM, entre otros), 
- Empresas de mantenimiento de edificios y peritos. 

## Conjunto de datos

El conjunto de datos contiene imágenes de superficies de concreto que tienen grietas. Los datos se recopilan de varios edificios del campus de METU. El conjunto de datos se divide en dos como imágenes de grietas negativas y positivas para la clasificación de imágenes.

Cada clase tiene 2000  imágenes con un total de 40000 imágenes con 256 x 256 píxeles con canales RGB. 

El conjunto de datos se genera a partir de 458 imágenes de alta resolución (4032 x 3024 píxeles) con el método propuesto por Zhang et al (2016).
Las imágenes de alta resolución varían en términos de acabado superficial y condiciones de iluminación. 

## Modelo propio
La red esta compuesta por una red convolucional con 3 capas ocultas, de entrada para imágenes RGB de 256x256 pixeles, maxpooling de 2 dropout de 20% de probabilidad y función de activación ReLU.

Resnet-50 es una red neuronal convolucional profunda con bloques residuales que permite entrenar redes más profundas con menos problemas de desvanecimiento del gradiente.
Usamos ResNet-50 con una adaptación a un problema de clasificación binario pasando de 1000 salidas a 2 (positivo y negativo).

DenseNet-121 es una arquitectura de red neuronal convolucional con conexiones densas entre capas, lo que permite un flujo de información más efectivo durante el entrenamiento y hace que la red sea más eficiente en términos de parámetros.
Usamos DenseNet-121 una adaptación a un problema de clasificación binario pasando de 1024 salidas a 2 (positivo y negativo).
