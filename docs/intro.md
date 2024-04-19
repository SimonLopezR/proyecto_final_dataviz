# Introducción

En el dinámico mundo de las inversiones, la capacidad de tomar decisiones informadas y estratégicas es fundamental para el éxito de cualquier empresa de compra de acciones. En este contexto, Global Securities Colombia se ha propuesto llevar a cabo un proyecto integral de analítica descriptiva y predictiva con el objetivo de potenciar su capacidad de análisis y mejorar sus decisiones de inversión.
Global Securities Colombia conoce a profundidad el funcionamiento de los productos de inversión y sus beneficios, sin embargo la llegada de un nuevo canal 100% digital para potenciar de manera inteligente la capacidad de comprar acciones por parte del inversionista, pone la empresa frente a la inevitable transformación de todos los productos financieros. 

Este informe final presenta los hallazgos y resultados obtenidos durante el desarrollo del proyecto, el cual se divide en dos partes fundamentales: analítica descriptiva (EDA) y analítica predictiva (modelado).

En la primera parte, se llevó a cabo un exhaustivo análisis exploratorio de datos con el fin de extraer insights significativos del conjunto inicial de datos. Este análisis no solo permitió identificar tendencias clave en el mercado de acciones, sino también proporcionó una visión profunda de los factores que influyen en el rendimiento de las empresas. Similar a un Business Intelligence (BI), este enfoque permitió a Global Securities Colombia obtener una comprensión más completa y contextualizada del entorno en el que opera, facilitando así la toma de decisiones fundamentadas.

En la segunda parte del proyecto, nos adentramos en el campo de la analítica predictiva, donde se quiere implementar un modelo predictivo para estimar la clasificación de si una empresa es favorable o no para comprar acciones. A través de técnicas avanzadas de aprendizaje automático y modelado predictivo, se propone construir un modelo robusto capaz de evaluar una amplia gama de variables independientes y generar predicciones precisas y confiables. Este modelo no solo proporciona a Global Securities Colombia una herramienta invaluable para evaluar el potencial de inversión de diferentes empresas, sino que también allana el camino para una toma de decisiones más ágil y eficaz.

En este caso de uso, nos enfrentamos al desafío de desarrollar un modelo de clasificación binaria utilizando métodos avanzados de aprendizaje automático, específicamente Support Vector Machines (SVM), Random Forest y Gradient Boosting.

Contamos con un conjunto de datos exhaustivo que abarca diversas variables financieras clave para varias empresas. El objetivo principal es construir un modelo predictivo que pueda discernir, basándose en estas variables independientes, si es favorable o no invertir en determinadas empresas. Para lograr este objetivo, nos proponemos utilizar técnicas de hiperparametrización y creación de pipelines automatizadas, con el fin de optimizar el rendimiento de nuestros modelos y agilizar el proceso de análisis predictivo.

<br>

## Objetivos

1) Realizar un análisis exploratorio de datos exhaustivo con el fin de identificar tendencias, patrones y relaciones significativas en el mercado de acciones, así como en los factores que influyen en el rendimiento de las empresas. Este análisis descriptivo permitirá extraer insights relevantes para la toma de decisiones informadas y estratégicas por parte de Global Securities Colombia

2) Implementar técnicas de Machine Learning para desarrollar un modelo
de clasificación, entre SVM, RandomForestClassifer y GradientBoostingClassifier,para determinar si cierta firma con determinadas variables financieras es
favorable para comprar acciones en ella o no con el fin de minimizar pérdidas e impulsar la
toma de deciones basada en datos para añadir valor al negocio


## Datos

Los datos usados en este caso de estudio provienen de un proyecto de aprendizaje de IA llamado "AI Learn to invest" del libro SaturdaysAI - Euskadi 1st edition. Se recopilaron más de 900 inversiones aleatorias con los datos de los últimos 10 años del mercado NYSE (The New York Stock Exchange). Los ratios financieros y la volatilidad fueron calculadas y agregaron al conjunto de datos de inversiones aleatorias.

Biblioteca de datos: En su totalidad, el conjunto de datos utilizados contiene estas características
<br>

| Columna   | Descripción |
|------------|--------|
| company | Acrónimo de la compañía |
| sector | Sector de la compañía |
| horizon (days) | Números de dias desde que se compra hasta que se vende |
| amount | Número de dólares invertidos |
| date_BUY_fix | Fecha de compra |
| date_SELL_fix | Fecha de venta |
| price_BUY | Precio de compra de la acción |
| price_SELL | Precio de venta de la acción |
| Volatility_Buy | Volatilidad al comprar |
| Volatility_sell | Volatilidad al vender |
| Sharpe Ratio | Sharpe Ratio |
| expected_return (yearly) | Retorno anual esperado en dólares |
| inflation | Inflación durante la variable horizon (days) |
| nominal_return | Retorno nominal |
| ESG_ranking | ESG_ranking |
| PE_ratio | PE_ratio |
| EPS_ratio | EPS_ratio |
| PS_ratio | PS_ratio |
| PB_ratio | PB_ratio |
| NetProfitMargin_ratio | Utilidad neta anual |
| current_ratio | Reporte de utilidad más reciente de la firma |
| roa_ratio | roa_ratio |
| roe_ratio | roe_ratio |
| investment | Categoría si es buena (1) inversión o mala (0) |

## Esquema de desarrollo

El desarrollo sigue la siguiente metodologia:
- Pre-procesamiento de datos: En esta parte del desarrollo se busca fabricar las pipeline de tratamientos de datos, con ellas se busca transformar los datos de la manera adecuada para poder alimentar y entrenar el modelo de una manera óptima, seleccionar las variables indicadas y para esquematizar las transformaciones de manera automatica

- Definición de Modelos: En este segmento se definiran los modelos de Machine Learning a utilizar, como XGBoostrap (XGB), asi como el tuneo de sus parametros para buscar cual de todos los modelos entrenados presenta mejor rendimiento

- Ajuste y evaluación de Modelos: Mediante las métricas de rendimiento para medir precisión de los modelos, se buscara dentro de los modelos ajustados con un conjunto de datos de entrenamiento el que presenta mejor rendimiento comparandolos con un conjunto
de datos de validación

- Predicción: Por ultimo, con el mejor modelo seleccionado, se establece una funcion para poder estimar la clasificación de una firma dada sus caracteristicas financieras, si es favorable o no

A continuacion se explica el desarrollo celda a celda con el fin de entender ampliamente lo desarrollado, empezando por la pagina del EDA y continuando con el modelado