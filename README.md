# 🚴‍♂️ Sistema de Análisis y Predicción de Arriendos de Bicicletas

Este proyecto busca analizar y predecir el arriendo de bicicletas en Washington D.C. entre 2022 y 2024, usando datos históricos de uso y clima. Se entrenó un modelo de machine learning y se desarrolló una interfaz web interactiva.

## 🧪 Etapas del proyecto

1. **Carga de datos**  
   - Se incorporaron 36 archivos `.csv` de arriendos mensuales (2022–2024) y un dataset de clima diario.

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

- Los meses con más arriendos son **mayo, junio y septiembre**.
- La **lluvia y nubosidad** disminuyen significativamente la cantidad de viajes.
- Hay una relación directa entre **temperatura y cantidad de viajes**.

### 📊 Visualizaciones

![Distribución mensual de arriendos](images/arriendos_mes.png)
*Cantidad de viajes por mes (2022–2024)*

![Relación temperatura y viajes](images/Viajes_vs_temperatura.png)
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

## 🖥️ Interfaz Gradio (capturas)

![Predicción por clima](images/interfaz_clima.png)
![Consulta por hora](images/interfaz_horas.png)

---

## 👨‍💻 Autores

- Nicolás [Apellido]
- Mauricio [Apellido]

Proyecto para la asignatura **Minería de Datos (2025)**.
