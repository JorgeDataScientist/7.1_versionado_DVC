

```markdown
# MNIST Dataset Classifier (Digit "3" vs Others)

Este proyecto tiene como objetivo preprocesar y visualizar el dataset MNIST, específicamente para clasificar el dígito "3" frente a otros dígitos. El código permite cargar el dataset, dividirlo en conjuntos de entrenamiento y prueba, y luego crear un directorio organizado con imágenes del número "3" y otros dígitos para su posterior uso en tareas de clasificación.

## Descripción de las Funciones

### 1. **Carga y Preprocesamiento de Datos**

El primer paso del código es cargar el dataset MNIST desde OpenML usando la librería `sklearn`. Se cargan las imágenes y etiquetas del dataset y se dividen en conjuntos de entrenamiento y prueba.

- **Carga de los datos**:  
  El código usa `fetch_openml("mnist_784")` para obtener las imágenes (X) y etiquetas (y) del dataset MNIST. Posteriormente, se realiza una división en entrenamiento y prueba utilizando `train_test_split`.

```python
X, y = fetch_openml("mnist_784", version=1, return_X_y=True, as_frame=False)
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=10000)
```

### 2. **Visualización de Imágenes Aleatorias**

Se implementa una función para visualizar aleatoriamente 25 imágenes de un conjunto de datos. En este caso, se pueden visualizar tanto imágenes del número "3" como de otros números.

- **Visualización con `matplotlib`**:  
  La función `plot_samples(X)` muestra las imágenes en una cuadrícula de 5x5. Las imágenes se seleccionan aleatoriamente de los datos pasados como argumento (ya sea solo de números "3" o de otros números).

```python
def plot_samples(X):
    # Código que muestra 25 imágenes aleatorias
```

### 3. **Creación del Dataset Organizado**

A continuación, el código organiza las imágenes en un conjunto de directorios:  
- **train/3/**: Imágenes de entrenamiento del número "3"
- **train/no3/**: Imágenes de entrenamiento de otros números
- **test/3/**: Imágenes de prueba del número "3"
- **test/no3/**: Imágenes de prueba de otros números

La función `generate_dataset()` se encarga de crear estas carpetas y guardar las imágenes en ellas. Además, se divide el dataset en entrenamiento y prueba, separando una cantidad específica de imágenes para las pruebas, definida por el parámetro `test_size`.

```python
def generate_dataset(X_train_3, X_train_no_3, test_size):
    # Código para organizar y guardar imágenes en carpetas de entrenamiento y prueba
```

### 4. **Obtener Rutas de las Imágenes**

La función `get_paths()` obtiene las rutas de las imágenes almacenadas en las carpetas creadas anteriormente. Estas rutas se utilizan para cargar las imágenes cuando se desee visualizarlas o realizar un procesamiento posterior.

```python
def get_paths():
    # Código para obtener las rutas de las imágenes de "3" y "no3"
```

### 5. **Visualización de Imágenes desde Rutas**

Por último, se proporciona una función llamada `plot_images()` que recibe las rutas de las imágenes y las visualiza. Esta función selecciona aleatoriamente 25 imágenes de las rutas proporcionadas y las muestra en una cuadrícula de 5x5.

```python
def plot_images(paths):
    # Código para mostrar 25 imágenes desde rutas aleatorias
```

## Propósito del Proyecto

El propósito principal de este proyecto es preparar y organizar un subconjunto del dataset MNIST para tareas de clasificación binaria, donde el objetivo es identificar si una imagen representa el dígito "3" o no. El código carga, divide y organiza los datos de manera eficiente para ser utilizados en el entrenamiento y evaluación de modelos de clasificación, como los basados en redes neuronales o máquinas de soporte vectorial (SVM).

## Requisitos

- **Python 3.x**
- **Librerías**:
  - `scikit-learn` (para el manejo de datasets y particiones)
  - `matplotlib` (para la visualización de imágenes)
  - `scikit-image` (para leer y guardar imágenes)
  - `numpy` (para manipulación de arrays)
  - `glob` (para obtener rutas de archivos)

Puedes instalar las dependencias necesarias utilizando `pip`:

```bash
pip install scikit-learn matplotlib scikit-image numpy
```

## Uso

1. **Generación de Dataset**:  
   Para crear el dataset organizado en carpetas, utiliza la función `generate_dataset()` pasándole las imágenes del número "3" y de otros números, junto con el tamaño del conjunto de prueba.

```python
generate_dataset(X_train_3, X_train_no_3, test_size=1000)
```

2. **Visualización de Imágenes**:  
   Para visualizar las imágenes de entrenamiento de números "3", puedes usar la función `plot_images()` pasando las rutas obtenidas con `get_paths()`.

```python
plot_images(train_3)
```

## Conclusión

Este código es útil para crear un dataset organizado del dígito "3" y otros números del conjunto MNIST, y para realizar visualizaciones rápidas de las imágenes contenidas en el dataset. Se puede utilizar como base para entrenar modelos de clasificación de dígitos.

```

### Explicación del **README**:
1. **Propósito del Proyecto**: Explica qué hace el código y por qué se crea un dataset organizado con los números "3" y otros números.
2. **Descripción de Funciones**: Describe las funciones principales y su propósito.
3. **Requisitos**: Menciona las librerías necesarias para ejecutar el código.
4. **Uso**: Explica cómo usar las funciones para crear el dataset y visualizar las imágenes.

🚀