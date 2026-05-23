# Diplomatura-en-IA-Universidad-de-Palermo
# Análisis Exploratorio de Datos (EDA) - Planta de Flotación (Proceso Minero)

**Universidad de Palermo** -
**Autor:** Cocha Jorge

---

## 📌 Contexto del Proyecto
Este repositorio contiene el Trabajo Práctico de Análisis Exploratorio de Datos (EDA). El objetivo del proyecto es analizar las variables operativas y de control de una planta de flotación de mineral de hierro, interpretando el comportamiento de los lazos automáticos y su impacto en la calidad del producto final. 

Los datos provienen de lecturas reales de sensores e instrumentos (flujos, pH, densidades) tomadas a intervalos regulares, emulando un entorno SCADA industrial continuo.

## 📊 Sobre el Dataset
* **Fuente:** Kaggle (Quality Prediction in a Mining Process).
* **Volumen original:** +730,000 registros (se aplicó un muestreo aleatorio de 100,000 filas para optimización de recursos).
* **Variables:** 24 columnas numéricas originales, ampliadas con variables categóricas derivadas (`Turno` y `Calidad_Silica`).

## 🎯 Hipótesis Planteadas
Durante el análisis, se plantearon las siguientes preguntas enfocadas en el control del proceso:
1. **Factor Humano:** ¿Existe una mayor variabilidad en las variables de control (pH de la pulpa, flujo de aire) durante el Turno Noche (20:00 a 08:00) frente al Turno Día (08:00 a 20:00), sugiriendo diferencias en la intervención manual de los operadores?
2. **Rendimiento Operativo:** ¿La planta logra mantener una calidad de mineral estable independientemente del turno?
3. **Control de Reactivos:** ¿El aumento del flujo de reactivo (Amina) tiene una correlación lineal directa con la reducción del porcentaje de impureza (Sílice)?
4. **Comprobación Física:** ¿Se puede verificar matemáticamente la correlación negativa entre el concentrado de hierro y el de sílice a la salida de las columnas?

## 📈 Conclusiones Principales
Tras la limpieza de datos (chequeo de nulos, duplicados y normalización) y la evaluación visual, se concluye:

* **Estabilidad Operativa:** Contrario a la hipótesis inicial, los gráficos de cajas (*boxplots*) demuestran que el proceso es sumamente estable en ambos turnos, promediando un ~65% de pureza de hierro. El sistema de control absorbe bien las transiciones operativas.
* **Alta Eficiencia:** El 74.7% de la producción analizada califica como mineral de "Alta Pureza" (Sílice < 3.0%).
* **Multivariabilidad:** No existe una correlación directa simple entre inyectar más Amina y reducir la impureza. Esto confirma que la calidad final depende del equilibrio multivariable de todo el circuito de flotación.
* **Correlación Validada:** Los gráficos de dispersión (*scatterplots*) comprueban perfectamente la rampa de correlación negativa entre el Hierro y la Sílice, validando el principio físico de separación de la planta.

## 🛠️ Herramientas Utilizadas
* **Lenguaje:** Python 3
* **Entorno:** Google Colab / Jupyter Notebook
* **Librerías:** Pandas (Manipulación de datos), Matplotlib & Seaborn (Visualización)
* **Asistente de IA:** Google Gemini (Soporte en generación de sintaxis, debugging de código y formateo de visualizaciones).
* ---
**Nota sobre el uso de herramientas de asistencia:**
Para la optimización del código en este Trabajo Práctico, se utilizó el modelo de inteligencia artificial Gemini (Google). Su aplicación se restringió estrictamente al *debugging* de errores en Colab, la generación de sintaxis para las librerías de visualización y el formato del documento, manteniendo la selección de variables, la definición de hipótesis y el análisis crítico del proceso industrial bajo la autoría e interpretación directa del estudiante.
