# Análisis y Predicción de Cancelación de Clientes (Churn)

Este proyecto tiene como objetivo predecir la probabilidad de que un cliente de telecomunicaciones cancele su servicio (Churn) utilizando diversos modelos de aprendizaje automático. Se realiza un análisis exhaustivo de los datos, preprocesamiento, entrenamiento y evaluación de modelos para identificar los factores clave que influyen en la cancelación y proponer estrategias de retención.

## 📊 Contenido del Cuaderno

1.  **Extracción del Archivo Tratado:** Carga de los datos pre-procesados desde un archivo CSV.
2.  **Eliminación de Columnas Irrelevantes:** Limpieza de columnas con lógica negativa (terminadas en `_No` o `_no`) y otras columnas especificadas (`gender_Female`, `Churn_Label`).
3.  **Verificación de la Proporción de Cancelación (Churn):** Análisis de la distribución de la variable objetivo (`Churn`).
4.  **Balanceo de Clases:** Aplicación de técnicas de re-muestreo (upsampling de la clase minoritaria) para abordar el desbalance de clases.
5.  **Normalización/Estandarización:** Escalado de las características numéricas utilizando `MinMaxScaler`.
6.  **Análisis de Correlación:** Visualización de la matriz de correlación y análisis de la correlación de las variables con la variable objetivo `Churn`.
7.  **Análisis Dirigido:** Exploración visual de la relación entre variables clave como `tenure` y `Charges.Total` con `Churn`.
8.  **Separación de Datos:** División del conjunto de datos en conjuntos de entrenamiento y prueba (`train_test_split`) con estratificación.
9.  **Creación de Modelos:**
    *   Regresión Logística
    *   KNN (K-Nearest Neighbors)
    *   Random Forest
    *   SVM (Support Vector Machine)
    *   Árbol de Decisión (con optimización de hiperparámetros usando GridSearchCV)
    *   Red Neuronal (implementada con TensorFlow/Keras)
10. **Evaluación de los Modelos:** Cálculo y comparación de métricas de rendimiento (Accuracy, Precision, Recall, F1-score) para cada modelo en el conjunto de prueba.
11. **Análisis de la Importancia de las Variables:** Identificación de las características más relevantes para la predicción del Churn utilizando métodos como coeficientes (LR) e importancia de características (RF, DT).
12. **Conclusión:** Resumen de los hallazgos, comparación de modelos, identificación de factores clave de cancelación y propuesta de estrategias de retención basadas en los resultados.

## 🚀 Cómo Ejecutar el Cuaderno

Este cuaderno está diseñado para ser ejecutado en Google Colaboratory o un entorno Jupyter Notebook.

1.  **Abrir en Google Colab:** Haz clic en el enlace para abrir el cuaderno directamente en Google Colab.
2.  **Ejecutar Celdas:** Ejecuta las celdas secuencialmente. El cuaderno instala automáticamente las bibliotecas necesarias y carga los datos desde la URL especificada.
3.  **Explorar Resultados:** Revisa las salidas de cada celda, incluyendo visualizaciones, métricas de rendimiento y análisis de importancia de variables.

## ⚙️ Requisitos

Las siguientes bibliotecas se utilizan en este cuaderno. Serán instaladas automáticamente en Google Colab si no están presentes:

*   `pandas`
*   `numpy`
*   `sklearn`
*   `matplotlib`
*   `seaborn`
*   `tensorflow`
*   `keras`

## 📂 Datos

Los datos utilizados en este cuaderno son cargados desde la siguiente URL:

`https://raw.githubusercontent.com/ggsgranados/TelecomX-LATAM-Parte-2/refs/heads/main/df_normalizado.csv`

Este archivo CSV es una versión pre-procesada de un conjunto de datos de clientes de telecomunicaciones, que incluye características de cuenta, demografía, servicios contratados y la variable objetivo `Churn`.

## ✨ Factores Clave de Cancelación Identificados

Basado en el análisis, los factores más relevantes que influyen en la cancelación de clientes son:

*   **Tiempo de Contrato (`tenure`):** Clientes con contratos cortos son más propensos a cancelar.
*   **Tipo de Contrato (`Contract_Month-to-month`):** Los contratos mes a mes presentan una mayor tasa de cancelación.
*   **Servicio de Internet (`InternetService_Fiber optic`):** La fibra óptica, sorprendentemente, mostró una correlación positiva con el churn, lo que requiere una investigación más profunda (problemas técnicos, precio, etc.).
*   **Método de Pago (`PaymentMethod_Electronic check`):** Los usuarios de cheque electrónico tienden a cancelar más.
*   **Falta de Servicios Adicionales:** La ausencia de servicios como seguridad online, respaldo, protección de dispositivo y soporte técnico aumenta la probabilidad de churn.
*   **Gasto Total (`Charges.Total`):** Un gasto total bajo acumulado puede indicar un riesgo mayor.

## 📈 Estrategias de Retención Propuestas

Considerando los factores identificados, se sugieren las siguientes estrategias:

*   Ofrecer incentivos a clientes con contratos cortos y mes a mes para migrar a planes a largo plazo.
*   Investigar y abordar las causas de la alta tasa de churn en usuarios de fibra óptica.
*   Optimizar la experiencia de pago para usuarios de cheque electrónico o incentivar el cambio a otros métodos.
*   Promocionar activamente los servicios de seguridad y soporte técnico para aumentar la fidelización.
*   Implementar programas de alerta temprana basados en el modelo predictivo para contactar proactivamente a clientes de alto riesgo.
*   Mejorar la experiencia general del cliente y la comunicación transparente.

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Si deseas mejorar este cuaderno, puedes hacer un fork del repositorio, realizar tus cambios y enviar un pull request.

## 📄 Licencia

[MIT](https://github.com/ggsgranados/TelecomX-LATAM-Parte-2/blob/main/LICENSE)
