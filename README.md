# Impacto del estrés térmico ambiental y ciclos lunares en la incidencia cardiovascular aguda: Un análisis basado en telemetría satelital

**Autores:** Nayara López de Armentia, Aurora Real y Álex Sanz  
**Asignatura:** Fuentes de Datos Biomédicos y Web Semántica  
**Grado:** Ingeniería de la Salud (Universidad de Burgos)

## Introducción
La biometeorología humana estudia la interacción entre las variables atmosféricas y la salud de las personas a escala meteorológica. En este proyecto integramos datos ambientales obtenidos mediante telemetría satelital de la NASA (NASA/POWER), variables astronómicas (ciclos lunares) y registros clínicos oficiales del Instituto Nacional de Estadística (INE) para evaluar cómo las fluctuaciones bruscas de temperatura y los factores circadianos inciden en las enfermedades cardiovasculares agudas en España.

## Objetivos
1. **Evaluación del choque térmico:** Analizar la relación entre los episodios de frío extremo, los cambios bruscos de temperatura interdiarios ($\Delta T$) y la incidencia hospitalaria por eventos cardiovasculares.
2. **Contraste geográfico y climático:** Comparar el comportamiento epidemiológico entre cinco provincias españolas con perfiles climáticos opuestos: **Burgos** (continental frío), **Madrid** (continental mesetario), **Sevilla** (mediterráneo cálido), **A Coruña** (oceánico húmedo) y **Las Palmas** (subtropical estable).
3. **Exploración de variables cronobiológicas:** Incorporar el cálculo algorítmico de las **fases lunares** mediante el paquete `lunar` de R para evaluar posibles correlaciones o efectos confusores junto al estrés térmico.

## Estructura del repositorio
Este proyecto sigue un flujo de trabajo reproducible en RStudio y se organiza de la siguiente manera:
* `INPUT/DATA/`: Contiene las bases de datos originales en crudo:
  * `infartos_españa.csv`: Registro de morbilidad hospitalaria extraído del INE.
  * `temperaturas_*.json`: Series diarias de temperatura media (`T2M`) y mínima (`T2M_MIN`) en formato GeoJSON descargadas de NASA/POWER para las cinco ubicaciones de estudio.
* `OUTPUT/`: Directorio destinado a almacenar las tablas procesadas, gráficas (`ggplot2`) y resultados exportados.
* `Seminario_NASA_Corazon.Rproj`: Archivo de configuración del proyecto en RStudio para garantizar rutas relativas reproducibles.
* `Seminario_NASA.Rmd`: Documento principal en RMarkdown que integra la narrativa científica, el procesamiento con `tidyverse` (`dplyr`, `readr`), el parseo de datos semiestructurados (`jsonlite`), el cálculo lunar (`lunar`) y las tablas interactivas (`DT`).