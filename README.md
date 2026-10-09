# telecom-analysis
# Análisis de clientes de ConnectaTel

## 🎯 Objetivo del proyecto

El objetivo de este proyecto es analizar el comportamiento de los clientes de **ConnectaTel**, una empresa de telecomunicaciones, a partir de información sobre sus características demográficas y su consumo de servicios.

El análisis busca identificar patrones de uso, segmentos de clientes y posibles oportunidades comerciales que permitan comprender mejor el comportamiento de los usuarios y apoyar la toma de decisiones.

---

## 📊 Datasets utilizados

Para realizar el análisis se utilizaron tres datasets:

### `plans.csv`

Contiene información sobre los planes ofrecidos por ConnectaTel, incluyendo:

* Nombre del plan.
* Mensajes incluidos.
* GB incluidos.
* Minutos incluidos.
* Precio mensual.
* Costo por GB adicional.
* Costo por mensaje adicional.
* Costo por minuto adicional.

### `users_latam.csv`

Contiene información de los usuarios, incluyendo:

* Identificador del usuario.
* Nombre y apellido.
* Edad.
* Ciudad.
* Fecha de registro.
* Plan contratado.
* Fecha de cancelación, cuando corresponde.

### `usage.csv`

Contiene información sobre el consumo de los usuarios:

* Identificador del registro.
* Identificador del usuario.
* Tipo de uso.
* Fecha.
* Duración de las llamadas.
* Cantidad de caracteres en los mensajes.

---

## 🔎 Etapas del análisis

El proyecto se desarrolló mediante las siguientes etapas:

### 1. Carga y exploración de los datos

Se cargaron los tres datasets utilizando `pandas` y se realizó una revisión inicial de su estructura, tipos de datos, dimensiones y valores faltantes.

### 2. Limpieza y preparación de los datos

Se identificaron y trataron diferentes problemas de calidad:

* Valores atípicos o sentinelas en la variable de edad.
* Valores faltantes y registros con `"?"` en la ciudad.
* Fechas fuera del periodo de análisis.
* Valores ausentes en las variables de consumo.
* Revisión de valores faltantes en la fecha de cancelación.

Los valores faltantes en `duration` y `length` se conservaron cuando correspondían al tipo de registro, debido a que representan valores estructurales: los mensajes no tienen duración de llamada y las llamadas no tienen longitud de mensaje.

### 3. Análisis exploratorio

Se analizaron las principales variables de comportamiento de los usuarios:

* Edad.
* Cantidad de mensajes.
* Cantidad de llamadas.
* Minutos de llamadas.

Se utilizaron estadísticas descriptivas, histogramas y diagramas de caja para identificar patrones de distribución y posibles valores extremos.

### 4. Identificación de valores atípicos

Se utilizó el método del **rango intercuartílico (IQR)** para identificar posibles valores atípicos en las variables de consumo.

Los valores extremos encontrados se conservaron cuando representaban comportamientos de consumo plausibles, ya que pueden ser útiles para identificar usuarios de alto consumo.

### 5. Segmentación de usuarios

Se construyeron segmentos de usuarios de acuerdo con:

* Grupo de edad.
* Nivel de uso de los servicios.

Esto permitió identificar grupos de bajo, medio y alto consumo y analizar sus principales características.

### 6. Análisis por plan

Se comparó el comportamiento de los usuarios de los planes **Básico** y **Premium**, considerando variables como mensajes, llamadas y minutos consumidos.

El análisis permitió evaluar si existían diferencias relevantes en los patrones de consumo entre ambos planes.

### 7. Conclusiones y recomendaciones

Finalmente, se integraron los principales hallazgos para identificar oportunidades comerciales, especialmente relacionadas con:

* La propuesta de valor del plan Premium.
* Los usuarios de alto consumo.
* Los usuarios de bajo consumo.
* La segmentación de clientes.
* El análisis futuro de cancelación de servicios.

---

## ▶️ Cómo ejecutar el notebook

El análisis se encuentra en un notebook de **Jupyter Notebook** y puede ejecutarse utilizando **Google Colab**.

Para abrirlo en Google Colab:

1. Descarga o abre el archivo `.ipynb` incluido en este repositorio.
2. Ingresa a [Google Colab](https://colab.research.google.com/).
3. Selecciona **Archivo → Abrir notebook**.
4. Selecciona la opción para subir el archivo `.ipynb`.
5. Carga también los datasets necesarios en la sesión de Colab.
6. Ejecuta las celdas del notebook en orden.

---

## 🔁 Guía de reproducción

Para reproducir el análisis:

1. Descargar o clonar este repositorio.
2. Abrir el notebook `S7_ConnectaTel_final_corregido.ipynb`.
3. Asegurarse de contar con los tres datasets:

   * `plans.csv`
   * `users_latam.csv`
   * `usage.csv`
4. Mantener los archivos en la ubicación esperada por el notebook o actualizar las rutas de lectura de los archivos.
5. Ejecutar las celdas en orden desde el inicio.
6. Revisar las tablas, visualizaciones y conclusiones generadas durante el análisis.

### Principales herramientas utilizadas

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **Jupyter Notebook / Google Colab**

---

## 📌 Resultado general

El análisis muestra que la mayor parte de los clientes presenta un nivel de uso medio, mientras que existe un grupo más pequeño de usuarios con un consumo elevado.

También se observa que los patrones de consumo de los usuarios de los planes Básico y Premium son relativamente similares, lo que representa una oportunidad para revisar la diferenciación de la propuesta de valor del plan Premium y desarrollar estrategias específicas para los distintos segmentos de usuarios.
