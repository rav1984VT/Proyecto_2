Proyecto 2: Análisis Inicial y Selección de Problema

- Descripción

El presente proyecto tiene como objetivo realizar un Análisis Exploratorio de Datos (EDA) inicial sobre cuatro conjuntos de datos distintos. A partir del diagnóstico, se selecciona un problema específico de Machine Learning, justificando la elección de la técnica basada en árboles para resolverlo.

- Conjuntos de Datos Analizados

    - faultdata-new.csv: Datos eléctricos de un generador eólico. Problema natural de clasificación de fallos.

    - global-data-on-sustainable-energy.csv: Datos panel (país-año) sobre sostenibilidad, economía y medio ambiente.

    - household_power_consumption.csv: Series temporales (minuto a minuto) del consumo eléctrico doméstico.

    - powerconsumption.csv: Series temporales que relacionan el clima con el consumo energético por zonas.

- Resumen del EDA Inicial

    - faultdata-new: Datos numéricos limpios. El desafío principal son las escalas dispares de las señales eléctricas.

    - global-data-on-sustainable-energy: Alto volumen de valores nulos (especialmente en finanzas de países en desarrollo). Alta multicolinealidad entre variables de generación eléctrica. Distribuciones muy sesgadas.

    - household_power_consumption: Requiere intensa limpieza de strings (? como nulos) y parseo de fechas.

    - powerconsumption: Estructura limpia con distribuciones normales en variables climáticas y ciclicidad clara.

- Problema Seleccionado

Regresión de Emisiones de CO2 (Árboles de Regresión)

    - Dataset: global-data-on-sustainable-energy.csv

    - Variable Objetivo (Target): Value_co2_emissions_kt_by_country (Emisiones de CO2 en kilotones).

    - Tipo de Problema: Regresión.

- Justificación:

    - Alineación con la temática de Árboles: Aunque comúnmente se asocian a clasificación, los árboles de decisión son extremadamente potentes para regresión (ej. DecisionTreeRegressor, RandomForestRegressor).

    - Relaciones No Lineales: La relación entre el desarrollo económico (PIB per cápita) y las emisiones de CO2 no es lineal (suele seguir una curva ambiental de Kuznets). Los árboles capturan estas no linealidades de forma nativa sin necesidad de transformaciones polinómicas.

    - Robustez a Outliers y Escalas: El dataset tiene valores atípicos enormes (ej. China o EE.UU. vs. pequeños islandes) y escalas dispares (porcentajes vs. kilómetros cuadrados). Los árboles no requieren estandarización de datos y son robustos ante valores atípicos, a diferencia de la Regresión Lineal.

    - Manejo de Nulos: Algoritmos modernos de árboles (como XGBoost) pueden manejar valores faltantes (NaN) internamente sin necesidad de imputaciones complejas, vital en este dataset que tiene gran cantidad de datos faltantes.

 - Objetivo Específico: Predecir la cantidad exacta de emisiones de CO2 de un país en un año dado basándose en su perfil energético y económico.

Instrucciones para Ejecutar

1.- Clonar el repositorio.
2.- Ubicar los archivos .csv en la carpeta /datasets.
3. -Ejecutar los notebooks en la carpeta /EDA para el análisis individual.
4. -El notebook EDA_selected_dataset.ipynb contiene el análisis profundo del problema de regresión.
5.- Librerías requeridas: pandas, numpy, matplotlib, seaborn, scikit-learn.

Autores

Raúl Araya V.

Licencia

Uso académico exclusivo.
