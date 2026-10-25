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
4. **Evaluación y pronóstico:** comparación cuantitativa de modelos sobre un período de validación, evaluación final fuera de muestra en 2024 y regla de contratación basada en cuantiles predictivos.

Cada evaluación se identifica por su sigla: **F** para formativa y **S** para sumativa, seguida del número de la semana (F1, S1, F2, S2, F3…).

## Desarrollo del proyecto

### Semana 1 — Exploración de la serie
Caracterización inicial del consumo eléctrico, análisis exploratorio, estacionalidad, valores faltantes y atípicos.

### Semana 2 — Modelos clásicos
Transformación de la serie, estacionariedad, identificación y evaluación de modelos ARIMA/SARIMA y selección del modelo M4 mediante validación fuera de muestra 2023.

### Semana 3 — Modelos avanzados
Evaluación de memoria larga mediante ARFIMA y volatilidad condicional mediante GARCH. Los resultados no justificaron sustituir el modelo SARIMA seleccionado.

### Semana 4 — Evaluación final y comunicación
Reestimación del modelo M4 = SARIMA(0,1,0)(1,1,0)₁₂ sobre log(consumo) con datos 2015–2023 y evaluación final fuera de muestra durante 2024.

Se evaluaron RMSE, MAE, MASE, ME y cobertura de intervalos. El pronóstico puntual se retransforma con exp(μ + σ²/2) y los cuantiles con exp(μ + z_τ σ).

El proyecto culmina traduciendo la distribución predictiva a una regla de contratación basada en costos asimétricos:

```text
tau* = cu / (cu + co)
```

Se analizaron escenarios Q50, Q75 y Q80, cuantificando volumen contratado, déficit, excedente y meses con déficit o excedente.

### Retroalimentación incorporada en Semana 4

A partir de la Formativa 4 se incorporaron tres mejoras indicadas por el docente:

1. Completar la comparación con las alternativas evaluadas durante la Semana 2.
2. Unificar la retransformación de los modelos estimados sobre logaritmos.
3. Cuantificar con datos 2024 el efecto de la regla de contratación basada en cuantiles predictivos.

La Sumativa 4 documenta estas tres respuestas en la sección «Respuesta al feedback del profesor».

### Accesos rápidos — Semana 4

- [Formativa 4](notebooks/semana_4/F4/)
- [Sumativa 4](notebooks/semana_4/S4/)
- [Resultados Semana 4](resultados/semana_4/)

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
│   ├── semana_3/
│   │   ├── F3/
│   │   │   └── mcdi505_s3calarcon.ipynb
│   │   └── S3/
│   │       └── mcdi505_S3CAlarcon.ipynb
│   └── semana_4/
│       ├── F4/
│       │   └── mcdi505_F4CAlarcon.ipynb
│       └── S4/
│           └── mcdi505_S4CAlarcon.ipynb
├── resultados/
│   ├── semana_2/
│   │   └── F2/
│   │       └── mcdi505_s2calarcon.html
│   ├── semana_3/
│   │   ├── F3/
│   │   │   └── mcdi505_s3calarcon.html
│   │   └── S3/
│   └── semana_4/
│       ├── F4/
│       └── S4/
│           ├── figura1_pronostico_2024.png
│           ├── figura2_q50_q75_2024.png
│           └── tablas/
│               ├── tabla3_evaluacion_2023_2024.csv
│               ├── tabla4_sesgo.csv
│               ├── tabla5b_alternativas_s2_validacion_2023.csv
│               ├── tabla6_contratacion_q50_q75_q80.csv
│               └── tabla6b_cambio_q50_q75.csv
├── .gitignore
├── README.md
└── requirements.txt
```

- `notebooks/` contiene los notebooks fuente con sus salidas guardadas.
- `resultados/` contiene exportaciones HTML de notebooks ejecutados y, en la Semana 4, las figuras y tablas CSV que genera la Sumativa 4.
- En la Semana 3, **F3 = Evaluación Formativa 3** y **S3 = Evaluación Sumativa 3**. `resultados/semana_3/S3/` contiene solo un archivo `.gitkeep`, porque Git no guarda carpetas vacías.
- En la Semana 4, **F4 = Evaluación Formativa 4** y **S4 = Evaluación Sumativa 4**. La S4 escribe sus figuras y tablas en `resultados/semana_4/S4/`; `resultados/semana_4/F4/` contiene solo un `.gitkeep`.
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
| Sumativa 3 | `notebooks/semana_3/S3/mcdi505_S3CAlarcon.ipynb` | — | Versión final de la entrega sumativa: ARFIMA y GARCH contrastados con el SARIMA M4, que se mantiene como modelo seleccionado. |

### Semana 4 — Evaluación final y comunicación

- **F4 = Evaluación Formativa 4** → `notebooks/semana_4/F4/` y `resultados/semana_4/F4/`
- **S4 = Evaluación Sumativa 4** → `notebooks/semana_4/S4/` y `resultados/semana_4/S4/`

| Evaluación | Notebook | Resultado | Contenido |
| --- | --- | --- | --- |
| Formativa 4 | [`notebooks/semana_4/F4/mcdi505_F4CAlarcon.ipynb`](notebooks/semana_4/F4/mcdi505_F4CAlarcon.ipynb) | — | Borrador del informe ejecutivo del proyecto que dio origen a la retroalimentación docente. |
| Sumativa 4 | [`notebooks/semana_4/S4/mcdi505_S4CAlarcon.ipynb`](notebooks/semana_4/S4/mcdi505_S4CAlarcon.ipynb) | [`resultados/semana_4/S4/`](resultados/semana_4/S4/) | Informe ejecutivo final: reestimación de M4 con 2015–2023, prueba 2024 (RMSE, MAE, MASE, ME y cobertura), tabla con las alternativas de la Semana 2, retransformación unificada y efecto de la regla de contratación Q50/Q75/Q80 en 2024. |

## Datos

| Archivo | Uso |
| --- | --- |
| `data/raw/consumo_electrico_litoral.csv` | Serie original del caso transversal (Sumativa 1 y Formativa 2). |
| `data/raw/consumo_electrico_litoral_depurado.csv` | Serie depurada (Sumativa 2, Semana 3 y Semana 4). |

Los CSV no se modifican: cada notebook hace sus transformaciones en memoria. El año 2024 se reserva para la evaluación final de la Semana 4 y no se usa para estimar ni seleccionar modelos.

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

Las salidas guardadas provienen de entornos distintos. F1 se ejecutó con Python 3.13.16, NumPy 2.5.3, pandas 3.0.5 y statsmodels 0.15.0. S1 se ejecutó con Python 3.12.5, pandas 3.0.3 y statsmodels 0.14.6. F2, S2 y F3 se ejecutaron con Python 3.12.5. F4 y S4 se ejecutaron con Python 3.12.5, NumPy 2.4.6, pandas 3.0.3, SciPy 1.18.0, statsmodels 0.14.6 y matplotlib 3.10.9. Estas son las versiones que registran las salidas; no se validó un entorno común.

`requirements.txt` enumera las dependencias sin fijar versiones. Sirve para preparar el entorno, pero no garantiza reproducir exactamente el entorno original.
