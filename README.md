# Unidad 15 · NLP en entornos productivos

## Introducción
En esta práctica trabajamos con el dataset **Customer Support on Twitter (twcs.csv)** para simular un caso real de negocio.  
El objetivo fue construir un pipeline automático de NLP que permita procesar grandes volúmenes de texto, aplicar análisis de sentimiento y clasificación simple, y calcular métricas relevantes para soporte al cliente.  

Este ejercicio conecta la teoría de NLP con su aplicación en entornos productivos, mostrando cómo la escalabilidad y la automatización impactan en métricas clave de negocio como TTR y ROI.

---

## Metodología

### Paso 6 – Limpieza de texto
Se normalizaron los tweets para reducir ruido y facilitar el análisis posterior:
- Conversión a minúsculas.  
- Eliminación de URLs y menciones.  
- Remoción de caracteres especiales.  

**Ejemplo de resultado:**

Original: "@sprintcare I did."
Limpio: "i did"

---

### Paso 7 – Análisis de sentimiento
Se utilizó **TextBlob** para calcular la polaridad de cada tweet y clasificarlo en tres categorías:

| Sentimiento | Proporción (%) |
|-------------|----------------|
| Neutro      | 51.48          |
| Positivo    | 31.15          |
| Negativo    | 17.37          |

👉 La mayoría de las consultas son neutrales, pero un 17% negativas requieren atención prioritaria.

---

### Paso 8 – Clasificación de consultas
Se definieron tres categorías simples para segmentar las consultas:

| Categoría        | Proporción (%) |
|------------------|----------------|
| Reclamos         | 95.27          |
| Soporte Técnico  | 2.70           |
| Facturación      | 2.03           |

👉 La gran mayoría son reclamos generales, mientras que los casos críticos (soporte y facturación) son minoritarios pero estratégicos.

---

### Paso 9 – Métricas de negocio
Se calcularon indicadores clave:

- **Tasa de automatización**: 100%  
- **Distribución de sentimiento**: Neutro 51%, Positivo 31%, Negativo 17%  
- **Tiempo de respuesta promedio (TTR)**: 2 minutos (vs. 10 minutos manuales)  

👉 El pipeline reduce drásticamente el TTR y elimina la necesidad de clasificación manual.

---

## 3. Resultados e interpretación

- **Escalabilidad**: el pipeline procesó miles de tweets de manera eficiente, demostrando capacidad para entornos productivos.  
- **Automatización**: el 100% de las consultas fueron clasificadas automáticamente, liberando al equipo de soporte de tareas repetitivas.  
- **Impacto en negocio (ROI)**: la reducción del TTR de 10 a 2 minutos implica un ahorro significativo en horas de soporte y beneficios económicos directos.  
- **Gestión de la experiencia del cliente**: atender rápidamente los casos negativos (17%) contribuye a reducir churn y mejorar la retención.  

---

## 4. Conclusiones

El pipeline NLP desarrollado cumple con los objetivos técnicos y genera un impacto tangible en métricas clave de negocio:

- Escala a grandes volúmenes de datos.  
- Automatiza procesos críticos.  
- Mejora la satisfacción del cliente.  
- Justifica la inversión a través de un ROI positivo.  

👉 Este caso demuestra cómo llevar NLP a producción no es solo un desafío tecnológico, sino una oportunidad estratégica para generar valor empresarial.

---

## 5. Anexos
- Código completo del notebook (Pasos 6–9).  
- Capturas de resultados de ejecución.  

