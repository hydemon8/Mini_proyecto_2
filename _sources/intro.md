#  Predicción de Volatilidad de Bitcoin con Redes Neuronales (MLP)

### Un análisis de Deep Learning para pronosticar la volatilidad diaria de BTC

Este notebook documenta el proceso de **análisis, entrenamiento y validación** de un modelo de `Deep Learning` para predecir la volatilidad del precio de Bitcoin. El objetivo es construir un sistema robusto basado únicamente en el historial de precios, implementando buenas prácticas para el manejo de series temporales.

---

##  Contexto y Motivación del Proyecto

El mercado de Bitcoin se caracteriza por una **volatilidad excepcionalmente alta**, lo que representa tanto un riesgo como una oportunidad. Mientras que predecir el precio exacto es una tarea notoriamente difícil, pronosticar la **magnitud de sus variaciones (la volatilidad)** es un enfoque más estable y fundamental en el análisis cuantitativo.

Anticipar la volatilidad es clave para:
* La gestión de riesgo en portafolios.
* El desarrollo de estrategias de trading algorítmico.
* La cobertura (`hedging`) contra movimientos de mercado adversos.

---

##  Objetivos del Notebook

Este trabajo implementa un pipeline de modelado completo y reproducible para:

1.  **Analizar** el comportamiento del precio de cierre diario de BTC.
2.  **Calcular** la volatilidad histórica a partir de los retornos logarítmicos.
3.  **Entrenar** un modelo `MLPRegressor` multi-salida para predecir 7 horizontes de volatilidad futuros.
4.  **Validar** el modelo de forma robusta usando validación cruzada para series temporales (`TimeSeriesSplit`) para evitar el *data leakage*.
5.  **Diagnosticar** los residuos del modelo con pruebas estadísticas (como el test BDS) para asegurar que no queda información predecible sin capturar.

**Dataset Utilizado:** Histórico de precios diarios BTC/USD (2018–2025) de Binance.

---

##  Enfoque del Modelado

La estrategia se centra en un modelo **MLP (Perceptrón Multicapa) multi-salida**, que aprende a predecir simultáneamente la volatilidad para los próximos 7, 14, 21 y 28 días.

Como features de entrada, se utiliza la **ingeniería de retardos (lags)**, es decir, se alimenta al modelo con los valores de volatilidad de los días anteriores para que aprenda los patrones temporales. Se experimenta con distintas ventanas de lags (7, 14, 21 y 28 días) para encontrar el historial óptimo.

---

##  Resultados Principales

Tras entrenar y evaluar los cuatro modelos, el **modelo que utiliza un lag de 7 días** demostró el mejor rendimiento general en los datos de prueba, alcanzando un **RMSE promedio de 0.2978**.

A continuación, se muestra un ejemplo de su capacidad predictiva en uno de los folds de validación:

![Lag 7 mejor fold 2](img/serie_temporal_lag7_Mejor_Fold_Fold_2.png)


---

## 🛠️ Stack Tecnológico Utilizado

* **Análisis y Modelado:** Python, Pandas, NumPy, Scikit-learn
* **Visualización:** Matplotlib, Seaborn
* **Entorno:** Jupyter Notebook


```{tableofcontents}
```
