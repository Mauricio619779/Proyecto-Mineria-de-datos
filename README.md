# 🚴‍♂️ Sistema de Análisis y Predicción de Arriendos de Bicicletas

Este proyecto busca analizar y predecir el arriendo de bicicletas en Washington D.C. entre 2022 y 2024, usando datos históricos de uso y clima. Se entrenó un modelo de machine learning y se desarrolló una interfaz web interactiva.




## 📂 Fuentes de datos

- 🚲 **Datos de arriendos de bicicletas (Capital Bikeshare)**  
  [https://www.capitalbikeshare.com/system-data](https://www.capitalbikeshare.com/system-data)

- 🌦️ **Datos de clima histórico de Washington DC**  
  [https://www.kaggle.com/datasets/taweilo/washington-dc-historical-weather-20158202407](https://www.kaggle.com/datasets/taweilo/washington-dc-historical-weather-20158202407)

---


## 🧪 Etapas del proyecto

1. **Carga de datos**  
   - Se incorporaron 36 archivos `.csv` de arriendos mensuales (2022–2024) y un dataset del clima diario de Washington D.C.

2. **Limpieza y preparación**  
   - Se eliminaron valores nulos, se unificaron formatos de fecha, y se filtraron registros incompletos.
   - Se creó una columna `date` para agrupar viajes por día.

3. **Análisis exploratorio**  
   - Se estudiaron los patrones de arriendo según mes, día de la semana y condiciones climáticas.
   - Se visualizaron correlaciones entre clima y uso de bicicletas.

4. **Cruce con datos climáticos**  
   - Se unieron los datasets de clima y arriendos por fecha.
   - Se identificaron variables climáticas que más afectan la demanda.

5. **Entrenamiento del modelo**  
   - Se usó un **Random Forest Regressor** para predecir la cantidad de viajes diarios.
   - Se entrenó con variables como temperatura, humedad, precipitación, viento y condición climática.

6. **Desarrollo de interfaz interactiva**  
   - Se implementaron 4 herramientas con Gradio para consultas y predicciones.

---

## 📈 Análisis exploratorio

Algunos hallazgos:

- Los meses con más arriendos son **Mayo, Abril y Marzo**.
- La **lluvia y nubosidad** disminuyen significativamente la cantidad de viajes.
- Hay una relación directa entre **temperatura y cantidad de viajes**.

### 📊 Visualizaciones

![Distribución mensual de arriendos](/arriendos_mes.png)
*Cantidad de viajes por mes (2022–2024)*

![Relación temperatura y viajes](/Viajes_vs_temperatura.png)
*Más temperatura suele implicar más arriendos*

---

## 🧠 Variables del modelo

- `temp`: Temperatura promedio diaria (°C)
- `precip`: Precipitación acumulada (mm)
- `humidity`: Humedad relativa (%)
- `windspeed`: Velocidad del viento (km/h)
- `conditions_*`: Variables dummy con tipo de clima (soleado, nublado, etc.)

---

## 💡 Funcionalidades de la interfaz

### 1. 🌤️ Predicción por clima
- El usuario ingresa condiciones climáticas y el sistema predice los viajes estimados.

### 2. 📅 Predicción por fecha futura
- Basado en datos históricos del mismo día en años anteriores.

### 3. 📊 Consulta de viajes reales
- Permite ver cuántos viajes hubo un día específico y muestra su distribución por hora.

### 4. 🌦️ Consulta del clima histórico
- Permite revisar el clima real de una fecha específica.

📌 *Las consultas históricas están disponibles hasta el 31 de mayo de 2024.*

---

## 🎯 Resultados del modelo

- **MAE:** ~2.100  
- **RMSE:** ~2.600  
- **R²:** 0.62

---


## 🤖 Reflexión sobre el desempeño del modelo

El modelo de regresión basado en **Random Forest** obtuvo un **R² de aproximadamente 0.62**, lo cual indica que es capaz de explicar alrededor del **62% de la variabilidad** en la cantidad diaria de arriendos de bicicletas en Washington D.C.

Aunque este valor no representa una predicción perfecta, se considera **un resultado sólido y realista** para este tipo de problema, donde existen múltiples factores externos que afectan la demanda y que no están presentes en el dataset, tales como:

- Eventos públicos, celebraciones o manifestaciones.
- Feriados o cambios en la rutina laboral/educativa.
- Disponibilidad o mantenimiento de bicicletas.
- Cambios en políticas urbanas o infraestructura.

En este proyecto solo se utilizaron variables climáticas (temperatura, precipitación, humedad, etc.) y temporales (fecha), por lo que alcanzar un **R² superior al 0.6** refleja una buena capacidad predictiva del modelo considerando las limitaciones de los datos.

---

## 🖥️ Interfaz Gradio 

![Predicción por clima](/Interfaz_clima.png)
![Consulta por hora](/Interfaz_horas.png)

---

## 👨‍💻 Autores

- Nicolás Concha.
- Mauricio Badilla.

Proyecto para la asignatura **Minería de Datos (2025)**.
