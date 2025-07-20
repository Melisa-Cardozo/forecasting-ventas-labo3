<img width="603" height="174" alt="image" src="https://github.com/user-attachments/assets/4b9c01d9-2617-4d68-b456-c8a8db659eaa" /># Predicción de Ventas por Producto – Laboratorio III (Universidad Austral)

Este proyecto fue realizado en el marco de la materia **Laboratorio III** de la Maestría en Ciencia de Datos. El objetivo fue predecir las ventas de febrero 2020 para 780 productos, utilizando datos históricos mensuales (archivo `sell-in.txt`) y una lista de productos objetivo (`780_a_predecir.txt`).

## 🔍 Descripción del problema

La competencia consistía en generar un archivo de predicción `submission.csv` con la mejor precisión posible (menor RMSE). Se trabajó con series temporales mensuales por producto, sin segmentación adicional por cliente ni categoría.

## 📊 Estrategia de modelado

Se exploraron múltiples alternativas:

- Promedios móviles (3, 9 y 12 meses) – línea base inicial (RMSE ~0.270)
- Modelos clásicos: ARIMA, SARIMA, RidgeCV, regresión lineal con lags
- Modelos supervisados con PyCaret: regresión lineal, Random Forest, LightGBM
- Generación manual y masiva de features por producto
- Modelos automáticos con **AutoGluon TimeSeries**

## 🏆 Modelo final seleccionado

El modelo ganador fue entrenado con AutoGluon TimeSeries con la siguiente configuración:

- `presets='best_quality'`
- `num_val_windows=5`
- `time_limit=3600` segundos
- `set.seed=777`

Este enfoque logró un RMSE público de **0.242**, superando todos los intentos anteriores.

## 📁 Estructura del repositorio


forecasting-ventas-labo3/
├── noteboook_autogluon_final.ipynb
├── data/
│   ├── sell-in.txt.gz               # Histórico de ventas
│   ├── 780_a_predecir.txt
│   └── tb_productos.txt
├── output/
│   └── prediccion_mejor_autogluon.csv
├── src/
│   └── main.py                      # Script reproducible
├── requirements.txt
└── README.md


## 🧪 Reproducibilidad

1. Clonar el repositorio:

```
git clone https://github.com/Melisa-Cardozo/forecasting-ventas-labo3.git
cd forecasting-ventas-labo3
conda create -n laboratorio3 python=3.9
conda activate laboratorio3
pip install -r requirements.txt
python src/main.py
```



## 📌 Notas finales
Se eligió AutoGluon por su rendimiento robusto sin requerir tuning intensivo.

El modelo fue validado por score en el public leaderboard de Kaggle.

Melisa Cardozo
📍 MSc. Ciencia de Datos – Universidad Austral
