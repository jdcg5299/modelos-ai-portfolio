# 🤖 Industrial AI & Machine Learning Portfolio
### Soluciones de Inteligencia Artificial Aplicadas al Negocio, Real Estate y la Salud

Este repositorio compila mis proyectos de Machine Learning desarrollados en el marco de la **Especialización en Inteligencia Artificial (UAO)**. Como **Technical Product Owner**, cada modelo está enfocado bajo un marco ágil y de producto: identificando un dolor operativo o comercial, aplicando ingeniería de características y seleccionando el algoritmo idóneo basándose en el balance entre rendimiento matemático, mitigación de riesgos, estabilidad ante datos nuevos y explicabilidad.

---

## 📂 Casos de Estudio & Prototipos de IA

### 🔹 1. Valoración Inmobiliaria Inteligente mediante Modelos Multialgorítmicos (Real Estate Valuation)
* **Problema de Negocio:** Falta de herramientas automatizadas para estimar el precio justo de mercado de inmuebles por metro cuadrado, dependiendo de factores geográficos y de micro-entorno urbano.
* **Análisis de Producto (Descubrimiento del Valor):**
  * **El valor está en el tiempo:** El análisis exploratorio descubrió el *"Efecto Tobogán"*, donde el valor de una propiedad cae en picada tras superar los primeros 1,000 metros de distancia a la estación de metro más cercana.
  * **Efecto Micro-entorno:** El número de tiendas de conveniencia cercanas actúa como un multiplicador directo de plusvalía (las propiedades con más servicios se venden entre $2,367 USD/m² y $4,261 USD/m²).
* **Evaluación Comparativa de Modelos (Ciclo de Vida del MVP):**
  1. **Gradiente Descendente (Manual):** Logró converger numéricamente tras 2,414 iteraciones, pero hacia una solución subóptima. Explicaba únicamente el **14.7% de la variabilidad (R² ≈ 0.15)**, con un margen de error alto (RMSE ≈ 12.79).
  2. **Regresión Lineal OLS (Scikit-Learn):** Incrementó radicalmente el desempeño, logrando explicar el **58.3% de la variabilidad del mercado (R² ≈ 0.58)** y reduciendo el error promedio significativamente.
  3. **Regresión Ridge (Regularización L2 + GridSearchCV):** Se optimizó mediante la búsqueda del hiperparámetro `alpha` ideal (0.1). Obtuvo métricas idénticas al OLS (R² de 0.582, error MAPE de 18.9%).
* **Criterio de Decisión del PO (Conclusión):** Se seleccionó la **Regresión Lineal OLS / Ridge** para producción. Dado que el rendimiento fue idéntico, se concluye que el dataset no sufre de multicolinealidad severa o sobreajuste (*overfitting*), garantizando un modelo altamente estable, ligero y con un margen de error predecible del 19% en promedio.
* **Stack Técnico:** Python, Pandas, NumPy, Scikit-Learn (LinearRegression, Ridge, GridSearchCV), Seaborn, Matplotlib, Plotly, UCIMLRepo.
* [👉 Abrir Caso de Estudio Completo en Google Colab](https://colab.research.google.com/drive/1ZMCc6DZ2uXqm51ebvIQKCSC_NXuLZjWi) *(Nota: Recuerda verificar si tus códigos están unificados o en links separados)*

### 🔹 2. Analítica Predictiva para Diagnóstico Oncológico (Wisconsin Breast Cancer)
* **Problema de Negocio / Clínico:** Dificultad para agilizar y automatizar el diagnóstico de malignidad en masas mamarias sin perder precisión médica ni generar cajas negras algorítmicas que el personal de salud no pueda auditar.
* **Estrategia Funcional:** Ingeniería de características para reducir redundancias masivas en variables geométricas celulares (de 11 a 5 variables críticas), protegiendo al modelo del sobreentrenamiento.
* **Criterio de Producto y Gestión de Riesgo:** * Descarte de *Naive Bayes* por alto riesgo clínico (5 falsos negativos, Recall del 88% en tumores malignos).
  * Descarte de *KNN* por falta de interpretabilidad (caja negra geométrica).
  * **Selección Final:** *Regresión Logística* por su capacidad de **explicabilidad a través de coeficientes**, permitiendo al médico auditar qué variables influyeron en el diagnóstico.
* **Stack Técnico:** Python, Scikit-Learn (LogisticRegression, GaussianNB, KNeighborsClassifier), Pandas, NumPy.
* [👉 Abrir Caso de Estudio Completo en Google Colab](https://colab.research.google.com/drive/1ZMCc6DZ2uXqm51ebvIQKCSC_NXuLZjWi)

---

## ⚙️ Habilidades de Gestión de Producto en IA Demostradas
* **Selección de Algoritmos Basada en Criterio Comercial:** Capacidad para balancear la complejidad computacional, la estabilidad (evitar *overfitting*) y el riesgo operativo al elegir un modelo para producción.
* **Análisis de Datos Orientado al Valor:** Habilidad para traducir histogramas y matrices de correlación en insights de negocio claros (definición de precios promedio en USD, identificación de zonas de alta plusvalía).
* **Optimización de Procesos de Modelado:** Uso de técnicas avanzadas de normalización, escalado y sintonización de hiperparámetros (`GridSearchCV`) para extraer la máxima precisión de los datos disponibles.
