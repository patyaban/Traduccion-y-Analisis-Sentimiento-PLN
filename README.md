# Traducción de Texto y Análisis de Sentimiento con Transformers

Este proyecto implementa una solución avanzada de Procesamiento de Lenguaje Natural (NLP) para la unificación y análisis de reseñas de películas y series. Utiliza arquitecturas de aprendizaje profundo basadas en Transformers para traducir contenido de múltiples idiomas al inglés y, posteriormente, clasificar el sentimiento de cada reseña.

## Descripción del Proyecto

El objetivo principal es transformar un conjunto de datos heterogéneo (reseñas en inglés, francés y español) en una base de datos consolidada y etiquetada. El flujo de trabajo sigue una arquitectura de datos por capas (Bronce, Plata y Oro) para garantizar la integridad y calidad de la información.

### Características principales:

* **Traducción Automática:** Uso de modelos `Helsinki-NLP` para convertir sinopsis y reseñas al inglés.
* **Análisis de Sentimiento:** Implementación de `DistilBERT` para la clasificación binaria de sentimientos (Positivo/Negativo).
* **Almacenamiento Estructurado:** Exportación de resultados a formatos CSV y bases de datos relacionales SQLite.
* **Evaluación de Desempeño:** Cálculo de métricas de exactitud y reportes de clasificación detallados.

## Estructura del Desarrollo (Pipeline)

El proyecto se divide en cuatro fases críticas:

1. **Preprocesamiento (Capa de Bronce):** Extracción de datos desde archivos CSV, estandarización de columnas y etiquetado de idioma original.
2. **Traducción (Capa de Plata):** Implementación de modelos secuencia a secuencia (Seq2Seq) para la unificación lingüística, manejando restricciones de longitud mediante técnicas de truncamiento.
3. **Clasificación (Capa de Oro):** Aplicación de modelos de clasificación de secuencias para la detección de polaridad en el texto.
4. **Almacenamiento y Métricas:** Persistencia de datos y validación estadística del modelo frente a un conjunto de etiquetas de control.

## Requisitos Técnicos

Para ejecutar este proyecto, es necesario contar con un entorno de Python 3.12+ y las siguientes bibliotecas:

* **pandas:** Manipulación y análisis de estructuras de datos.
* **transformers:** Acceso a modelos pre-entrenados de Hugging Face.
* **torch:** Motor de cómputo para tensores y redes neuronales.
* **scikit-learn:** Cálculo de métricas y evaluación de modelos.
* **sqlite3:** Motor de base de datos relacional ligero.

### Instalación

```bash
pip install pandas transformers torch scikit-learn torchvision


## Modelos Utilizados

El sistema se apoya en modelos de última generación disponibles en la plataforma Hugging Face:

* **Francés a Inglés:** `Helsinki-NLP/opus-mt-fr-en`
* **Español a Inglés:** `Helsinki-NLP/opus-mt-es-en`
* **Análisis de Sentimiento:** `distilbert-base-uncased-finetuned-sst-2-english`

## Resultados

El resultado final es un archivo denominado `reviews_with_sentiment.csv` que contiene el esquema de salida esperado:

* **Title:** Nombre de la obra.
* **Year:** Año de estreno.
* **Synopsis:** Texto traducido al inglés.
* **Review:** Reseña unificada en inglés.
* **Original_Language:** Idioma de origen del registro.
* **Sentiment:** Clasificación final (POSITIVE / NEGATIVE).

---
**Autor:** Ana Patricia Aban Monzon
