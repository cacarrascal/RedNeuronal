# Red Neuronal para Clasificar Flores Iris

Red neuronal construida con TensorFlow/Keras para clasificar especies de flores Iris a partir de sus características morfológicas (largo/ancho del sépalo y pétalo).

## Dataset

El dataset Iris contiene 150 muestras distribuidas en 3 especies:

| Especie      | Cantidad |
| ------------ | -------- |
| setosa       | 50       |
| versicolor   | 50       |
| virginica    | 50       |

Fuentes del dataset:

- Kaggle: `https://www.kaggle.com/datasets/arshid/iris-flower-dataset`
- El notebook incluye un botón para subir el archivo `iris.csv` desde tu equipo (Google Colab).

## Arquitectura del modelo

```
Input(shape=(4,))        # 4 características de entrada
Dense(16, relu)          # Capa oculta 1
Dense(8, relu)           # Capa oculta 2
Dense(3, softmax)        # Salida: 3 especies
```

Con un total de 243 parámetros entrenables.

## Requisitos

Instala las dependencias ejecutando:

```
pip install pandas numpy tensorflow scikit-learn matplotlib seaborn
```

Versión recomendada de Python: 3.8 o superior.

## Cómo usarlo

1. Abre `Red.ipynb` en [Google Colab](https://colab.research.google.com/) o en Jupyter Notebook.
2. Ejecuta las celdas en orden, de arriba hacia abajo.
3. En la celda 2 aparecerá un botón **"Choose Files"**: selecciona tu archivo `iris.csv`.
4. El modelo se entrenará automáticamente y mostrará:

   - Precisión sobre el conjunto de prueba.
   - Gráfica de precisión y pérdida durante el entrenamiento.
   - Matriz de confusión.
   - Predicción de una flor nueva de ejemplo.

## Flujo del pipeline

| Paso | Descripción                                |
| ---- | ------------------------------------------ |
| 1    | Importar librerías                         |
| 2    | Subir el dataset (`iris.csv`)              |
| 3    | Preprocesamiento y codificación de etiquetas |
| 4    | División entrenamiento/prueba (80/20)      |
| 5    | Normalización con `StandardScaler`         |
| 6    | Construcción de la red neuronal           |
| 7    | Compilación del modelo                     |
| 8    | Entrenamiento (100 épocas)                 |
| 9    | Evaluación sobre el conjunto de prueba     |
| 10   | Predicciones y prueba con una flor nueva   |
| 12   | Gráficas de precisión y pérdida            |
| 13   | Matriz de confusión                        |

## Resultados

- El modelo alcanza típicamente una precisión superior al 95% en el conjunto de prueba.
- La matriz de confusión permite ver visualmente cuántas flores de cada especie se clasificaron correctamente.

## Estructura del proyecto

```
Red/
├── Red.ipynb     # Notebook con el código completo
└── README.md     # Este archivo
```
