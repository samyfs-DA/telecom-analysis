# telecom-analysis

# Objetivo del Proyecto:
Evaluar el **comportamiento de los clientes** de una empresa de telecomunicaciones en Latinoamérica, ConnectaTel.

Trabajaremos con información registrada **hasta el año 2024**, lo cual permitirá analizar el comportamiento del negocio dentro de ese periodo.

# DataSet.
Para ello trabajarás con tres datasets:

**plans.csv** → información de los planes actuales (precio, minutos incluidos, GB incluidos, costo por extra) 
<br>
**users.csv** → información de los clientes (edad, ciudad, fecha de registro, plan, churn)
<br>
**usage.csv** → detalle del uso real de los servicios (llamadas y mensajes)

# Etapas del análisis.
Las etapas componen en **explorar, limpiar y analizar** estos datos para construir un **perfil estadístico** de los clientes, detectar **comportamientos atípicos** y crear segmentos de clientes.

Este análisis permite **identificar patrones de consumo, diseñar estrategias de retención y sugerir mejoras en los planes** ofrecidos por la empresa.

## 1. Cargar y Explorar
En esta etapa, validar que los archivos se carguen correctamente, conocer sus columnas y tipos de datos, y detectar posibles inconsistencias.

###1.1 Carga de datos y vista rápida
Tener los 3 datasets listos en memoria, entender su contenido y realizar una revisión preliminar.

###1.2 Exploración de la estructura de los datasets
Conocer la estructura de cada dataset, revisar cuántas filas y columnas tienen, identificar los tipos de datos de cada columna y detectar posibles inconsistencias o valores nulos antes de iniciar el análisis.

## 2. Identificación de problemas de calidad de datos

### 2.1 Revisión de valores nulos
Detectar la presencia y magnitud de valores faltantes para evaluar si afectan el análisis o requieren imputación/eliminación.

### 2.2 Detección de valores inválidos y sentinels
Identificar sentinels: valores que no deberían estar en el dataset.

### 2.3 Revisión y estandarización de fechas
Asegurar que las columnas de fecha estén correctamente formateadas y detectar años fuera de rango que indiquen errores de captura.

## 3. Limpieza básica de datos

### 3.1 Corregir sentinels y fechas imposibles
Aplicar reglas de limpieza para reemplazar valores sentinels y corregir fechas imposibles.

### 3.2 Corregir sentinels y fechas imposibles
Decidir qué hacer con los valores nulos según su proporción y relevancia.

## 4. Summary statistics de uso por usuario

### 4.1 Agrupación por comportamiento de uso
Resumir las variables clave de la tabla `usage` **por usuario**, creando métricas que representen su comportamiento real de uso histórico.

### 4.2 Resumen estadístico por usuario durante el 2024
Analizar las columnas numéricas y categóricas de los usuarios, para identificar rangos, valores extremos y distribución de los datos antes de continuar con el análisis.

## 5. Visualización de distribuciones (uso y clientes) y outliers

### 5.1 Visualización de Distribuciones
Entender visualmente cómo se comportan las variables clave tanto de **uso** como de **clientes**, observar si existen diferencias según el tipo de plan, y analizar la **forma de la distribución**.

### 5.2 Identificación de Outliers
Detectar valores extremos en las variables clave de **uso** y **clientes** que podrían afectar el análisis, y decidir si requieren limpieza o revisión adicional.

## 6. Segmentación de Clientes

### 6.1 Segmentación de Clientes Por Uso
Clasificar a cada usuario en un grupo de uso (Bajo uso, Uso medio, Alto uso) basándose en la cantidad de llamadas y mensajes registrados.

### 6.2 Segmentación de Clientes Por Edad
Clasificar a cada usuario en un grupo por **edad**.

### 6.3 Visualización de la Segmentación de Clientes
Visualizar la distribución de los usuarios según los grupos creados: **grupo_uso** y **grupo_edad**.

## 7. Insight Ejecutivo para Stakeholders
Traducir los hallazgos del análisis en conclusiones accionables para el negocio, enfocadas en segmentación, patrones de uso y oportunidades comerciales.

## 8. Ejecutar el Notebooc.
Adjunto se encuentra el notbook para que sea explorado en GoogleColab, para ejecutar:

¿Cómo ejecutar el notebook?
1. Da click en el logo de Open in Colab <img width="151" height="29" alt="image" src="https://github.com/user-attachments/assets/929c4364-5fa9-46d3-82ac-37ccb6d6ba5b" />
Los dataset ya estan en este repositorio y solo debes de ejecuta las celdas en orden desde la primera hasta la última (Runtime > Run all)
<img width="1007" height="121" alt="image" src="https://github.com/user-attachments/assets/df3a852e-59f6-4a8e-ad4c-71f715c63983" />
Autmotaicamente correra todos comandos hasta el último
