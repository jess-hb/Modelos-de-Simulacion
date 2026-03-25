# Modelos de Simulación - Actuaría
Este repositorio contiene mis códigos y tareas de la materia de Modelos de Simulación en la BUAP.

## Contenido
* **PROYECTOS.Rproj**: Archivo de proyecto de RStudio.
* **PROYECTO DISTRIBUCION**
* **1. evaluador_probabilistico(datos, distribuciones)**
Es el motor de cálculo del sistema. Su función es realizar un ajuste por Máxima Verosimilitud (MLE) para múltiples familias de distribuciones simultáneamente.

Lo que hace: Toma una muestra de datos y la "prueba" contra una lista de distribuciones (Normal, Poisson, Gamma, etc.).

Valor Agregado: Devuelve una tabla comparativa con los parámetros estimados y métricas de bondad de ajuste, ahorrando el trabajo de ajustar cada modelo por separado.

* **2. super_decision(resultado_evaluador)**
Es el algoritmo de lógica de decisión. No solo elige una distribución al azar, sino que aplica criterios estadísticos rigurosos.

Criterio de Selección: Utiliza el AIC (Akaike Information Criterion) para encontrar el modelo con mejor equilibrio entre ajuste y simplicidad.

Filtro de Validación: Valida los resultados mediante la prueba de Kolmogorov-Smirnov, descartando automáticamente cualquier modelo donde el p-value<0.05, asegurando que la distribución elegida sea estadísticamente significativa.

* **3. graficar_ajustes_pro(resultado_evaluador, datos)**
Es la herramienta de visualización híbrida. Transforma los datos abstractos en evidencia visual clara.

Naturaleza Dual: Identifica automáticamente si la distribución es Discreta (dibujando puntos de masa de probabilidad) o Continua (dibujando curvas de densidad suavizadas).

Comparativa Visual: Superpone la curva teórica del modelo "ganador" sobre el histograma de los datos reales, permitiendo identificar visualmente sesgos o colas pesadas en la muestra.

