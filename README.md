# **Predicción de Popularidad de Videos en YouTube con Modelos LSTM**

Este proyecto aborda la predicción del comportamiento de las vistas de videos que aparecen en la sección *Trending* de YouTube, utilizando diferentes variantes de redes neuronales LSTM. El objetivo es anticipar cómo evolucionarán las vistas de un video a partir de su historial temporal y ciertos metadatos.

## **Descripción**

Los videos en tendencia presentan series temporales cortas, ruidosas y altamente variables, lo que vuelve difícil anticipar su crecimiento. Para estudiar este problema, se construyeron distintos modelos basados en LSTM que intentan aprender patrones característicos de popularidad.

El proyecto incluye:

* Preparación y limpieza de un dataset de videos en tendencia.
* Construcción de ventanas temporales para series de tiempo.
* Entrenamiento de modelos LSTM univariantes y multivariantes.
* Experimentación con modelos por clústers.
* Un esquema de *transfer learning* entre modelos.

El objetivo principal es comparar estos enfoques y entender cuál se adapta mejor a la naturaleza del dataset.

## **Enfoque**

### **1. Modelos LSTM**

Se implementan distintas arquitecturas LSTM para predecir el valor de vistas del día siguiente.
Se probaron:

* Modelos univariantes (solo vistas).
* Modelos multivariantes (vistas + otras variables numéricas).
* Modelos especializados según grupos de videos (clústers).
* Modelo multivariante entrenado con *transfer learning* desde el modelo univariante.

### **Ventanas deslizantes**

Cada ejemplo de entrenamiento se construye a partir de una ventana de **7 días consecutivos**, usada para predecir el octavo día.

---

## **Funcionalidad**

* **Procesamiento del dataset:**
  Filtrado, ordenamiento temporal, limpieza, codificación de categorías y normalización.

* **Construcción de series temporales:**
  Generación automática de ventanas para entrenar los modelos LSTM.

* **Entrenamiento de modelos:**
  Pruebas con múltiples configuraciones y uso de callbacks como *EarlyStopping*.

* **Transfer Learning:**
  Reutilización y adaptación de pesos para acelerar y estabilizar el entrenamiento multivariante.

* **Comparación de resultados:**
  Evaluación del desempeño en un conjunto de prueba común.

## **Requisitos**

Este proyecto utiliza Python y las siguientes bibliotecas principales:

* **TensorFlow / Keras:** para los modelos LSTM.
* **NumPy & Pandas:** manejo y transformación de datos.
* **scikit-learn:** normalización, clústers y métricas.
* **Matplotlib / Seaborn:** visualización.
