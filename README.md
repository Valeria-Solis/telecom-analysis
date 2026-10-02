# telecom-analysis
Análisis de uso y segmentación de clientes de telecom.

## 🎯 Objetivo del proyecto

Analizar el comportamiento de uso de los clientes de ConnectaTel mediante información sobre usuarios, planes contratados y registros de llamadas y mensajes.

El análisis busca identificar patrones de uso, valores atípicos y segmentos de clientes según su edad y nivel de utilización del servicio, con el propósito de generar información útil para el análisis comercial.

## 📂 Datasets utilizados

El proyecto utiliza tres datasets:

- `plans.csv`: información de los planes disponibles.
- `users_latam.csv`: información de los usuarios, incluyendo edad, ciudad, plan y fecha de registro.
- `usage.csv`: registros históricos de llamadas y mensajes.

## 🔎 Etapas del análisis

### 1. Exploración de los datos

- Carga de los datasets.
- Revisión de dimensiones y tipos de datos.
- Identificación de valores nulos.
- Exploración de variables numéricas y categóricas.

### 2. Limpieza de datos

- Identificación de valores inválidos y sentinels.
- Reemplazo del sentinel `-999` en `age`.
- Reemplazo del valor `?` en `city`.
- Conversión y revisión de fechas.
- Identificación de fechas fuera de rango.
- Análisis de valores nulos en `duration` y `length`.

### 3. Estadísticas de uso por usuario

Se construyó un perfil de uso por usuario con las siguientes métricas:

- Cantidad de mensajes.
- Cantidad de llamadas.
- Total de minutos de llamadas.

Estas métricas se integraron con la información de los usuarios para construir un perfil completo de comportamiento.

### 4. Visualización y análisis de distribuciones

Se utilizaron histogramas para analizar:

- Edad de los usuarios.
- Cantidad de mensajes.
- Cantidad de llamadas.
- Total de minutos de llamadas.

Las distribuciones también se compararon según el tipo de plan.

### 5. Identificación de outliers

Se utilizaron boxplots y el método del rango intercuartílico (IQR) para identificar valores extremos en las variables de uso.

Los valores atípicos fueron revisados para determinar si representaban posibles errores o comportamientos reales de usuarios con un nivel de uso elevado.

### 6. Segmentación de clientes

Los usuarios fueron segmentados según dos criterios:

**Por nivel de uso:**

- Bajo uso.
- Uso medio.
- Alto uso.

**Por edad:**

- Joven.
- Adulto.
- Adulto Mayor.

Finalmente, se analizaron las características y distribución de estos segmentos.

## 🛠️ Herramientas utilizadas

- Python
- Pandas
- NumPy
- Seaborn
- Matplotlib
- Jupyter Notebook
- GitHub

## ▶️ Cómo ejecutar el notebook

### Jupyter Notebook

1. Descargar o clonar este repositorio.
2. Obtener los datasets utilizados en el proyecto.
3. Colocar los archivos en la carpeta `/datasets/`.
4. Abrir el archivo `connectatel_analysis.ipynb`.
5. Ejecutar las celdas del notebook en orden.

### Google Colab

El notebook también puede abrirse en Google Colab para ejecutar el análisis.

Los datasets deben estar disponibles en la ruta `/datasets/` utilizada por el notebook.

## 🔁 Guía de reproducción

Para reproducir el análisis:

1. Obtener los tres datasets utilizados.
2. Colocarlos en la carpeta `/datasets/`.
3. Abrir `connectatel_analysis.ipynb`.
4. Ejecutar las celdas desde la exploración inicial hasta el análisis ejecutivo.
5. Revisar las tablas, visualizaciones y conclusiones generadas.

## 📁 Estructura del proyecto

```text
connectatel-analysis/
│
├── README.md
└── connectatel_analysis.ipynb
