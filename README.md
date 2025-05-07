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

## 🧭 Metodología
   1. Carga y limpieza de datos
   2. PCA
   3. Modelo de predicciones
   4. Validación de residuos
   5. Pronóstico y evaluación

## 📸 

<img width="751" alt="image" src="https://github.com/user-attachments/assets/0c8350fd-960f-4ce6-b7c2-30df46d3dd17" />

<img width="755" alt="image" src="https://github.com/user-attachments/assets/f84885f3-12f2-49e7-94af-10434a3a9455" />

  

## 📈 Resultados clave

El modelo Identifica los componentes principales y logra hacer buenas predicciones con precisión de hasta el **64%** de las particulas en el aire

Conclusión: Este modelo demuestra un ajuste preciso a los datos históricos y ofrece pronósticos confiables, convirtiéndolo en una herramienta eficaz para la planificación y toma de decisiones basadas en series temporales.


