# II. Metodología y resultados obtenidos

## 2.1. Preparación de datos

El análisis se realizó sobre 2,517 registros de pacientes con enfermedades crónicas. Se excluyeron observaciones con IMC fuera del rango 10-60 kg/m² y valores extremos superiores a 10,000. La muestra final presentó una media de IMC de 27.72 kg/m² (DS: 12.82) y edad promedio de 67.89 años (DS: 12.98).

## 2.2. Especificación de los modelos

Se plantearon dos modelos de regresión lineal estimados por Mínimos Cuadrados Ordinarios (OLS). El **Modelo 1** adopta un enfoque categórico mediante variables dummy para evaluar diferencias promedio del IMC entre grupos diagnósticos:

$$IMC_i = \beta_0 + \sum_{j=1}^{5} \beta_j D_{ij} + \varepsilon_i$$

donde $D_{ij}$ representa los cinco diagnósticos más frecuentes (Hipertensión, Diabetes, Hipotiroidismo, EPOC, Obesidad), usando "OTROS" como referencia.

El **Modelo 2** adopta un enfoque continuo para analizar la asociación entre edad e IMC:

$$IMC_i = \beta_0 + \beta_1 EDAD_i + \varepsilon_i$$

## 2.3. Resultados del Modelo 1

El Modelo 1 resultó estadísticamente significativo (F = 11.67; p < 0.001), aunque con baja capacidad explicativa (R² = 0.023). Los coeficientes estimados (Tabla 1) mostraron que únicamente dos grupos presentaron asociaciones significativas: "Obesidad, no especificada" (β = 8.60; p < 0.001) y EPOC (β = -4.89; p = 0.007). Los demás grupos no mostraron diferencias significativas respecto a la categoría de referencia.

### Tabla 1. Coeficientes del Modelo 1

| Variable | Coeficiente | Error Estándar | p-valor |
|----------|-------------|----------------|---------|
| Constante | 28.58 | 0.99 | < 0.001 |
| EPOC | -4.89 | 1.82 | 0.007 |
| Obesidad | 8.60 | 1.87 | < 0.001 |
| Hipertensión | -0.28 | 1.05 | 0.789 |
| Hipotiroidismo | -2.14 | 1.61 | 0.186 |

## 2.4. Resultados del Modelo 2

El Modelo 2 también resultó estadísticamente significativo (F = 30.92; p < 0.001), pero con capacidad explicativa aún menor (R² = 0.012). El coeficiente de edad fue negativo y significativo (β = -0.109; p < 0.001), indicando una reducción promedio de 1.1 puntos de IMC por cada 10 años adicionales de edad.

### Tabla 2. Coeficientes del Modelo 2

| Variable | Coeficiente | Error Estándar | p-valor |
|----------|-------------|----------------|---------|
| Constante | 35.11 | 1.35 | < 0.001 |
| EDAD | -0.109 | 0.020 | < 0.001 |

## 2.5. Comparación de modelos

La comparación (Tabla 3) muestra que ambos modelos son significativos (p < 0.001), pero con capacidad explicativa limitada. El Modelo 1 presenta un R² ligeramente superior (0.023 vs. 0.012), mientras que el Modelo 2 tiene un F-statistic mayor (30.92 vs. 11.67), reflejando que la significancia estadística no necesariamente implica mayor capacidad explicativa.

### Tabla 3. Comparación de modelos

| Métrica | Modelo 1 | Modelo 2 |
|---------|----------|----------|
| R² | 0.023 | 0.012 |
| F-statistic | 11.67 | 30.92 |
| p-valor | < 0.001 | < 0.001 |
| AIC | 19,940 | 19,960 |

Las discrepancias entre modelos evidencian que distintos enfoques conducen a interpretaciones complementarias: el Modelo 1 revela heterogeneidad entre grupos clínicos, mientras que el Modelo 2 sugiere una tendencia global decreciente del IMC con la edad. Sin embargo, ambos modelos confirman que el IMC es multifactorial y depende de factores no incluidos en el análisis.
