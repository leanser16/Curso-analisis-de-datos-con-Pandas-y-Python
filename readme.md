# Curso de Manipulación y Análisis de Datos con Pandas y Python

Notas y Código del [Curso de Manipulación y Análisis de Datos con Pandas y Python de Platzi](https://platzi.com/cursos/pandas/)

- [Curso de Manipulación y Análisis de Datos con Pandas y Python](#curso-de-manipulación-y-análisis-de-datos-con-pandas-y-python)
  - [Módulo 1. Comenzando con pandas](#módulo-1-comenzando-con-pandas)
    - [Clase 2. Primeros pasos con Google Colab: configuración del entorno de trabajo](#clase-2-primeros-pasos-con-google-colab-configuración-del-entorno-de-trabajo)
    - [Clase 3. Series e Indexación y selección de datos](#clase-3-series-e-indexación-y-selección-de-datos)
      - [Algunos métodos útiles para filtrar datos](#algunos-métodos-útiles-para-filtrar-datos)
    - [Clase 4. De paneles de datos al DataFrame](#clase-4-de-paneles-de-datos-al-dataframe)
      - [Otros métodos útiles para analizar DataFrames](#otros-métodos-útiles-para-analizar-dataframes)


## Módulo 1. Comenzando con pandas

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