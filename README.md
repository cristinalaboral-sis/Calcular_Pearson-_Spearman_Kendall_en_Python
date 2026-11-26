# Análisis de Correlación del Mercado Inmobiliario Argentino

## Propósito

El objetivo de este proyecto es analizar las relaciones existentes entre distintas características de las propiedades publicadas en el mercado inmobiliario argentino, con especial atención al precio en dólares, las superficies, la cantidad de ambientes y la antigüedad.

A través de Python y sus principales bibliotecas de análisis de datos, se busca identificar cómo se relacionan estas variables y evaluar la intensidad y el comportamiento de dichas relaciones.

Para ello, se aplican tres métodos estadísticos de correlación: Pearson, Spearman y Kendall. La comparación permite observar cómo cambian los resultados según el método utilizado y las características de los datos.

También se analiza el efecto de los valores atípicos sobre los coeficientes de correlación, comparando los resultados obtenidos con el conjunto de datos original y con un conjunto sin los valores identificados como extremos.

## Tecnologías y Herramientas Utilizadas

- **Python:** lenguaje utilizado para el procesamiento y análisis de los datos.
- **Pandas:** lectura, selección, limpieza y manipulación del conjunto de datos.
- **NumPy:** operaciones numéricas y tratamiento de valores inválidos.
- **Matplotlib:** construcción y personalización de gráficos.
- **Seaborn:** visualización estadística mediante distintos tipos de gráficos.
- **SciPy:** herramientas para el análisis estadístico.
- **Jupyter Notebook:** entorno interactivo utilizado para desarrollar y documentar el análisis.

## Descripción del Análisis

El proyecto se organiza en las siguientes etapas:

### 1. Carga y exploración inicial

Se utiliza Pandas para leer el archivo `venta.csv`, que contiene publicaciones de propiedades inmobiliarias.

El conjunto de datos original cuenta con:

- **Registros:** 519.792.
- **Variables:** 35.

Se realiza una revisión inicial de las dimensiones, los tipos de datos, los primeros registros y la estructura general del conjunto de datos.

### 2. Selección de variables

Para el análisis se seleccionan las variables necesarias para estudiar las relaciones entre las características de las propiedades.

Las principales variables utilizadas son:

- `p_dolar`: precio expresado en dólares.
- `sup_tot`: superficie total.
- `sup_cub`: superficie cubierta.
- `amb`: cantidad de ambientes.
- `antig`: antigüedad de la propiedad.

También se conservan las variables `id` y `barrio` como información complementaria para identificar y revisar publicaciones.

Se crea un conjunto de trabajo independiente para realizar las modificaciones necesarias sin alterar el dataset original.

### 3. Preparación y limpieza de datos

Se revisan las variables seleccionadas para identificar valores faltantes, registros inconsistentes y posibles errores de carga.

Las operaciones incluyen:

- Revisión de valores negativos en antigüedad.
- Identificación de posibles años registrados incorrectamente como antigüedad.
- Revisión de antigüedades superiores a 100 años.
- Identificación de valores iguales a cero en cantidad de ambientes.
- Revisión de cantidades de ambientes superiores a 50.

Los valores considerados inválidos o poco confiables se reemplazan por valores faltantes (`NaN`), manteniendo los registros para no eliminar información innecesariamente.

### 4. Análisis descriptivo de las variables

Se calculan medidas estadísticas para conocer el comportamiento de las variables numéricas:

- Cantidad de observaciones disponibles.
- Media.
- Mediana.
- Desviación estándar.
- Valores mínimos y máximos.
- Cuartiles.

También se analiza la distribución de las variables mediante medidas de asimetría y curtosis.

Este análisis permite observar diferencias entre las distribuciones y reconocer características que pueden influir en los resultados de las correlaciones.

### 5. Análisis de normalidad y distribución

Se estudia el comportamiento de las variables numéricas para evaluar si presentan distribuciones simétricas o asimétricas.

Se tienen en cuenta las características de cada variable y la presencia de valores extremos.

Esta etapa permite fundamentar la elección de los métodos de correlación y comprender por qué los distintos coeficientes pueden presentar resultados diferentes.

### 6. Detección y análisis de valores atípicos

Se utiliza el método del rango intercuartílico (IQR) para identificar valores atípicos en las principales variables numéricas.

El procedimiento contempla:

- Cálculo del primer y tercer cuartil.
- Obtención del rango intercuartílico.
- Determinación de los límites inferior y superior.
- Identificación de los valores que se encuentran fuera de esos límites.
- Revisión de la cantidad de registros afectados.

Los valores atípicos se conservan inicialmente para evaluar su influencia sobre las relaciones entre las variables.

### 7. Comparación de correlaciones con y sin valores atípicos

Se construye un segundo conjunto de datos excluyendo los registros identificados como atípicos mediante el criterio IQR.

El objetivo es comparar los resultados obtenidos antes y después de esta exclusión.

El proceso permitió obtener los siguientes resultados:

- **Registros originales:** 519.792.
- **Registros sin valores atípicos:** 455.892.
- **Registros excluidos:** 63.900.
- **Porcentaje conservado:** 87,71 %.

Esta comparación permite observar cuánto pueden influir los valores extremos en las relaciones entre las variables.

### 8. Aplicación de los métodos de correlación

Se aplican tres métodos para analizar las relaciones entre las variables numéricas:

**Pearson**

Permite medir la intensidad y dirección de la relación lineal entre dos variables. Es sensible a los valores atípicos y puede verse afectado por distribuciones muy asimétricas.

**Spearman**

Permite evaluar si existe una relación monotónica entre dos variables, sin exigir que la relación sea lineal. Trabaja a partir de los rangos de los valores.

**Kendall**

Mide la asociación entre dos variables mediante la comparación de pares de observaciones. Permite complementar los resultados obtenidos con Spearman.

Se calculan las matrices de correlación para los datos originales y para los datos sin valores atípicos.

## Visualizaciones

Se utilizan distintas representaciones gráficas para facilitar la interpretación de los resultados:

- **Histogramas:** permiten observar la distribución de las variables numéricas.
- **Boxplots:** permiten identificar la dispersión de los datos y la presencia de valores extremos.
- **Mapas de calor (Heatmaps):** permiten visualizar las matrices de correlación e identificar la intensidad y dirección de las relaciones entre variables.
- **Gráficos comparativos:** permiten observar las diferencias entre los métodos de correlación y entre los conjuntos de datos originales y sin valores atípicos.

Las visualizaciones complementan los resultados numéricos y ayudan a identificar patrones y diferencias entre los métodos utilizados.

## Resultados del Análisis

La comparación de los tres métodos permitió identificar diferencias importantes en las relaciones entre las variables.

Entre los principales resultados se destacan:

- Pearson muestra relaciones lineales débiles entre el precio en dólares y las variables de superficie y cantidad de ambientes.
- Spearman identifica asociaciones positivas fuertes entre el precio en dólares y las superficies, así como con la cantidad de ambientes.
- Kendall presenta resultados similares a Spearman, aunque con coeficientes de menor magnitud.
- La relación entre superficie total y superficie cubierta presenta una asociación positiva importante.
- La antigüedad muestra una relación muy débil con el precio en dólares.

Los resultados muestran que la elección del método influye en la interpretación de las relaciones encontradas.

Spearman y Kendall permiten identificar asociaciones monotónicas que no necesariamente se reflejan en los resultados de Pearson.

## Interpretación y Conclusiones

El análisis permitió observar que las relaciones entre las características de las propiedades y sus precios pueden variar según el método de correlación utilizado.

En particular, las superficies y la cantidad de ambientes presentan asociaciones positivas con el precio en dólares cuando se utilizan los métodos de Spearman y Kendall.

También se comprobó la importancia de analizar los valores atípicos, ya que pueden modificar la intensidad de algunas correlaciones.

La comparación entre los datos originales y los datos sin valores atípicos permite evaluar estas diferencias y obtener una interpretación más completa.

Es importante tener en cuenta que una correlación indica asociación entre variables, pero no demuestra que una variable sea la causa de los cambios en otra.

## Estructura del Repositorio

- `data/`: contiene el archivo original `venta.csv`.
- `notebooks/`: contiene el notebook Jupyter con el desarrollo del análisis.
- `.gitignore`: permite excluir archivos temporales, entornos virtuales y otros elementos que no deben incluirse en el repositorio.
- `README.md`: documentación general del proyecto.

## Dataset

El conjunto de datos utilizado corresponde a publicaciones de propiedades inmobiliarias en la Ciudad Autónoma de Buenos Aires (CABA).

**Fuente:** [Dataset de mercado inmobiliario en CABA. Venta y alquiler – Zenodo](https://zenodo.org/records/13826379)

**Autor:** Sergio Rosanovich – Universidad Nacional de San Martín.

El archivo utilizado para el análisis es `venta.csv`, obtenido a partir del conjunto de datos original en formato Excel.

## Requisitos

- Python 3.10 o superior.
- Pandas.
- NumPy.
- Matplotlib.
- Seaborn.
- SciPy.
- Jupyter Notebook.

## Pasos para Ejecutar

1. Clonar el repositorio desde GitHub.
2. Descargar el archivo `venta.csv` desde la fuente indicada.
3. Colocar el archivo dentro de la carpeta `data/`.
4. Abrir el proyecto en Visual Studio Code.
5. Seleccionar un entorno de Python con las bibliotecas necesarias instaladas.
6. Abrir el notebook `analisis_correlacion.ipynb`, ubicado en la carpeta `notebooks/`.
7. Ejecutar las celdas en orden.

## Autor

Proyecto académico de análisis estadístico y correlación aplicado al mercado inmobiliario argentino, desarrollado con Python y herramientas de análisis de datos.