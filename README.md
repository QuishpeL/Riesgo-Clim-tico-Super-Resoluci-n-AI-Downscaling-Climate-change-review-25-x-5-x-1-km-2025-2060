# Riesgo-Clim-tico-Super-Resoluci-n-AI-Downscaling-Climate-change-review-25-x-5-x-1-km-2025-2060
Análisis geoespacial avanzado que utiliza Machine Learning (Random Forest) en Google Earth Engine para evaluar el riesgo de amenazas climáticas extremas tormentas en Ecuador, implementando una técnica de Downscaling Estadístico Topográfico GMC 25km hasta 1km, integrando la física de la atmósfera, la orografía y la vulnerabilidad


1. Evolución Multiescalar (The Downscaling Journey)
El script permite visualizar en tiempo real cómo la Inteligencia Artificial "aprende" y refina los datos climáticos:
•	Nivel 1 (Macro - 25km): La visión cruda de los modelos globales (CMIP6). Útil para tendencias regionales.
•	Nivel 2 (Satelital - 5km): Ajuste estadístico basado en el "Lienzo CHIRPS". Ideal para comparaciones históricas.
•	Nivel 3 (Super-Resolución - 1km): La joya de la corona. La IA inyecta datos topográficos (SRTM: Elevación y Pendiente) para predecir cómo se comportará la lluvia en valles y montañas específicos.
2. Motor de Inteligencia Artificial
•	Algoritmo: Random Forest Regression (100 árboles).
•	Entrenamiento: El modelo se entrena encontrando patrones complejos entre la lluvia histórica real (CHIRPS), las variables climáticas globales y la geografía local.
•	Target: Lluvia_Max_Hist (Eventos extremos históricos).
3. Riesgo Integral (Fórmula Cúbica)
El riesgo no es solo lluvia. TORMENTASRC calcula el índice final usando la fórmula:
$$Riesgo = \sqrt[3]{Amenaza \times Vulnerabilidad \times Exposición}$$
•	Amenaza: Lluvia futura extrema proyectada a 1km.
•	Vulnerabilidad: Índice socioeconómico basado en el estudio de Fernández et al. (2015), categorizando cantones desde "Baja" (ej. Quito, Cuenca) hasta "Muy Alta" (ej. Aguarico, Olmedo).
•	Exposición: Capa satelital WorldCover + Ajuste manual interactivo.


Datos
•	Plataforma: Google Earth Engine (JavaScript API).
•	Modelo Climático: MPI-ESM1-2-HR (Max Planck Institute) | Escenario: SSP5-8.5 (Trayectoria de altas emisiones).
•	Datos Base:
o	NASA/GDDP-CMIP6: Proyecciones climáticas globales.
o	UCSB-CHG/CHIRPS/DAILY: Precipitación satelital histórica (Ancla a tierra).
o	USGS/SRTMGL1_003: Topografía digital para el downscaling.
o	ESA/WorldCover/v100: Mapa de cobertura terrestre para exposición.

<img width="660" height="81" alt="image" src="https://github.com/user-attachments/assets/c2b07806-e893-4989-91ac-39e24d299803" />


<img width="1915" height="883" alt="Captura de pantalla 2025-12-18 134616" src="https://github.com/user-attachments/assets/3138ffee-625f-4c63-b82b-9ecf534ef605" />



Referencias Científicas
1.	Vulnerabilidad: Fernández, M. A., Bucaram, S. J., & Rentería, W. (2015). Assessing local vulnerability to climate change in Ecuador. SpringerPlus. 
2.	Metodología: Downscaling estadístico mediante algoritmos de aprendizaje automático (Random Forest) aplicados a modelos de circulación general (GCM).






