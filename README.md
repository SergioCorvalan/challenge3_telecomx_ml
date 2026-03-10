`README.md` 

---

# 📊 Predicción de Churn - Telecom X (Parte 2)

## 🎯 Propósito del Proyecto

El objetivo principal de este proyecto es desarrollar un modelo predictivo capaz de identificar a los clientes con alta probabilidad de cancelar su servicio (**Churn**) en la empresa Telecom X. Mediante el uso de algoritmos de clasificación, buscamos anticiparnos a la fuga y proporcionar insights estratégicos para el equipo de marketing y retención.

---

## 📂 Estructura del Proyecto

* `notebooks/`: Cuaderno principal con el paso a paso del análisis (`Telecom_X_Modelado.ipynb`).
* `data/`: Contiene el dataset original y el dataset procesado (`df_final.csv`).
* `images/`: Exportación de las visualizaciones clave (Matrices de confusión, Scatter plots).
* `README.md`: Documentación del proyecto.

---

## 🛠️ Preparación de Datos y Modelado

### 1. Clasificación y Preprocesamiento

* **Variables Categóricas:** Transformadas mediante **One-Hot Encoding** (usando `drop_first=True`) para evitar la redundancia y la multicolinealidad.
* **Variables Numéricas:** Estandarizadas con `StandardScaler` para asegurar que variables como `TotalCharges` no sesguen los modelos basados en optimización.
* **Balanceo de Clases:** Implementamos **SMOTE** para equilibrar la clase minoritaria (Churn) y mejorar la detección de fugas.

### 2. División de Datos

Se utilizó una proporción de **70% Entrenamiento / 30% Prueba**, aplicando **estratificación** para mantener la distribución original de la variable objetivo en ambos conjuntos.

### 3. Selección de Modelos

* **Regresión Logística:** Elegida por su interpretabilidad y alto **Recall (80%)**.
* **Random Forest:** Utilizado como modelo de ensamble para capturar relaciones no lineales complejas.

---

## 📈 Insights y Visualizaciones Clave

* **El "Cuadrante de Peligro":** Identificamos que los clientes con menos de 10 meses de antigüedad y cargos mensuales superiores a $70 USD tienen la mayor tasa de cancelación.
* **Factores de Retención:** Los contratos de larga duración (1 y 2 años) y los servicios adicionales (Soporte Técnico) actúan como fuertes anclas de lealtad.

---

## 🚀 Instrucciones de Uso

### Requisitos Previos

Es necesario tener instalado Python y las siguientes librerías:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn

```

### Ejecución

1. Clona este repositorio.
2. Asegúrate de que el archivo de datos esté en la ruta `data/`.
3. Abre el cuaderno Jupyter:
```bash
jupyter notebook notebooks/Telecom_X_Modelado.ipynb

```


4. Ejecuta las celdas en orden secuencial para reproducir el entrenamiento y la evaluación.

---

## 💡 Conclusión y Estrategia

El modelo de **Regresión Logística** es el recomendado para producción, ya que logra capturar al **80% de los clientes en riesgo**. Las estrategias de retención deben enfocarse en la migración de contratos "Mes a mes" hacia modelos anuales durante el primer año de vida del cliente.

