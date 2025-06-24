# 📦 Predicción de Ventas por Producto - Laboratorio III (Maestría en Ciencia de Datos)

Este proyecto forma parte de la materia **Laboratorio de Implementación III** de la Maestría en Ciencia de Datos (Universidad Austral). El objetivo es predecir las ventas (en toneladas) por producto para el período **febrero 2020**, en el marco de una competencia privada de Kaggle con datos reales de distribución y consumo.

---

## 🎯 Objetivo

Predecir la cantidad de toneladas (`tn`) vendidas por cada uno de los **780 productos seleccionados** en el canal de distribución, para el mes **2020-02**, utilizando únicamente información anterior a esa fecha.

---

## 📁 Estructura del repositorio

├── data/ # Datasets o muestras (no se suben los originales pesados)
├── notebooks/ # Exploración, análisis y pruebas
├── src/ # Código limpio y funcional (predicción final)
├── notebooks/modelos.ipynb: entrenamiento y evaluación de modelos
├── submission/ # Archivos .csv listos para subir a Kaggle
└── README.md


---

## 📦 Datasets utilizados

Los datos fueron provistos por la cátedra e incluyen:

- `sell-in.txt.gz`: ventas históricas por producto, cliente y mes
- `tb_productos.txt`: catálogo de productos
- `tb_stocks.txt`: niveles de stock mensuales por producto
- `product_id_apredecir201912.txt`: listado oficial de los 780 productos a predecir

> ⚠️ Por motivos de privacidad y tamaño, no se incluyen en este repositorio. Para reproducir el trabajo, colocarlos en la carpeta `/data`.

---

## 🧠 Enfoque metodológico

1. **Exploración de datos (EDA)**
   - Análisis de distribución, estacionalidad y datos faltantes
   - Uniones con catálogo de productos y stock

2. **Modelos base (triviales)**
   - Promedios móviles de 1, 3, 6, 9, 12 meses previos a 2020-02

3. **Modelos estadísticos**
   - ARIMA por producto (lento pero interpretable)

4. **Modelos de machine learning**
   - Regresores tipo LightGBM / Random Forest vía PyCaret
   - Ingeniería de features: lags, fechas, categorías, stock

5. **Evaluación y comparación**
   - Métrica de competencia (por definir por la cátedra)
   - Tabla comparativa de errores por modelo
   - Justificación del modelo elegido

---

## 📊 Resultados

> (Aquí se incluirán gráficos, métricas y conclusiones una vez finalizado el proyecto.)

---

## 🧩 Reproducibilidad

Para ejecutar el proyecto, asegurate de tener las siguientes librerías instaladas:

```bash
pip install -r requirements.txt

✍️ Autor
Melisa Cardozo
📍 MSc. Ciencia de Datos – Universidad Austral
🌱 Enfocada en agtech, forecasting y sustentabilidad
🔗 LinkedIn | Portfolio
