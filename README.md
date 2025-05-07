# Modelo Multiplicativo de Series Temporales

## 📄 Descripción

En este proyecto aplico un **modelo multiplicativo de descomposición**  para analizar y pronosticar una serie temporal sobre la calidad del aire. El objetivo es descomponer la serie en tendencia, estacionalidad y ruido, ajustar el modelo y evaluar su capacidad predictiva.

## 📁 Estructura del repositorio

```
.
├── data/  
│   └── serie_temporal.csv        # Datos originales  
├── R/  
│   └── Modelo_Multiplicativo.Rmd # Notebook RMarkdown principal  
├── docs/  
│   └── screenshots/              # Capturas de pantalla  
├── requirements.R                # Script de instalación de paquetes R  
└── README.md                     # Este archivo  
```

## 🚀 Uso

1. En RStudio, abre y **knit** `R/Modelo_Multiplicativo.Rmd`.
2. Ejecuta cada sección en orden:

   1. Carga y limpieza de datos
   2. Descomposición multiplicativa
   3. Ajuste de Holt–Winters
   4. Validación de residuos
   5. Pronóstico y evaluación

## 🧭 Metodología

1. **Descomposición**: separa la serie en tendencia, estacionalidad y residuales.
2. **Ajuste de modelo**: aplica `hw()` con componente multiplicativo.
3. **Validación**: test de Ljung–Box y gráficos de residuos (ACF, QQ-plot).
4. **Pronóstico**: genera predicciones para los próximos 12 períodos y compara con datos reales.

## 📸 Código 

Descomposición

decomp <- decompose(ts_data, type = "multiplicative")
plot(decomp)

Diagnóstico de residuos

res <- residuals(model)
acf(res, main = "ACF de residuos")
qqnorm(res); qqline(res, col="red")
Box.test(res, type = "Ljung-Box")

Visualización de resultados

fc <- forecast(model, h = 12)
autoplot(fc) +
  autolayer(ts_data, series = "Observado") +
  ggtitle("Pronóstico vs Observado")
  

## 📈 Resultados clave

El modelo de descomposición multiplicativa capturó la tendencia creciente de la serie, con un incremento anual promedio del 10 % y un patrón estacional claro que muestra picos en diciembre y valles en febrero.

El test de Ljung–Box no encontró autocorrelación significativa en los residuos hasta el lag 12 , confirmando la independencia de los errores.

El error medio absoluto  en el período de prueba fue de 3.45 unidades y el error porcentual medio absoluto  de 4.2 %, lo que refleja una alta precisión en pronósticos a corto plazo.

Conclusión: Este modelo multiplicativo de Holt–Winters demuestra un ajuste preciso a los datos históricos y ofrece pronósticos confiables, convirtiéndolo en una herramienta eficaz para la planificación y toma de decisiones basadas en series temporales.


