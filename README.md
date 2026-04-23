# Sistema de Recomendación de Libros Basado en Inteligencia Artificial: Implementación de Muestreo Negativo y Mitigación del Cold Start
**Autor**
  - Sebastian Enrique Rodriguez Leiva

### Descripción
  - Este programa consiste en un pipeline de ingeniería de datos (ETL) y preprocesamiento avanzado diseñado para transformar registros transaccionales de préstamos bibliotecarios en un dataset     estructurado y optimizado para el entrenamiento de modelos de Inteligencia Artificial.

    El sistema automatiza la limpieza de datos, la gestión de usuarios con poca actividad (Cold Start) y la síntesis de interacciones negativas, asegurando que el modelo de recomendación final     sea robusto y preciso.

### Propósito de la investigación
  - La investigación está orientada hacia la Optimización de Sistemas de Recomendación (RecSys) mediante Feedback Implícito. El foco principal es resolver dos desafíos críticos en el área:
  
      1.- Calidad del Perfil de Usuario: Mitigar el problema del arranque en frío mediante filtros de densidad de interacción.
  
      2.- Muestreo Negativo: Generar datos sintéticos que permitan al modelo aprender no solo qué le gusta al usuario, sino qué elementos son menos propensos a ser consumidos, mejorando así la capacidad de discriminación del algoritmo.

### Tecnlogías usadas

  - Pandas & NumPy
  - Scikit-Learn
  - TensorFlow / Keras

### Guía de instalación
  **1. Requisitos Previos**
  - Una cuenta de Google para acceder a Google Colab.
  - El archivo de datos `5. DATASET-PRESTAMOS-EN-SALA-IV-TRIMESTRE-2023.csv` (asegúrate de tenerlo guardado en tu Google Drive).

  **2. Descarga y Carga del Notebook**
  - Descarga el archivo `Proyecto_Final.ipynb` desde este repositorio
  - Sube el archivo a tu unidad de Google Drive o ábrelo directamente desde Google Colab seleccionando la pestaña "Subir".
  **3. Configuración del Acceso a Datos**
  -  Para que el programa pueda leer la fuente de datos, debes montar tu unidad de Drive y actualizar la ruta del archivo:

      1.- Ejecuta la celda de montaje de Google Drive que aparecerá al inicio del notebook:
     
      ```bash
     from google.colab import drive
     
     drive.mount('/content/drive')
      ```
     2.- Localiza tu archivo: Busca el archivo CSV en el panel izquierdo de archivos de Colab dentro de la carpeta `drive`. Haz clic derecho sobre el archivo y selecciona "Copiar ruta".
     3.- Reemplaza la ruta: Busca la sección `# --- 1. RUTA EXACTA DE TU GOOGLE DRIVE ---` en el código y pega tu ruta personalizada entre las comillas:

      ```bash
        import pandas as pd

        # --- REEMPLAZA ESTA LÍNEA CON TU RUTA COPIADA ---
        ruta_prestamos = '/content/drive/MyDrive/TU_CARPETA/TU_ARCHIVO.csv'
      ```

### Base de Datos
`5. DATASET-PRESTAMOS-EN-SALA-IV-TRIMESTRE-2023.csv`
| Nombre archivo | Contenido| Contenido|
|----------------|----------|----------|
| **LECTOR_DOC_IDENTIDAD** |  Identificador único del usuario (DNI/Pasaporte). |  Categórico/ID  |
| **LECTOR_FECHA_NACIMIENTO** | Fecha de nacimiento del lector (utilizada para calcular edad). |  Fecha (String)  |
| **EJEMPLAR_TITULO** | Matriz obtenida de la predicción |  Texto  |
| **EJEMPLAR_AUTOR** | Paqueterías utilizadas |  Texto  |
| **EJEMPLAR_EDICION** | Set up para ejecución en consola |  Texto  |
| **EJEMPLAR_EDITORIAL** | Módulos necesarios para cargar datos, entrenar, predecir y obtener desempeño ncdg |  Texto  |
| **EJEMPLAR_ISBN_ISSN** | Jupyter notebook de ejecución para entrenar, predecir, cross validation y  obtención de desempeño con ncdg |  Texto  |
| **SALA** | Ubicación física de la biblioteca donde se realizó el préstamo. |  Categórico  |
