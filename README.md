# Análisis de Series de Tiempo — MCDI505

Repositorio correspondiente al curso **MCDI505 — Análisis de Series de Tiempo** del Magíster en Ciencia de Datos e Inteligencia Artificial.

## Semana 1

Durante la Semana 1 se desarrollan las actividades **Formativa 1 (F1)** y **Sumativa 1 (S1)**.

### Formativa 1

La actividad formativa corresponde al análisis del caso **“Bodegaje y quiebres de stock”**, utilizado para trabajar conceptos iniciales de series de tiempo, exploración gráfica, componentes temporales y autocorrelación.

Archivo:

`notebooks/semana_1/F1/mcdi505_f1calarcon.ipynb`

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

`notebooks/semana_1/S1/mcdi505_s1calarcon.ipynb`

Dataset:

`data/raw/consumo_electrico_litoral.csv`

## Estructura actual

| Archivo | Contenido |
| --- | --- |
| `data/raw/consumo_electrico_litoral.csv` | Datos originales de la Sumativa 1 |
| `notebooks/semana_1/F1/mcdi505_f1calarcon.ipynb` | Formativa 1 |
| `notebooks/semana_1/S1/mcdi505_s1calarcon.ipynb` | Sumativa 1 |
| `requirements.txt` | Dependencias para ejecutar los notebooks |
| `README.md` | Descripción e instrucciones |

## Reproducción

1. Clonar el repositorio y entrar en su carpeta:

   ```bash
   git clone https://github.com/claudioalarconP/Analisis_de_serie_de_tiempo.git
   cd Analisis_de_serie_de_tiempo
   ```

2. Crear un entorno virtual:

   ```bash
   python -m venv .venv
   ```

   Activarlo en Windows PowerShell con `.venv\Scripts\Activate.ps1`, o en Linux/macOS con `source .venv/bin/activate`.

3. Instalar las dependencias y abrir JupyterLab:

   ```bash
   python -m pip install -r requirements.txt
   python -m jupyterlab
   ```

4. Abrir el notebook correspondiente y ejecutar **Restart Kernel and Run All Cells**.

La Formativa genera sus series simuladas dentro del notebook. La Sumativa busca el CSV junto al notebook, en `data/raw/` desde la raíz del proyecto o en las rutas relativas hacia esa carpeta. En Google Colab, si el CSV no está disponible, solicita subirlo.

El CSV original se conserva; la limpieza se realiza en memoria. La Sumativa analiza enero de 2015 a diciembre de 2023 (108 meses) y reserva 2024 para evaluación posterior.

### Versiones de ejecución

Las salidas guardadas registran entornos distintos: F1 usa Python 3.13.16, NumPy 2.5.3, pandas 3.0.5 y statsmodels 0.15.0; S1 usa Python 3.12.5, pandas 3.0.3 y statsmodels 0.14.6. Estas son las versiones informadas en las salidas, no un entorno común validado.

`requirements.txt` enumera las dependencias sin fijar versiones. Permite preparar el entorno, pero no garantiza reproducir exactamente el entorno original. Antes de entregar, ejecutar ambos notebooks desde cero en el entorno utilizado.
