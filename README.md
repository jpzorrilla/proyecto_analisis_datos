# Guía didáctica del proyecto de análisis de datos: Del dato crudo a la decisión

## Qué hace el código, paso a paso
- Ingesta y Exploración Inicial: Carga el conjunto de datos de la UNESCO (13.332 registros y 25 columnas) desde una URL o archivo local, inspeccionando dimensiones y memoria utilizada.
- Diagnóstico de Calidad: Evalúa la tipología de variables, conteo de nulos, valores únicos y porcentaje de registros incompletos.
- Depuración y Limpieza: Preserva los datos crudos en una copia, elimina columnas irrelevantes (coordenadas, afiliación) y filtra observaciones nulas en variables críticas de población y salud (dejando 13.096 filas).
- Carga e Integración en SQL (SQLite): Crea una base de datos SQLite relacional, convierte el DataFrame limpio en tabla y conecta una segunda tabla auxiliar de clasificaciones regionales de la ONU mediante códigos ISO.
- Consultas Analíticas SQL: Resuelve preguntas de negocio utilizando GROUP BY, HAVING, ORDER BY, LIMIT y JOIN relacionales.
- Inferencia Estadística: Divide la muestra por la mediana del PIB y aplica una prueba t de Welch (scipy.stats.ttest_ind) para evaluar la significación estadística en la esperanza de vida.
- Visualización Avanzada: Genera una matriz de correlación (heatmap), un gráfico de violín por regiones, y dos gráficos de dispersión con tamaño de burbuja y regresión lineal con cálculo de $r$ y $R^2$.

## ¿Qué aprendería una persona estudiante?

**Competencias técnicas**
- Carga de datos con Pandas.
- Limpieza y preparación de datos.
- Análisis exploratorio (EDA).
- Consultas SQL sobre datos reales.
- Visualización con Matplotlib y Seaborn.
- Estadística descriptiva e inferencial básica.
- Interpretación de correlaciones y pruebas de hipótesis.

**Competencias analíticas**
- Formular preguntas de negocio.
- Traducir datos en evidencia.
- Diferenciar correlación y causalidad.
- Comunicar resultados a perfiles no técnicos.

## Uso en una clase

### Duración sugerida

Cuatro horas distribuidas en dos sesiones.

### Sesión 1 (120 minutos)

**Actividad 1: Exploración**
- Revisar el dataset.
- Detectar problemas de calidad.

**Actividad 2: Limpieza**
- Debatir qué variables eliminar.
- Justificar decisiones.

**Actividad 3: SQL**
- Resolver preguntas de negocio mediante consultas.

### Sesión 2 (120 minutos)

**Actividad 4: Visualización**
- Interpretar gráficos.
- Comparar patrones regionales.

**Actividad 5: Storytelling**
- Redactar conclusiones ejecutivas.
- Diseñar una recomendación de política pública.

**Actividad final**
- Presentación grupal de resultados (5 minutos por equipo).

## Qué podría salir mal y cómo solucionarlo

### URL utilizadas no disponibles durante la ejecución del Notebook
**Solución**: Utilizar copia local CSV, y ejecutar el bloque de código creado por si se presenta está situación.

### Versiones incompatibles de librerías
**Solución**: Utilizar entorno reproducible con requirements.txt

## Adaptación a distintos niveles

### Nivel inicial
- Ejecutar el notebook completo.
- Interpretar resultados.
- Modificar parámetros sencillos.

### Nivel intermedio
- Crear nuevas consultas SQL.
- Diseñar visualizaciones alternativas.
- Añadir indicadores derivados.

### Nivel avanzado
- Aplicar modelos de regresión múltiple.
- Evaluar hipótesis adicionales.
- Comparar resultados con otros conjuntos de datos internacionales.
- Implementar dashboards en Power BI o Tableau.

### Adaptación a ritmos distintos
- Proporcionar notebook parcialmente resuelto para alumnado con menos experiencia.
- Ofrecer retos opcionales para alumnado avanzado.
- Trabajar en parejas mediante programación colaborativa.

## Uso de Inteligencia Artificial

Durante el desarrollo de este proyecto se utilizaron herramientas de Inteligencia Artificial como apoyo para la generación, revisión y mejora de código y documentación.

El código fue revisado, adaptado y ejecutado por el autor. La selección de los métodos de análisis, la interpretación de los resultados y las conclusiones son responsabilidad del autor.
