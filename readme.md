# Descripción del Reto para el Curso

## Propósito
Una imagen puede marcar la diferencia para miles de animales callejeros que buscan un hogar. Las fotos más atractivas de mascotas tienen más probabilidades de generar interés y acelerar su adopción. Pero, ¿qué hace que una foto sea buena? A través de técnicas de **Deep Learning**, podemos determinar con precisión el atractivo de una foto de mascota y sugerir mejoras que aumenten sus posibilidades de ser adoptadas.

**PetFinder.my**, una plataforma líder en bienestar animal en Malasia, utiliza actualmente un **Cuteness Meter** básico para clasificar las fotos de mascotas, analizando la composición y otros factores en comparación con miles de perfiles. Sin embargo, este algoritmo es experimental y puede mejorarse.

El reto consiste en desarrollar un modelo basado en **Deep Learning** que prediga el "Pawpularity" de las fotos de mascotas utilizando imágenes en bruto y metadatos. Si el modelo tiene éxito, se integrará como una herramienta de IA para mejorar la calidad de las fotos y sugerir mejoras en la composición, ayudando a que los animales encuentren hogares más rápido.

Este proyecto no solo busca desarrollar un modelo efectivo, sino también demostrar tus conocimientos en **Deep Learning** como parte fundamental para superar el curso.


## Parámetros

- **Imágenes**: Fotos de los perfiles de mascotas proporcionadas en formato .jpg.
- **Metadatos de las fotos**: Etiquetas manuales de calidad visual y parámetros de composición, que incluyen características como:
  - **Focus**: La mascota se destaca contra un fondo limpio.
  - **Eyes**: Ambos ojos están mirando al frente o casi al frente.
  - **Face**: El rostro es claramente visible y está mirando al frente.
  - **Near**: La mascota ocupa una parte significativa de la foto.
  - **Action**: La mascota está en medio de una acción (por ejemplo, saltando).
  - **Accessory**: La mascota tiene algún accesorio físico o digital (excluyendo collar y correa).
  - **Group**: Hay más de una mascota en la foto.
  - **Collage**: Foto retocada digitalmente.
  - **Human**: Hay un humano en la foto.
  - **Occlusion**: Objetos no deseados bloquean parte de la mascota.
  - **Info**: Texto o etiquetas añadidos a la foto.
  - **Blur**: La imagen está desenfocada o con ruido, especialmente en los ojos y rostro.

## Datos

### Conjunto de Entrenamiento

- **train/**: Carpeta que contiene las fotos del conjunto de entrenamiento en formato `{id}.jpg`, donde `{id}` es un ID único de Perfil de Mascota.
- **train.csv**: Archivo que contiene la metadata de las fotos del conjunto de entrenamiento y el objetivo, el puntaje de Pawpularity de cada foto.

### Conjunto de Prueba de Ejemplo

- **test/**: Carpeta con imágenes generadas aleatoriamente, similar al formato de las fotos del conjunto de entrenamiento.
- **test.csv**: Metadata generada aleatoriamente, similar a la metadata del conjunto de entrenamiento.
- **sample_submission.csv**: Archivo de envío de muestra en el formato correcto.

### Metadata de las Fotos

Tanto `train.csv` como `test.csv` contienen metadata etiquetada manualmente para cada foto en el conjunto de entrenamiento y prueba, respectivamente. Cada foto está etiquetada con 1 (Sí) o 0 (No) para las características mencionadas anteriormente.

## Evaluación

El modelo será evaluado utilizando el **Root Mean Squared Error (RMSE)**. El RMSE mide la diferencia entre los valores reales y los valores predichos por el modelo. Se define como:

RMSE = sqrt( (1/n) * Σ (y_i - ŷ_i)^2 )

Donde:
- ŷ_i es el valor predicho.
- y_i es el valor original.
- n es el número total de instancias.


### Archivo de Envío

Para cada `Id` en el conjunto de prueba, debes predecir una probabilidad para la variable objetivo, **Pawpularity**. El archivo de envío debe tener un encabezado y estar en el siguiente formato:

```csv
Id,Pawpularity
0008dbfb52aa1dc6ee51ee02adf13537,99.24
0014a7b528f1682f0cf3b73a991c17a0,61.71
0019c1388dfcd30ac8b112fb4250c251,6.23
00307b779c82716b240a24f028b0031b,9.43
00320c6dd5b4223c62a9670110d47911,70.89
...
