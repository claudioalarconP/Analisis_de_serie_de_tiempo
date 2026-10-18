# Análisis de Series de Tiempo — MCDI505

Repositorio de las evaluaciones formativas y sumativas del curso **MCDI505 — Análisis de Series de Tiempo**. El trabajo se organiza por semana y por tipo de evaluación, y se basa en un caso transversal: la serie mensual de consumo eléctrico comercial.

## Información académica

- **Programa:** Magíster en Ciencia de Datos e Inteligencia Artificial
- **Asignatura:** Análisis de Series de Tiempo — MCDI505
- **Estudiante:** Claudio Rodolfo Alarcón Pradenas
- **Docente:** Dr. Harvey Jezlid Rosas Quintero
- **Institución:** Universidad Andrés Bello
- **Año:** 2026

## Objetivo del repositorio

El repositorio reúne el desarrollo progresivo del proyecto del curso:

1. **Análisis exploratorio:** auditoría de la serie, tendencia, estacionalidad, atípicos, efecto COVID-19, ACF y PACF.
2. **Modelamiento clásico:** estacionariedad, identificación, estimación y diagnóstico de modelos ARIMA y SARIMA.
3. **Modelos avanzados:** memoria larga (ARFIMA) y volatilidad condicional (GARCH), contrastados con el SARIMA de referencia.
4. **Evaluación y pronóstico:** comparación cuantitativa de modelos sobre un período de validación.

Cada evaluación se identifica por su sigla: **F** para formativa y **S** para sumativa, seguida del número de la semana (F1, S1, F2, S2, F3…).

## Estructura del repositorio

```text
.
├── data/
│   └── raw/
│       ├── consumo_electrico_litoral.csv
│       └── consumo_electrico_litoral_depurado.csv
├── notebooks/
│   ├── semana_1/
│   │   ├── F1/
│   │   │   └── mcdi505_f1calarcon.ipynb
│   │   └── S1/
│   │       └── mcdi505_s1calarcon.ipynb
│   ├── semana_2/
│   │   ├── F2/
│   │   │   └── mcdi505_s2calarcon.ipynb
│   │   └── S2/
│   │       └── mcdi505_s2calarcon.ipynb
│   └── semana_3/
│       ├── F3/
│       │   └── mcdi505_s3calarcon.ipynb
│       └── S3/          ← reservada para mcdi505_s3calarcon.ipynb (versión final)
├── resultados/
│   ├── semana_2/
│   │   └── F2/
│   │       └── mcdi505_s2calarcon.html
│   └── semana_3/
│       ├── F3/
│       │   └── mcdi505_s3calarcon.html
│       └── S3/          ← reservada para mcdi505_s3calarcon.html
├── .gitignore
├── README.md
└── requirements.txt
```

- `notebooks/` contiene los notebooks fuente con sus salidas guardadas.
- `resultados/` contiene exportaciones HTML de notebooks ejecutados, para revisarlos sin instalar el entorno.
- En la Semana 3, **F3 = Evaluación Formativa 3** y **S3 = Evaluación Sumativa 3**. Las carpetas `notebooks/semana_3/S3/` y `resultados/semana_3/S3/` ya están creadas y preparadas para recibir la versión final de la entrega sumativa. Mientras tanto contienen solo un archivo `.gitkeep`, porque Git no guarda carpetas vacías.
- Las carpetas F2 y S2 contienen archivos con el mismo nombre (`mcdi505_s2calarcon.ipynb`) y lo mismo ocurre con F3. La carpeta indica la evaluación: F2 es la Formativa 2 y S2 la Sumativa 2. El notebook de `semana_3/F3/` es la Formativa 3.

## Contenido por semana

### Semana 1 — Análisis exploratorio

| Evaluación | Notebook | Contenido |
| --- | --- | --- |
| Formativa 1 | `notebooks/semana_1/F1/mcdi505_f1calarcon.ipynb` | Caso «Bodegaje y quiebres de stock»: conceptos iniciales, exploración gráfica, componentes temporales y autocorrelación, con series simuladas dentro del notebook. |
| Sumativa 1 | `notebooks/semana_1/S1/mcdi505_s1calarcon.ipynb` | Análisis exploratorio del consumo eléctrico comercial: auditoría, valores faltantes, atípico de noviembre de 2017, efecto COVID-19, tendencia, estacionalidad, cambios de nivel y variabilidad, descomposición, ACF y PACF. |

### Semana 2 — Modelos clásicos (ARIMA / SARIMA)

| Evaluación | Notebook | Resultado | Contenido |
| --- | --- | --- | --- |
| Formativa 2 | `notebooks/semana_2/F2/mcdi505_s2calarcon.ipynb` | `resultados/semana_2/F2/mcdi505_s2calarcon.html` | Informe técnico de modelos clásicos: estacionariedad (ADF, KPSS), quiebre COVID-19, identificación, estimación, selección y diagnóstico de residuos. |
| Sumativa 2 | `notebooks/semana_2/S2/mcdi505_s2calarcon.ipynb` | — | Hoja de decisiones, transformaciones, identificación, estimación, selección y diagnóstico de modelos ARIMA/SARIMA sobre la serie depurada. |

### Semana 3 — Modelos avanzados (ARFIMA / GARCH)

- **F3 = Evaluación Formativa 3** → `notebooks/semana_3/F3/` y `resultados/semana_3/F3/`
- **S3 = Evaluación Sumativa 3** → `notebooks/semana_3/S3/` y `resultados/semana_3/S3/`

| Evaluación | Notebook | Resultado | Contenido |
| --- | --- | --- | --- |
| Formativa 3 | `notebooks/semana_3/F3/mcdi505_s3calarcon.ipynb` | `resultados/semana_3/F3/mcdi505_s3calarcon.html` | Memoria larga (ARFIMA / diferenciación fraccional), volatilidad (GARCH), contraste con el SARIMA de la Sumativa 2 y selección del modelo con evidencia cuantitativa. Entrenamiento: 2015–2022; validación: 2023. |
| Sumativa 3 | `notebooks/semana_3/S3/mcdi505_s3calarcon.ipynb` (pendiente) | `resultados/semana_3/S3/mcdi505_s3calarcon.html` (pendiente) | Carpetas creadas y preparadas para recibir la versión final de la entrega sumativa. |

## Datos

| Archivo | Uso |
| --- | --- |
| `data/raw/consumo_electrico_litoral.csv` | Serie original del caso transversal (Sumativa 1 y Formativa 2). |
| `data/raw/consumo_electrico_litoral_depurado.csv` | Serie depurada (Sumativa 2 y Formativa 3). |

Los CSV no se modifican: cada notebook hace sus transformaciones en memoria. El año 2024 se reserva para la evaluación final y ningún notebook actual lo usa para estimar modelos.

## Reproducción

1. Clonar el repositorio y entrar en su carpeta:

   ```bash
   git clone https://github.com/claudioalarconP/Analisis_de_serie_de_tiempo.git
   cd Analisis_de_serie_de_tiempo
   ```

2. Crear y activar un entorno virtual:

   ```bash
   python -m venv .venv
   ```

   En Windows PowerShell: `.venv\Scripts\Activate.ps1`. En Linux/macOS: `source .venv/bin/activate`.

3. Instalar las dependencias y abrir JupyterLab:

   ```bash
   python -m pip install -r requirements.txt
   python -m jupyterlab
   ```

4. Abrir el notebook y ejecutar **Restart Kernel and Run All Cells**.

Los notebooks buscan el CSV con rutas relativas: junto al notebook, en `data/raw/` o subiendo carpetas hasta la raíz del proyecto. Por eso se pueden ejecutar desde la carpeta de su evaluación sin cambiar rutas.

Para regenerar una exportación HTML a partir de las salidas guardadas, sin volver a ejecutar el notebook:

```bash
python -m jupyter nbconvert --to html notebooks/semana_3/F3/mcdi505_s3calarcon.ipynb --output-dir resultados/semana_3/F3
```

### Versiones de ejecución

Las salidas guardadas provienen de entornos distintos. F1 se ejecutó con Python 3.13.16, NumPy 2.5.3, pandas 3.0.5 y statsmodels 0.15.0. S1 se ejecutó con Python 3.12.5, pandas 3.0.3 y statsmodels 0.14.6. F2, S2 y F3 se ejecutaron con Python 3.12.5. Estas son las versiones que registran las salidas; no se validó un entorno común.

`requirements.txt` enumera las dependencias sin fijar versiones. Sirve para preparar el entorno, pero no garantiza reproducir exactamente el entorno original.
