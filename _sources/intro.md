#  Introducción

##  Objetivo general

Este proyecto tiene como propósito desarrollar un sistema de predicción multisalida para el mercado de Bitcoin, abordando dos tareas complementarias:

1. **Predicción del precio de cierre diario** en horizontes de corto plazo.
2. **Estimación de la volatilidad futura del precio**, como indicador de riesgo.

Ambos modelos se construyen exclusivamente a partir del histórico temporal de precios de cierre (`Close`), sin incorporar variables externas. Esto permite evaluar el poder predictivo de las transformaciones internas del propio activo, manteniendo un enfoque reproducible y realista.

---

##  Enfoque metodológico

La estrategia se basa en:

- Aplicación de **ingeniería de retardos (lags)** y medias móviles como variables explicativas.
- **Validación temporal** mediante particiones secuenciales (`TimeSeriesSplit`).
- Entrenamiento de **redes neuronales MLP multisalida**, adaptadas a series temporales.
- **Análisis riguroso de residuos**, incluyendo pruebas de dependencia no lineal (BDS test).
- Preparación del modelo para su eventual **despliegue en un entorno MLOps** (API, contenedor, CI/CD).

---

##  Flujo de trabajo

1. Exploración y cálculo de la **volatilidad histórica**.
2. Generación de features temporales derivados de `Close`.
3. Separación de conjuntos de entrenamiento para cada tarea (precio y volatilidad).
4. Entrenamiento y evaluación de modelos independientes.
5. Validación con métricas específicas por tipo de salida.
6. Documentación reproducible y despliegue técnico.

---

##  Contexto financiero

El mercado de Bitcoin se caracteriza por su **alta volatilidad**, lo que representa tanto una oportunidad como un desafío para traders, gestores de portafolio e investigadores financieros.

Si bien la predicción del precio ha sido históricamente el foco de numerosos modelos, **anticipar la volatilidad** ofrece una ventaja estratégica más robusta en aplicaciones como:

- Trading algorítmico  
- Asignación dinámica de portafolios  
- Estrategias de cobertura  
- Estimación de riesgos extremos  

En este sentido, el forecasting de volatilidad —cuando se aborda con **rigor técnico**, **realismo** y **reproducibilidad**— se convierte en una herramienta esencial dentro del análisis cuantitativo moderno aplicado a mercados de criptomonedas.



```{tableofcontents}
```
