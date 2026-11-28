# **ConnectaTel**

Empresa de Telecomunicaciones con operaciones en México y Colombia

## **Análisis de una empresa de telecomunicaciones**
<img width="48" height="48" src="https://img.icons8.com/clouds/100/python.png" alt="python" title="Python"/> <img width="42" height="42" src="https://img.icons8.com/color/48/pandas.png" alt="pandas" title="Pandas"/> <img width="42" height="42" src="https://img.icons8.com/color/48/numpy.png" alt="numpy" title="Numpy"/> <img width="42" height="42" src="https://img.icons8.com/color/48/matplotlib.png" alt="matplotlib" title="Matplotlib"/> <img width="42" height="42" src="https://raw.githubusercontent.com/gilbarbara/logos/refs/heads/main/logos/seaborn-icon.svg" alt="seaborn" title="Seaborn"/>

El objetivo de la empresa es identificar *patrones de uso*, detectar *comportamientos atípicos* y comprender *qué segmentos de clientes* muestran necesidades diferenciadas, con el fin de optimizar la oferta comercial y mejorar la experiencia del usuario.

# **Objetivo del Proyecto:**

Evaluar el **comportamiento de los clientes** de una empresa de telecomunicaciones en Latinoamérica, ConnectaTel.

Trabajaremos con información registrada **hasta el año 2024**, lo cual permitirá analizar el comportamiento del negocio dentro de ese periodo.

## **DataSet.**
Para ello se cuenta con tres datasets:

**plans.csv** → información de los planes actuales (precio, minutos incluidos, GB incluidos, costo por extra) 
<br>
**users.csv** → información de los clientes (edad, ciudad, fecha de registro, plan, churn)
<br>
**usage.csv** → detalle del uso real de los servicios (llamadas y mensajes)

## **Etapas del análisis.**

Las etapas componen en **explorar, limpiar y analizar** estos datos para construir un **perfil estadístico** de los clientes, detectar **comportamientos atípicos** y crear segmentos de clientes.

Este análisis permite **identificar patrones de consumo, diseñar estrategias de retención y sugerir mejoras en los planes** ofrecidos por la empresa.

### **1. Cargar y Explorar**

En esta etapa, validar que los archivos se carguen correctamente, conocer sus columnas y tipos de datos, y detectar posibles inconsistencias.

#### 1.1 Carga de datos y vista rápida

Tener los 3 datasets listos en memoria, entender su contenido y realizar una revisión preliminar.

#### 1.2 Exploración de la estructura de los datasets

Conocer la estructura de cada dataset, revisar cuántas filas y columnas tienen, identificar los tipos de datos de cada columna y detectar posibles inconsistencias o valores nulos antes de iniciar el análisis.

### **2. Identificación de problemas de calidad de datos**

#### 2.1 Revisión de valores nulos

Detectar la presencia y magnitud de valores faltantes para evaluar si afectan el análisis o requieren imputación/eliminación.

#### 2.2 Detección de valores inválidos y sentinels

Identificar sentinels: valores que no deberían estar en el dataset.

### 2.3 Revisión y estandarización de fechas

Asegurar que las columnas de fecha estén correctamente formateadas y detectar años fuera de rango que indiquen errores de captura.

### **3. Limpieza básica de datos**

#### 3.1 Corregir sentinels y fechas imposibles

Aplicar reglas de limpieza para reemplazar valores sentinels y corregir fechas imposibles.

#### 3.2 Corregir sentinels y fechas imposibles

Decidir qué hacer con los valores nulos según su proporción y relevancia.

### **4. Summary statistics de uso por usuario**

#### 4.1 Agrupación por comportamiento de uso

Resumir las variables clave de la tabla `usage` **por usuario**, creando métricas que representen su comportamiento real de uso histórico.

#### 4.2 Resumen estadístico por usuario durante el 2024

Analizar las columnas numéricas y categóricas de los usuarios, para identificar rangos, valores extremos y distribución de los datos antes de continuar con el análisis.

### **5. Visualización de distribuciones (uso y clientes) y outliers**

#### 5.1 Visualización de Distribuciones

Entender visualmente cómo se comportan las variables clave tanto de **uso** como de **clientes**, observar si existen diferencias según el tipo de plan, y analizar la **forma de la distribución**.

#### 5.2 Identificación de Outliers

Detectar valores extremos en las variables clave de **uso** y **clientes** que podrían afectar el análisis, y decidir si requieren limpieza o revisión adicional.

### **6. Segmentación de Clientes**

#### 6.1 Segmentación de Clientes Por Uso

Clasificar a cada usuario en un grupo de uso (Bajo uso, Uso medio, Alto uso) basándose en la cantidad de llamadas y mensajes registrados.

#### 6.2 Segmentación de Clientes Por Edad

Clasificar a cada usuario en un grupo por **edad**.

#### 6.3 Visualización de la Segmentación de Clientes

Visualizar la distribución de los usuarios según los grupos creados: **grupo_uso** y **grupo_edad**.

### **7. Insight Ejecutivo para Stakeholders**

Traducir los hallazgos del análisis en conclusiones accionables para el negocio, enfocadas en segmentación, patrones de uso y oportunidades comerciales.

### **8. Ejecutar el Notebook.**

Adjunto se encuentra el notebook: "Project_ConnetaTel.ipynb" para que sea explorado en Google Colab, para ejecutar:

¿Cómo ejecutar el notebook?
1. Da click en el logo de Open in Colab <a href="https://colab.research.google.com/github/samyfs-DA/telecom-analysis/blob/main/Project_ConnectaTel.ipynb">
<img width="151" height="29" alt="image" src="https://github.com/user-attachments/assets/929c4364-5fa9-46d3-82ac-37ccb6d6ba5b" /> </a>

Los datasets ya están en este repositorio y solo debes ejecutar las celdas en orden desde la primera hasta la última (Runtime > Run all).

<img width="689" height="103" alt="image" src="https://github.com/user-attachments/assets/b7f6352a-1906-487a-a05b-93deaa3e7eb6" />

Automaticamente correra todos comandos hasta el último.

# **🎯 Resumen Ejecutivo**

**⚠️ Problemas detectados en los datos**

* En los dataset de users se encontraron el mayor porcentaje de nulos o faltantes en `churn_date` con un 88%, el siguiente fue `city` con un 11%, mientras que en `usage` nos encontramos con faltantes nulos o faltantes engañosos en las columnas `duration` y `length` debido a que dependen de la columna type que indica el uso y se comprueba más adelante que son del tipo **MAR**, y por último la columna date donde se encontró con un 0.12%.
* Encontramos con sentiles en el dataset de *users* para la columna de `age`, lo cual se manejó con la mediana, así como en `city` donde el sentinel fue `"?"`, lo cual se cambió a **NaN**.
* Se observó que las fechas en ambos datasets se consideraron como `string`, no como datetime, por lo que se realizó el cambio y permitió que se realizara el filtro para el año que nos solicitaron revisar, que es **2024.**

**🔍 Segmentos por Edad**

* Entre todos los segmentos por Edad se utiliza mayormente el **Plan Básico**, encontrando que los Adultos son los que más lo utilizan.
+ El **Plan Premium** es el menos utilizado y entre ellos se mantiene la tendencia de los Adultos, que son los que más tienen contratado este tipo de plan.

**📊 Segmentos por Nivel de Uso**

* El segmento de Uso medio tiene la mayor cantidad de usuarios entre todos los grupos de edad que tiene el dataset, seguido por el de Bajo Uso.
* En el segmento de Alto Uso encontramos que los Adultos son los predominantes, sin embargo se debe tomar acción para que este le sea más atractivo para los Jovenes

➡️ Esto sugiere que durante el periodo analizado ningún usuario sobrepasó los **mensajes incluidos** en su plan; por otro lado, los usuarios activos con Plan Básico cuentan con excedentes en los **minutos incluidos**, dando un total de 14 usuarios, y se mantiene el nivel de Uso Medio, pero se observa que en este caso *Adulto Mayor* es el que más tiene este tipo de comportamiento, seguido por *Joven*.

**💡 Recomendaciones**

* Se recomienda crear un plan intermedio entre *Básico* y *Premium* para poder captar a clientes que tienen un excedente; conforme al análisis realizado, se determina que el excedente medio es de 39.94 minutos, lo que implica en la facturación aproximadamente USD 3.99; se podría considerar que este plan tenga un costo de *USD 18 y contemple 250 mensajes incluidos y 300 minutos.*
* En este análisis y conforme a la información brindada no se observa el comportamiento del uso de datos para así determinar si una mejor oferta en datos incluidos pueda captar a los jóvenes y con ello contar con mayor cobertura de mercado.

Tabla que apoya los resultados para los insights de segmento Edad <br>
<img width="271" height="128" alt="image" src="https://github.com/user-attachments/assets/c8f2ec02-bc75-4b64-9e4c-4eb68be52fa8" />

Tabla que apoya los resultados para los insignts de Segmento Uso <br>
<img width="289" height="153" alt="image" src="https://github.com/user-attachments/assets/391fd1fd-185a-437b-8c51-83acac97a625" />

Filtro para cant_minutos_llamada >= 100 y siguen activos <br>
<img width="946" height="565" alt="image" src="https://github.com/user-attachments/assets/9a37a324-a75e-4837-8930-6530d45194f2" />

Filtro para cant_minutos_llamada >= 100 & que son de plan Premium <br>
<img width="1065" height="314" alt="image" src="https://github.com/user-attachments/assets/34f39282-9f9a-41a1-b948-8d3ae3ecc4c3" />

Filtro para cant_minutos_llamada >= 100 & que son de plan Básico <br>
<img width="1125" height="381" alt="image" src="https://github.com/user-attachments/assets/e072d8e6-8035-4d50-8036-6b7891ba7ce3" />

Tabla concentrado <br>
<img width="228" height="204" alt="image" src="https://github.com/user-attachments/assets/62675d33-731b-4d29-b6d6-46dba58a45d5" />

Filtro para mostrar el excedente de minutos de los usuarios que usaron sus 100 minutos <br>
<img width="1112" height="364" alt="image" src="https://github.com/user-attachments/assets/df28adb6-14ae-4d94-9cb4-ed05b85c7723" />

Pago adicional considerando el cobro del excedente en USD $0.10 <br>
<img width="1154" height="555" alt="image" src="https://github.com/user-attachments/assets/d920c460-98a8-4bb4-a298-504a9feb171c" />

Comportamiento de los excedentes obtenidos. <br>
<img width="220" height="230" alt="image" src="https://github.com/user-attachments/assets/dbb84f94-f05d-43f3-ba5e-4356876f8a4a" />

