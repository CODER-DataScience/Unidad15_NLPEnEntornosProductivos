# Unidad 15 · NLP en entornos productivos

# Procesamiento de Lenguaje Natural (NLP) en Entornos Productivos

## Descripción del Proyecto
Este notebook documenta un ejercicio práctico centrado en la construcción de un pipeline automático de Procesamiento de Lenguaje Natural (NLP) utilizando el dataset **Customer Support on Twitter (twcs.csv)**. El objetivo principal es simular un caso real de negocio donde una empresa recibe un alto volumen de consultas diarias y necesita automatizar su procesamiento y análisis para mejorar la eficiencia y la toma de decisiones.

## Objetivos
- Procesar grandes volúmenes de texto de manera eficiente.
- Implementar pipelines automáticos de limpieza y análisis de texto.
- Aplicar análisis de sentimiento para entender la percepción del cliente.
- Clasificar consultas de manera simple para priorización y enrutamiento.
- Calcular métricas de negocio relevantes para el soporte al cliente.
- Reflexionar sobre la escalabilidad de la solución y el Retorno de la Inversión (ROI).

## Dataset
El proyecto utiliza el dataset `twcs.csv` que contiene interacciones de soporte al cliente en Twitter. Este dataset incluye campos como `tweet_id`, `author_id`, `inbound`, `created_at`, `text`, `response_tweet_id`, y `in_response_to_tweet_id`.

## Metodología y Pasos del Pipeline

### 1. Configuración e Importación de Librerías
Se instalan librerías necesarias como `textblob` y se importan `pandas`, `numpy`, `re` para manipulación de datos y expresiones regulares, y `TextBlob` para análisis de sentimiento. También se utiliza `google.colab.files` para la subida del dataset.

### 2. Carga y Exploración Inicial del Dataset
El archivo `twcs.csv` se sube y se carga en un DataFrame de pandas. Se realiza una inspección inicial para entender sus dimensiones, columnas y las primeras filas, revelando la estructura de los datos de los tweets.

### 3. Limpieza de Texto
Se define una función `clean_text` para normalizar los tweets. Esta función realiza las siguientes operaciones:
- Convierte todo el texto a minúsculas.
- Elimina URLs (`http://`, `https://`, `www.`).
- Elimina menciones de usuarios (`@usuario`).
- Elimina caracteres especiales, manteniendo solo letras y espacios.
El texto limpio se almacena en una nueva columna `clean_text`.

### 4. Análisis de Sentimiento
Se aplica `TextBlob` para calcular la polaridad del sentimiento de cada `clean_text`. La función `get_sentiment` devuelve un valor numérico. Este valor se clasifica en tres categorías:
- **Negativo**: Polaridad < -0.1
- **Positivo**: Polaridad > 0.1
- **Neutro**: Polaridad entre -0.1 y 0.1 (inclusive).
La distribución de sentimiento se calcula y se muestra, proporcionando una visión general de la percepción del cliente.

### 5. Clasificación de Consultas
Se implementa una función `classify_query` para categorizar los tweets basándose en palabras clave simples:
- **Facturación**: Si el texto contiene 'bill', 'charge' o 'factura'.
- **Soporte Técnico**: Si el texto contiene 'error', 'problem' o 'soporte'.
- **Reclamo**: Para cualquier otra consulta que no encaje en las categorías anteriores.
Esta clasificación automática ayuda a segmentar y priorizar las solicitudes.

### 6. Cálculo de Métricas de Negocio
Se calculan métricas clave para evaluar el impacto del pipeline:
- **Tasa de Automatización**: Porcentaje de consultas clasificadas automáticamente (en este caso, 100% ya que todas las consultas pasan por el clasificador).
- **Distribución de Sentimiento**: La proporción de tweets negativos, neutros y positivos.
- **Tiempo de Respuesta Promedio (TTR) Simulado**: Se simula una reducción del TTR de 10 minutos (manual) a 2 minutos (automático), y se calcula un TTR promedio ponderado.

## Resultados Clave y Conclusiones

- **Eficiencia en el Procesamiento**: El pipeline demostró capacidad para procesar millones de tweets de forma eficiente.
- **Automatización Completa**: Se logró una tasa de automatización del 100% en la clasificación de consultas simples, liberando recursos humanos.
- **Impacto Económico (ROI)**: La simulación del TTR sugiere una reducción de 10 a 2 minutos por consulta, lo que representa un ahorro significativo en costos operativos y una mejora en la satisfacción del cliente.
- **Visibilidad del Sentimiento**: El análisis reveló que aproximadamente el 17% de los tweets son negativos, destacando la necesidad de una rápida intervención en estos casos críticos.

## Escalabilidad y Valor Estratégico
Este proyecto demuestra que la implementación de NLP en entornos de soporte al cliente no solo es técnicamente viable sino que también ofrece un valor estratégico considerable. La automatización y el análisis de sentimiento permiten a las empresas:
- Escalar sus operaciones de soporte.
- Reducir costos operativos.
- Mejorar la experiencia del cliente mediante respuestas más rápidas y una mejor comprensión de sus necesidades.
- Priorizar eficientemente las consultas, especialmente las negativas, para reducir la rotación de clientes.

## Cómo Ejecutar el Notebook
1.  Asegúrate de tener un entorno Python con `pandas`, `numpy`, `textblob`, y `re` instalados. Si estás en Google Colab, las instalaciones se manejan automáticamente.
2.  Sube el archivo `twcs.csv` cuando se te indique (a través de `files.upload()`).
3.  Ejecuta las celdas del notebook secuencialmente para replicar el análisis.

Este pipeline sirve como una base sólida para futuras expansiones, como la integración con sistemas de gestión de tickets o el uso de modelos de NLP más avanzados para una clasificación y análisis de sentimiento más granular.
