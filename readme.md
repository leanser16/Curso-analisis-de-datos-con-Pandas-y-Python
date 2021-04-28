# Curso de Manipulación y Análisis de Datos con Pandas y Python

Notas y Código del [Curso de Manipulación y Análisis de Datos con Pandas y Python de Platzi](https://platzi.com/cursos/pandas/)

- [Curso de Manipulación y Análisis de Datos con Pandas y Python](#curso-de-manipulación-y-análisis-de-datos-con-pandas-y-python)
  - [📚 Módulo 1. Comenzando con pandas](#-módulo-1-comenzando-con-pandas)
    - [Clase 2. Primeros pasos con Google Colab: configuración del entorno de trabajo](#clase-2-primeros-pasos-con-google-colab-configuración-del-entorno-de-trabajo)
    - [Clase 3. Series e Indexación y selección de datos](#clase-3-series-e-indexación-y-selección-de-datos)
      - [Algunos métodos útiles para filtrar datos](#algunos-métodos-útiles-para-filtrar-datos)
    - [Clase 4. De paneles de datos al DataFrame](#clase-4-de-paneles-de-datos-al-dataframe)
      - [Otros métodos útiles para analizar DataFrames](#otros-métodos-útiles-para-analizar-dataframes)
    - [Clase 5. Indexado y manejo de archivos CSV](#clase-5-indexado-y-manejo-de-archivos-csv)
    - [Clase 6. Cómo usar Pandas y Python para conectar con tu base de datos SQL](#clase-6-cómo-usar-pandas-y-python-para-conectar-con-tu-base-de-datos-sql)
      - [PostgreSQL](#postgresql)
      - [SQL Server](#sql-server)
      - [MySQL / Oracle / Otras](#mysql--oracle--otras)
      - [Conectarse a bases de Datos en la nube](#conectarse-a-bases-de-datos-en-la-nube)
    - [Clase 7. Ventajas y desventajas de los formatos de importar y guardado](#clase-7-ventajas-y-desventajas-de-los-formatos-de-importar-y-guardado)
  - [📚 Módulo 2. Funcionalidades básicas y esenciales de pandas](#-módulo-2-funcionalidades-básicas-y-esenciales-de-pandas)
    - [Clase 8. Formatos de lectura para cargar y guardar DataFrames](#clase-8-formatos-de-lectura-para-cargar-y-guardar-dataframes)
      - [Tamaño de Archivo](#tamaño-de-archivo)
      - [Tiempos de Carga y Lectura](#tiempos-de-carga-y-lectura)
      - [Consumo de memoria RAM](#consumo-de-memoria-ram)


## 📚 Módulo 1. Comenzando con pandas

### Clase 2. Primeros pasos con Google Colab: configuración del entorno de trabajo

[Notebook de la clase](https://github.com/bl00p1ng/Curso-analisis-de-datos-con-Pandas-y-Python/blob/main/primeros_pasos_con_colab.ipynb)

<a href="https://colab.research.google.com/github/bl00p1ng/Curso-analisis-de-datos-con-Pandas-y-Python/blob/main/primeros_pasos_con_colab.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>


### Clase 3. Series e Indexación y selección de datos

[Notebooks de la clase](https://github.com/bl00p1ng/Curso-analisis-de-datos-con-Pandas-y-Python/blob/main/series_indexacion_seleccion_de_datos.ipynb)

<a href="https://colab.research.google.com/github/bl00p1ng/Curso-analisis-de-datos-con-Pandas-y-Python/blob/main/series_indexacion_seleccion_de_datos.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

#### Algunos métodos útiles para filtrar datos

- `sr.isnull().any()` Regresa un booleano indicándonos si existe (TRUE) o no existe (FALSE) algún `nan`
- `sr[sr.notnull()]` Regresa los valores de la serie que **NO** son nulos.


### Clase 4. De paneles de datos al DataFrame

[Notebook de la Clase](https://github.com/bl00p1ng/Curso-analisis-de-datos-con-Pandas-y-Python/blob/main/dataframes.ipynb)

<a href="https://colab.research.google.com/github/bl00p1ng/Curso-analisis-de-datos-con-Pandas-y-Python/blob/main/dataframes.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a>

Un **Data Frame** es una estructura bidimensional en la que las columnas corresponden a varias que categorías de datos que pueden ser de tipo texto, numérico, lógico, etc.

_**Ejemplo:**_

![Ejemplo data frame](https://i.ibb.co/YPdbWt9/data-frame.png)

**Actualizar Pandas en Colab**

```bash
!pip install --upgrade pandas
```

La función query es muy útil pues aumenta la legibilidad del código a la hora de hacer consultas al DataFrame. 

_**Ejemplo:**_

Consulta **usando** `query()`
```python
df.query( 'edad >= 12 and pais == "mx" ')
```

Consulta **sin usar** `query()`
```python
df[(df['edad'] >= 12) & (df['pais'] == 'mx')]
```

Ambas muestran los mismos resultados pero el primero es mucho más legible que el segundo.

#### Otros métodos útiles para analizar DataFrames

- Conocer cuántos valores **iguales** hay en una columna:

  ```python
  df['Edad'].value_counts()
  ```

- Conocer cuántos valores **únicos** hay en una columna:

  ```python
  df['Edad'].unique()
  ```

- Obtener un resumen con la estructura de las variables y el tipo de datos que contienen:
  
  ```python
  df.info()
  ```

- Retorna un `summary()` del Data Set. Si se tienen variables numéricas el método va a retornar: mínimo. máximo, media, std, etc de las columnas numéricas.

  ```python
  df.describe()
  ```

- Cambiar el tipo de dato de las columnas:

  ```python
  df = df.astype({"Q1": float, "Q2": float})
  ```


### Clase 5. Indexado y manejo de archivos CSV

[Notebook de la clase](https://github.com/bl00p1ng/Curso-analisis-de-datos-con-Pandas-y-Python/blob/main/save_and_load.ipynb)

<a href="https://colab.research.google.com/github/bl00p1ng/Curso-analisis-de-datos-con-Pandas-y-Python/blob/main/save_and_load.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a>

[Información IPython Magic Commands](https://platzi.com/tutoriales/1794-pandas/6960-ipython-magics-commands/)


### Clase 6. Cómo usar Pandas y Python para conectar con tu base de datos SQL

Pandas cuenta con una funcionalidad que facilita el acceso a tus bases de datos tipo SQL

#### PostgreSQL

Instalar la librería **psycopg2** en caso de que no este instalada con `!pip install psycopg2`.

Luego se importa la librería:

```python
import pandas as pd
import psycopg2
```

Luego se crea la conexión a la DB:

```python
conn_sql = psycopg2.connect(user = "user_name",
  password = "password",
  host = "xxx.xxx.xxx.xxx",
  port = "5432",
  database = "postgres_db_name")
```

Después se puede definir la query en SQL:

```python
query_sql = '''
select *
from table_name
limit 10
'''
```

Por último se crea el DataFrame en base a la query:

```python
df = pd.read_sql(query_sql, sql_conn)
df.head(5)
```

#### SQL Server

Instalar la librería **pyodbc** en caso de que no este instalada con `!pip install pyodbc`.

Importar las librerías:

```python
import pandas as pd
import pyodbc
```

Crear la conexión a la DB:

```python
river = '{SQL Server}'
server_name = 'server_name'
db_name = 'database_name'
user = 'user'
password = 'password'
sql_conn = pyodbc.connect('''
DRIVER={};SERVER={};DATABASE={};UID={};PWD={};
Trusted_Connection=yes
'''.format(driver, server_name, db_name, user, password))
```

Si se tiene DSN:

```python
dsn = 'odbc_datasource_name'
sql_conn = pyodbc.connect('''
DSN={};UID={};PWD={};Trusted_Connection=yes;
'''.format(dsn, user, password))
Seguido simplemente definimos nuestra query en SQL:	
query_sql = 'select * from table_name limit 10'
```

Se crea el DataFrame:

```python
df = pd.read_sql(query_sql, sql_conn)
df.head(5)
```

#### MySQL / Oracle / Otras

Instalar la librería **sqlalchemy** en caso de que no este instalada con `!pip install sqlalchemy`.

Cargar las librerías:

```python
import pandas as pd
import sqlalchemy as sql
Escogemos nuestra base de datos, Oracle, MySql o la de tu preferencia:
database_type = 'mysql'
database_type = 'oracle'
```

Se crea la conexión a la DB:

```python
user = 'user_name'
password = 'password'
host = 'xxx.xxx.xxx.xxx:port'
database = 'database_name'

conn_string = '{}://{}:{}@{}/{}'.format(
database_type, user, password, host, database)

sql_conn = sql.create_engine(conn_string)
```

Definir query en SQL:

```python
query_sql = '''
select *
from table_name
limit 10
'''
```

Crear DataFrame:

```python
df = pd.read_sql(query_sql, sql_conn)
df.head(5)
```

**ℹ Nota:** La librería sqlalchemy también soporta PostgreSQL y otras fuentes de datos.


#### Conectarse a bases de Datos en la nube

**MySQL**

Instalar **pymysql** con `!pip install pymysql`, después se importa la librería:

```python
import pymysql
```

Luego se crea la conexión a la DB:

```python
conn = pymysql.connect(host=‘YOUR_IP_HOST’, port=DB_PORT, user=‘YOUR_USER’, passwd=‘YOUR_PASSWD’, db=‘YOUR_DB_NAME’)
```

Después se hace la query a la DB:

```python
cursor = conn.cursor()
query = (“select * from YOUR_TABLE_NAME”)
cursor.execute(query)
```

**Google Big Query**

Es una práctica recomendable subir los DataFrames a servidores en la nube como por ejemplo BigQuery.

```python
import pandas as pd
from pandas.io import gbq
```

Traer la DB:

```python
dataset = pd.read_csv('base_datos.csv')
```

Luego se le pasan los parámetros de BigQuery:

```python
dataset.to_gbq(destination_table='nombre_de_la_tabla',
  project_id = 'id_proyecto',
  if_exists = 'fail')
```


### Clase 7. Ventajas y desventajas de los formatos de importar y guardado

[Notebook de la Clase](https://github.com/bl00p1ng/Curso-analisis-de-datos-con-Pandas-y-Python/blob/main/save_and_load.ipynb)

<a href="https://colab.research.google.com/github/bl00p1ng/Curso-analisis-de-datos-con-Pandas-y-Python/blob/main/save_and_load.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a>

[Documentación IO Tools de Pandas ](https://pandas.pydata.org/pandas-docs/stable/user_guide/io.html)


## 📚 Módulo 2. Funcionalidades básicas y esenciales de pandas

### Clase 8. Formatos de lectura para cargar y guardar DataFrames

[Notebook de la Clase](https://github.com/bl00p1ng/Curso-analisis-de-datos-con-Pandas-y-Python/blob/main/formatos_cargar_guardar_datos.ipynb)

<a href="https://colab.research.google.com/github/bl00p1ng/Curso-analisis-de-datos-con-Pandas-y-Python/blob/main/formatos_cargar_guardar_datos.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a>

El siguiente análisis se realizó con un data set creado con datos aleatorios que contiene más de 100,000 registros y 30 columnas.

Comparativa entre los diferentes formatos para cargar y guardar datos:

#### Tamaño de Archivo

El formato que ocupa menos espacio es **Parquet**. Hay 2 formatos que destacan por ser más pesados que los demás, esos son *CSV* y *JSON*.

![Grafico del tamaño de archivo](https://i.ibb.co/Y2FydS9/serialized-file-size.png)

Si se hace una categorización de las variables, los formatos binarios toman ventaja y reducen drásticamente el tamaño del archivo.

![Grafico del tamaño de archivo después de categorizar las variables](https://i.ibb.co/PZCr2rJ/serialized-file-size-categories.png)

#### Tiempos de Carga y Lectura

Los formatos más lentos son *JSON* y *CSV*. **Parquet**, **Pickle** y **Feather** sobresalen por sus cortos tiempos de carga y lectura.

![Grafico del tiempo de carga](https://i.ibb.co/yy6DXk7/time-to-save-load-a-Data-Frame.png)

#### Consumo de memoria RAM

El formato que consume (por mucho) más memoria RAM es *JSON*. Los formatos que destacan por su eficiencia en uso de la memoria son **Parquet**, **Feather** y **Pickle**.

![Grafico Consumo de RAM](https://i.ibb.co/kDWbdrR/memory-consumption.png)

Si se hace una categorización de las variables, se tiene que **Parquet** sigue siendo extremadamente eficiente.

![Grafico del consumo de RAM después de categorizar variables](https://i.ibb.co/P97JSSW/memory-consumption-categories.png)

**Conclusiones:**

- **CSV y formatos String:** Son simples, requieren **alto costo computacional** y algo **lentos**.
- **HDF:** Gran soporte, **adecuado para grandes cantidades de datos**, rápido a costo de **alto costo computacional**.
- **Parquet:** Puede igualar a HDF e inclusive **trabajar por chunks y en paralelo**.
- **Pickle:** Es **práctico pero lento** con grandes cantidades de datos.