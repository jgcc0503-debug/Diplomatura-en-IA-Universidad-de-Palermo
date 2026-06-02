# Diplomatura en IA - Universidad de Palermo
## Análisis Exploratorio de Datos (EDA) - Planta de Flotación (Proceso Minero)
**Autor:** Cocha Jorge

### 📌 Contexto del Proyecto
Este repositorio contiene el Trabajo Práctico de Análisis Exploratorio de Datos (EDA). El objetivo del proyecto es analizar las variables operativas y de control de una planta de flotación de mineral de hierro, interpretando el comportamiento de los lazos automáticos y evaluando la viabilidad de implementar modelos predictivos (Machine Learning) para la optimización en la dosificación de reactivos.

Los datos provienen de lecturas reales de sensores e instrumentos (flujos, pH, densidades) tomadas a intervalos regulares, emulando un entorno SCADA/Historiador industrial continuo.

### 📊 Sobre el Dataset
* **Fuente:** Kaggle (Quality Prediction in a Mining Process).
* **Volumen original:** +730.000 registros.
* **Procesamiento y Muestreo:** Se realizó una limpieza de duplicados generados por la adquisición de datos de los instrumentos y se aplicó un **muestreo estratificado**. Se extrajeron 50.000 filas por guardia operativa (Turno Día y Turno Noche) para asegurar un rigor estadístico del 50/50 y evitar sesgos de análisis.
* **Variables:** 24 columnas numéricas originales, ampliadas con variables categóricas derivadas de la temporalidad (`Turno`) y el rendimiento (`Calidad_Silica`).

### 🎯 Hipótesis Planteadas
Durante el análisis, se plantearon preguntas con un enfoque directo en la ingeniería de procesos:
1. **Mineralogía y "Efecto Espejo":** ¿Se puede verificar matemáticamente una correlación negativa perfecta entre la recuperación del hierro y el rechazo de sílice?
2. **Saturación de Reactivos (Justificación para ML):** ¿La relación entre la dosificación de químicos (Almidón/Amina) y la pureza es lineal, o existe un punto de saturación que justifique abandonar el control PID tradicional por un control avanzado predictivo?
3. **Estabilidad Operativa:** ¿El cambio de guardia (Turno Día vs. Noche) y las condiciones asociadas afectan la dispersión y calidad del producto final?
4. **Habilitación por pH:** ¿Actúa el pH de la pulpa estrictamente como una variable de acondicionamiento previa a la flotación?

### 📈 Conclusiones Principales
* **Correlación Validada (Efecto Espejo):** El Mapa de Calor de variables operativas demostró una fuerte correlación inversa (-0.80) entre el hierro y la sílice concentrada, confirmando matemáticamente la eficiencia de la separación física.
* **Régimen de Operación Fijo:** Mediante mapas de densidad (Hexbinplots), se visualizó que la planta opera en una "ventana" (setpoint) muy conservadora y restringida en cuanto al flujo de almidón y amina, demostrando que la respuesta de los reactivos no es lineal. Esto fundamenta la necesidad de algoritmos de Machine Learning para optimizar el consumo en tiempo real.
* **Estabilidad entre Turnos:** A pesar de las variaciones naturales del proceso, el diseño estratificado demostró mediante Boxplots que el control de planta absorbe las transiciones de guardia de manera excelente, manteniendo la pureza de hierro estable en ~65% tanto de día como de noche.
* **Alta Eficiencia Global:** El 74.7% de la producción analizada bajo este muestreo califica como mineral de "Alta Pureza" (Sílice < 3.0%).

### 🛠️ Herramientas Utilizadas
* **Lenguaje:** Python 3
* **Entorno:** Google Colab / Jupyter Notebook
* **Librerías:** Pandas (Manipulación y resampleo temporal), Matplotlib & Seaborn (Visualización avanzada, Hexbinplots, Heatmaps, Series Temporales de doble eje).
* **Asistente de IA:** Google Gemini. *Nota de autoría: Se utilizó IA como soporte sintáctico para el debugging de código en Colab y el formato de visualizaciones de alto volumen de datos. La selección de variables, limpieza de duplicados de instrumentación, planteamiento de hipótesis de proceso y conclusiones industriales son de autoría e interpretación directa del estudiante.*
