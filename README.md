# Caso Series de Tiempo

Este proyecto corresponde al **caso evaluativo de predicción de consumo de combustibles** utilizando diferentes enfoques de **modelado de series temporales**.  
El objetivo es comparar modelos estadísticos, de machine learning y redes neuronales para pronosticar el comportamiento de la variable **Gasóleos**, perteneciente al dataset energético `fuel_consumption`.

## Dataset

El dataset base proviene del paquete `skforecast` e incluye las siguientes variables mensuales desde 1969 hasta 2023:

| Variable | Descripción | Tipo |
|-----------|--------------|------|
| **GLPs** | Gases licuados del petróleo (propano y butano). | Combustible doméstico / industrial |
| **Gasolinas** | Gasolina automotriz. | Transporte liviano |
| **Querosenos** | Queroseno (jet fuel). | Aviación / calefacción |
| **Gasoleos** | Gasóleo o diésel. | Transporte pesado / calefacción |
| **Fueloleos** | Fuelóleos residuales. | Uso industrial / generación eléctrica |

La variable objetivo del análisis es **`Gasoleos`**.

## Modelos implementados

| Tipo | Modelo |
|------|---------|
| **Estadístico** | SARIMAX (2,1,1)×(8,1,1)\_12 | 
| **Regresión clásica** | Regresión Lineal | 
| **Machine Learning** | Árbol de Decisión | 
| | Árbol de Decisión con Grid Search | 
| | Random Forest | 
| **Deep Learning** | RNN (SimpleRNN) | 

## Resultados

| Modelo | MAPE |
|---------|------|
| SARIMAX | **8%** |
| Regresión Lineal | 21% |
| Árbol de Decisión | 14% |
| Árbol de Decisión (Grid Search) | 11% |
| Random Forest | 12% |
| **RNN** | **4%** |

> El modelo **RNN** obtuvo el menor error porcentual (4%), mostrando gran capacidad para capturar patrones no lineales y estacionales.  
> El modelo **SARIMAX** también presentó un excelente desempeño (8%), lo que valida la fuerza del enfoque clásico cuando la estacionalidad es bien definida.
