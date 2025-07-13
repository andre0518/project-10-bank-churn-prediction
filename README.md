# Proyecto 10 – Predicción de abandono de clientes bancarios

Este proyecto tiene como objetivo predecir si un cliente del banco Beta abandonará o no la institución, utilizando modelos de clasificación basados en datos demográficos, financieros y de comportamiento. El análisis se realizó como parte del bootcamp de Ciencia de Datos de TripleTen.

---

## 📁 Dataset

El dataset proviene del archivo `/datasets/Churn.csv` y contiene 10,000 registros de clientes del banco, con las siguientes columnas relevantes:

- `CreditScore`: puntaje de crédito del cliente
- `Geography`: país de residencia
- `Gender`: sexo del cliente
- `Age`: edad del cliente
- `Tenure`: años con cuenta activa
- `Balance`: saldo de la cuenta
- `NumOfProducts`: cantidad de productos contratados
- `HasCrCard`: tiene tarjeta de crédito (1: sí, 0: no)
- `IsActiveMember`: actividad del cliente (1: activo, 0: inactivo)
- `EstimatedSalary`: salario estimado
- `Exited`: variable objetivo (1: abandonó el banco, 0: permaneció)

---

## 🔍 Análisis Exploratorio de Datos (EDA)

Se realizó un EDA completo con:
- Histogramas y diagramas de caja de variables numéricas
- Análisis de proporciones por clase
- Gráficos de frecuencia para variables categóricas

Se identificaron factores importantes en el abandono como la edad, saldo, nivel de actividad y país de residencia. También se confirmó un fuerte desequilibrio de clases: solo el 20% de los clientes abandonaron el banco.

---

## ⚙️ Preparación de los datos

- Se eliminaron columnas irrelevantes (`RowNumber`, `CustomerId`, `Surname`)
- Se imputaron valores nulos en `Tenure`
- Se codificaron variables categóricas con `get_dummies`
- Se escalaron los datos con `StandardScaler`
- Se dividió el conjunto en entrenamiento (75%) y validación (25%)

---

## 🤖 Modelado

Se probaron tres enfoques:
1. Regresión logística sin balanceo
2. Regresión logística con `class_weight='balanced'`
3. Regresión logística con **undersampling** (mejor resultado)

---

## 📊 Resultados del modelo final

El modelo final fue una regresión logística entrenada con submuestreo de la clase mayoritaria.

- **F1-score**: 0.5107
- **AUC-ROC**: 0.7643
- **Recall clase positiva (`Exited = 1`)**: 0.72

El modelo es capaz de identificar correctamente la mayoría de los clientes que abandonan, lo cual puede ser útil para aplicar acciones preventivas.

---

## 🧠 Tecnologías utilizadas

- Python
- Pandas, NumPy
- Scikit-learn
- Matplotlib, Seaborn

---

## 📌 Autor

Andreina Moreno Franco  
[LinkedIn](https://www.linkedin.com/in/andreina-moreno-franco)  
[GitHub](https://github.com/andre0518)