# Análisis de correlación del mercado inmobiliario argentino

## Descripción del proyecto

Este proyecto analiza la relación entre distintas características de las propiedades publicadas en el mercado inmobiliario argentino.

El objetivo es observar cómo se relacionan el precio en dólares, la superficie total, la superficie cubierta, la cantidad de ambientes y la antigüedad de las propiedades.

Para realizar el análisis se utilizaron tres métodos de correlación: Pearson, Spearman y Kendall. Esto permite comparar los resultados y comprender mejor las relaciones entre las variables.

## Herramientas utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

## Estructura del proyecto

```text
├── data/
│   └── venta.csv
├── notebooks/
│   └── analisis_correlacion.ipynb
└── README.md
```

## Desarrollo del análisis

El trabajo incluye:

- Exploración y preparación de los datos.
- Revisión de valores faltantes y atípicos.
- Análisis de distribución de las variables.
- Aplicación de los métodos Pearson, Spearman y Kendall.
- Comparación de resultados con y sin valores atípicos.
- Interpretación de las relaciones encontradas.

## Dataset

Se utilizó un conjunto de datos de publicaciones de propiedades del mercado inmobiliario argentino.

El archivo original se encuentra en la carpeta `data`.

## Fuente de datos

El conjunto de datos utilizado en este proyecto fue obtenido de Zenodo.

- **Repositorio:** [Zenodo – Dataset de publicaciones inmobiliarias](https://zenodo.org/records/13826379)
- **Archivo utilizado:** `venta.csv` (obtenido a partir del archivo original en formato Excel).

Se conservaron los datos originales como base para realizar las tareas de exploración, limpieza y análisis.

## Ejecución

Para ejecutar el proyecto:

1. Abrir el notebook ubicado en la carpeta `notebooks`.
2. Instalar las bibliotecas necesarias si no están disponibles.
3. Ejecutar las celdas en orden.

## Conclusión

El análisis permite identificar distintas relaciones entre las características de las propiedades y su precio, teniendo en cuenta que una correlación no implica necesariamente una relación de causa y efecto.