# Localización de Objetos en Imágenes con PyTorch

La localización de objetos consiste en identificar y ubicar un objeto dentro de una imagen, prediciendo un cuadro delimitador (bounding box) alrededor de él. Este proyecto implementa una solución basada en aprendizaje profundo utilizando PyTorch y 
redes neuronales convolucionales (CNNs). El modelo se construye sobre EfficientNet, una arquitectura de red neuronal eficiente y precisa, que se ajusta para predecir las coordenadas de los cuadros delimitadores. El proyecto muestra cómo se realizan la aumentación de datos, el entrenamiento del modelo y su evaluación para tareas de localización de objetos.

## Descripción

Este proyecto implementa un modelo de **localización de objetos** en imágenes utilizando redes neuronales convolucionales (CNN) con la librería **PyTorch**. El objetivo es predecir las coordenadas de un cuadro delimitador (bounding box) que encierra el objeto de interés en una imagen dada.

El pipeline incluye las siguientes etapas:

- **Preprocesamiento de datos y augmentación**: Se emplea **Albumentations** para realizar aumentación de datos, aplicando transformaciones como rotaciones, flips y redimensionado.
- **Modelo CNN preentrenado**: Utiliza **EfficientNet-B0** preentrenado de **timm**, modificado para realizar regresión de las coordenadas de los bounding boxes.
- **Entrenamiento y evaluación**: Se entrena el modelo para minimizar la pérdida (MSE) entre las coordenadas reales y predichas.
- **Visualización de resultados**: Los cuadros delimitadores predichos se comparan visualmente con los valores reales utilizando **OpenCV** y **Matplotlib**.



## Instalación

1. **Clona este repositorio**:

    ```bash
    git clone https://github.com/[tu_usuario]/[nombre_repo].git
    cd [nombre_repo]
    ```

2. **Instala las dependencias**:

    Asegúrate de tener Python 3.x instalado. Luego, instala las dependencias necesarias ejecutando:

    ```bash
    pip install -r requirements.txt
    ```

3. **Descarga el dataset**:

    El dataset se puede clonar desde el siguiente repositorio de GitHub:

    ```bash
    git clone https://github.com/parth1620/object-localization-dataset.git
    ```

    Asegúrate de que el archivo `train.csv` y las imágenes están correctamente estructurados.

## Uso

1. **Entrenamiento del Modelo**

Para entrenar el modelo desde cero, ejecuta el siguiente comando:

```bash
python src/train.py
```


## Configuración del Modelo

**Backbone:** EfficientNet-B0 (preentrenado en ImageNet).

**Pérdida:** Error Cuadrático Medio (MSE) entre las coordenadas del bounding box real y predicho.

**Optimizador:** Adam, con tasa de aprendizaje inicial de 0.001.

**Aumentación:** Se aplica resize, flips horizontales y verticales, y rotación aleatoria durante el entrenamiento.
