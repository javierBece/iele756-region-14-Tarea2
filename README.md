# iele756-region-14-Tarea2
# Tarea 2: Health Landscape -- ENO + GRD 🏥📊

**Integrantes:** Javier Becerra Muñoz y Jose Pino Muñoz  
**Asignatura:** Preparación y Análisis de Datos  
**Fecha:** Abril 2026

---

## 📌 Descripción del Proyecto
Este repositorio contiene la **Tarea 2**, cuyo objetivo es construir un perfil de salud poblacional para las comunas asignadas (**La Granja, Macul y San Ramón** en la Región Metropolitana, Chile). 

El análisis integra dos fuentes de datos de salud pública para complementar el perfil demográfico construido en la Tarea 1:
1. **ENO (Enfermedades de Notificación Obligatoria):** Datos de vigilancia epidemiológica (2007-2024).
2. **GRD (Grupos Relacionados de Diagnóstico):** Registros de egresos hospitalarios (2022-2024).

El proyecto abarca desde la limpieza de variables categóricas complejas y el cruce de datos demográficos, hasta el cálculo de tasas poblacionales y la creación de visualizaciones geoespaciales (Choropleth).

---

## 📂 Estructura del Repositorio

- `Tarea2.ipynb`: Jupyter Notebook principal con todo el código, análisis, visualizaciones (gráficos y mapas) y discusiones metodológicas.
- `output/`: Directorio que contiene las tablas resumen generadas a nivel comunal, listas para ser utilizadas en futuras fases del proyecto.
  - `tarea2_eno_summary.csv`
  - `tarea2_grd_summary.csv`
- `materials/carto/`: (No incluido en el repo por tamaño) Shapefiles utilizados para la visualización espacial (`comunas.shp`).

*(Nota: Los archivos de datos originales (ENO y GRD) no se incluyen en este repositorio debido a su tamaño y por razones de privacidad de datos).*

---

## 🛠️ Tecnologías y Librerías Utilizadas
El proyecto está desarrollado en **Python 3** y requiere las siguientes librerías:
- `pandas` (Manipulación de datos)
- `matplotlib` y `seaborn` (Visualización de datos)
- `geopandas` (Análisis y visualización de datos espaciales)
- `fiona` / `pyogrio` (Motores de lectura para Shapefiles)

---

## ⚠️ Notas Metodológicas Importantes
1. **Anonimización ENO:** Aproximadamente el 45% de los registros en la base de datos ENO original tienen la comuna de residencia anonimizada (`*****`). Por lo tanto, los conteos y tasas calculadas representan una subestimación (el límite inferior) de la realidad.
2. **Nacionalidad Desconocida:** La categoría "Desconocido" en la variable nacionalidad de ENO representa una porción significativa de los datos y fue excluida para el cálculo de tasas y proporciones específicas por nacionalidad, reportando explícitamente el porcentaje de datos faltantes en la tabla resumen.
3. **Mediana vs Promedio:** Para el análisis de días de estadía (Length of Stay - LOS), se privilegió el uso de la mediana debido a la presencia de valores atípicos (estadías prolongadas) que sesgan la media aritmética.

---

## 🚀 Cómo ejecutar este proyecto
1. Clonar el repositorio.
2. Asegurar que los archivos de la Tarea 1 (`tarea1_comuna_summary.csv`) estén accesibles en la ruta relativa especificada en el notebook.
3. Instalar dependencias espaciales (En Windows, si hay errores con GDAL, se recomienda usar el entorno Conda o forzar la instalación con `!pip install --force-reinstall pyogrio fiona`).
4. Ejecutar `Tarea2.ipynb` secuencialmente.
