# **Introducción**

##  *Objetivo*

Este proyecto tiene como propósito desarrollar un sistema de **predicción para el precio de cierre diario de Bitcoin**, utilizando exclusivamente su histórico temporal. 

La metodología se basa en la aplicación de **ingeniería de retardos (lags)**, validación temporal mediante **TimeSeriesSplit**, y el entrenamiento de una **red neuronal MLP (Multilayer Perceptron)** para modelar tanto el **precio** como la **volatilidad** del activo.


###  Flujo de trabajo

-  Medición y exploración de la **volatilidad histórica**.  
-  Generación de **ventanas temporales (lags)** como variables explicativas.  
-  Validación cruzada con **particiones temporales** (GroupKFold adaptado a series de tiempo).  
-  Evaluación con **métricas específicas para series temporales**.  
-  Análisis riguroso de **residuos**, incluyendo pruebas de dependencia no lineal.  
-  Preparación del modelo para su eventual **despliegue en un entorno MLOps**. 

###  Extensión del modelo

Además del precio, se propone construir un modelo robusto para **predecir la volatilidad futura del precio de BTC**, partiendo únicamente de los cierres diarios.  

Este enfoque permite abordar el problema desde una perspectiva de **riesgo y estabilidad del mercado**.

##  *Contexto*

El mercado de **Bitcoin** se distingue por su **alta volatilidad**, lo que representa tanto una **oportunidad** como un **desafío** para *traders*, gestores de riesgo e investigadores financieros.  

Si bien la **predicción del precio** ha sido históricamente el foco de numerosos modelos, **anticipar la volatilidad** ofrece una **ventaja estratégica** más robusta en aplicaciones como:

-  **Trading algorítmico**  
-  **Asignación dinámica de portafolios**  
-  **Estrategias de cobertura**  
-  **Estimación de riesgos extremos**  


En este sentido, el **forecasting de volatilidad** —cuando se aborda con **rigor técnico**, **realismo** y **reproducibilidad**— se convierte en una tarea esencial dentro del **análisis cuantitativo moderno** aplicado a mercados de criptomonedas.


```{tableofcontents}
```
