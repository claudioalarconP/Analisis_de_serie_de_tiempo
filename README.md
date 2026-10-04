# Análisis de Series de Tiempo — MCDI505

Repositorio correspondiente al curso **MCDI505 — Análisis de Series de Tiempo** del Magíster en Ciencia de Datos e Inteligencia Artificial.

## Semana 1

Durante la Semana 1 se desarrollan las actividades **Formativa 1 (F1)** y **Sumativa 1 (S1)**.

### Formativa 1

La actividad formativa corresponde al análisis del caso **“Bodegaje y quiebres de stock”**, utilizado para trabajar conceptos iniciales de series de tiempo, exploración gráfica, componentes temporales y autocorrelación.

Archivo:

`notebooks/F1/mcdi505_f1calarcon.ipynb`

### Sumativa 1

La Sumativa 1 corresponde al análisis exploratorio de la serie mensual de consumo eléctrico comercial del caso transversal del curso.

El análisis considera:

- auditoría de la serie;
- tratamiento de valores faltantes;
- análisis del dato atípico de noviembre de 2017;
- análisis del efecto COVID-19;
- tendencia;
- estacionalidad;
- cambios de nivel y variabilidad;
- descomposición de la serie;
- funciones ACF y PACF;
- interpretación técnica integrada.

Archivo:

`notebooks/S1/mcdi505_s1calarcon.ipynb`

Dataset:

`data/raw/consumo_electrico_litoral.csv`

## Estructura actual

```text
Analisis_de_serie_de_tiempo/
├── data/
│   └── raw/
│       └── consumo_electrico_litoral.csv
│
├── notebooks/
│   ├── F1/
│   │   └── mcdi505_f1calarcon.ipynb
│   └── S1/
│       └── mcdi505_s1calarcon.ipynb
│
├── results/
│   ├── F1/
│   └── S1/
│
└── README.md


