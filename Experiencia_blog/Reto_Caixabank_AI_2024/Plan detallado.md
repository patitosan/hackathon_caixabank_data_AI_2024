¡Excelente, Iván! Ahora que tenemos toda la información del reto, vamos a elaborar un plan detallado para abordarlo paso a paso. Mi objetivo es guiarte de manera clara y didáctica en cada etapa. Comencemos.

**Paso 1: Comprender el Reto y las Tareas**

Primero, asegurémonos de entender bien cada una de las tareas:

**Parte 1:**

• **Task 1:**

• **Objetivo:** Responder a cuatro consultas específicas utilizando los datos proporcionados.

• **Salida:** Un archivo JSON con las respuestas, siguiendo el formato en /predictions/predictions_1.json.

• **Task 2:**

• **Objetivo:** Implementar tres funciones en src/data/data_functions.py que realizan análisis específicos sobre los datos de transacciones.

• **Funciones a implementar:**

• earnings_and_expenses(data, client_id, start_date, end_date)

• expenses_summary(data, client_id, start_date, end_date)

• cash_flow_summary(data, client_id, start_date, end_date)

• **Validación:** Se proporcionan tests en /tests/statistics_test.py.


**Parte 2:**

• **Task 3:**

• **Objetivo:** Crear un modelo de detección de fraude en transacciones.

• **Salida:** Predicciones en formato JSON para ciertos transaction_id, siguiendo el formato en /predictions/predictions_3.json.

• **Task 4:**

• **Objetivo:** Desarrollar un modelo para predecir los gastos mensuales de los clientes durante los próximos tres meses.

• **Salida:** Predicciones en formato JSON, siguiendo el formato en /predictions/predictions_4.json.


**Parte 3:**

  

• **Task 5:**

• **Objetivo:** Implementar un agente de IA utilizando Langchain y el modelo llama3.2:1b hospedado localmente con Ollama.

• **Funcionalidad:** Procesar una entrada en lenguaje natural y generar un informe en PDF utilizando las funciones de Task 2.

• **Validación:** Tests en /tests/agent_test.py.

  

**Paso 2: Preparar el Entorno de Trabajo**

  

• **Python 3.10.12:** Asegúrate de que tu entorno está configurado con esta versión.

• **Instalar Dependencias:**

• Ejecuta pip install -r requirements.txt.

• Si necesitas instalar librerías adicionales, puedes hacerlo, pero **no elimines** las ya existentes en requirements.txt.

• **Estructura del Proyecto:**

• Sigue estrictamente la estructura de carpetas proporcionada.

• Familiarízate con la ubicación de cada archivo y directorio.

  

**Paso 3: Descarga y Exploración de Datos**

  

• **Descargar Datasets:**

• transactions_data.csv en data/raw/.

• mcc_codes.json en data/raw/.

• **Explorar las APIs:**

• Practica haciendo llamadas a las APIs de clientes y tarjetas.

• Comprende los parámetros necesarios (client_id) y el formato de la respuesta.

• **Análisis Exploratorio:**

• Carga los datasets en pandas DataFrames.

• Observa las columnas, tipos de datos y valores nulos.

• Haz algunas visualizaciones básicas si lo consideras útil.

  

**Paso 4: Abordar Task 1 (Consultas de Datos)**

  

**Objetivo:**

  

Responder a las cuatro consultas especificadas y guardar las respuestas en un archivo JSON.

  

**Pasos:**

  

1. **Integración de APIs:**

• Crea funciones en src/data/api_calls.py para obtener datos de clientes y tarjetas.

• Maneja posibles errores en las llamadas (e.g., clientes no encontrados).

2. **Cargar y Preprocesar Datos:**

• Carga transactions_data.csv y convierte las fechas a formato datetime.

• Combina los datos de transacciones con los datos de tarjetas y clientes según sea necesario.

3. **Realizar las Consultas:**

• **Consulta 1:** Encuentra el card_id con la fecha de expiración más lejana y el límite de crédito más bajo.

• **Consulta 2:** Identifica el client_id que se jubilará dentro de un año, con el puntaje de crédito más bajo y la deuda más alta.

• **Consulta 3:** Obtén el transaction_id de una compra en línea el 31 de diciembre con el monto absoluto más alto.

• **Consulta 4:** Determina qué cliente mayor de 40 años hizo más transacciones con una tarjeta Visa en febrero de 2016. Devuelve el client_id, card_id y el número total de transacciones.

4. **Guardar Resultados:**

• Asegúrate de que el archivo JSON cumple con el formato requerido.

• Guarda el archivo en la carpeta /predictions con el nombre adecuado.

  

**Paso 5: Implementar Task 2 (Funciones de Análisis de Datos)**

  

**Objetivo:**

  

Implementar las funciones en data_functions.py para analizar los datos de transacciones.

  

**Pasos:**

  

1. **Leer Descripciones:**

• Revisa las docstrings de cada función para entender qué se espera.

• Presta atención a los parámetros y valores de retorno.

2. **Implementar Funciones:**

• earnings_and_expenses**:** Calcula las ganancias y gastos totales para un client_id en un rango de fechas.

• expenses_summary**:** Proporciona un resumen de gastos por categoría para un cliente en un rango de fechas.

• cash_flow_summary**:** Genera un resumen del flujo de efectivo (entradas y salidas) para un cliente en un rango de fechas.

3. **Validación:**

• Utiliza los tests en /tests/statistics_test.py.

• Ejecuta python -m pytest tests/statistics_test.py para validar tus funciones.

  

**Paso 6: Desarrollar Task 3 (Modelo de Detección de Fraude)**

  

**Objetivo:**

  

Crear un modelo que clasifique transacciones como fraudulentas o no fraudulentas.

  

**Pasos:**

  

1. **Preparar Datos:**

• Carga las transacciones y las etiquetas de fraude desde train_fraud_labels.json.

• Combina las etiquetas con el dataset de transacciones.

2. **Preprocesamiento:**

• Maneja valores nulos y outliers.

• Codifica variables categóricas (e.g., One-Hot Encoding).

• Normaliza o estandariza variables si es necesario.

3. **Manejo de Desbalanceo:**

• Las transacciones fraudulentas suelen ser minoría.

• Considera técnicas como SMOTE, submuestreo o ajustar pesos en el modelo.

4. **Seleccionar y Entrenar el Modelo:**

• Comienza con modelos como Árboles de Decisión o Random Forest.

• Experimenta con modelos más avanzados como XGBoost o LightGBM.

5. **Evaluación:**

• Utiliza el Balanced Accuracy Score.

• Realiza validación cruzada para estimar la generalización del modelo.

6. **Generar Predicciones:**

• Predice para los transaction_id especificados en predictions_3.json.

• Guarda las predicciones en el formato requerido en /predictions.

  

**Paso 7: Desarrollar Task 4 (Modelo de Pronóstico de Gastos)**

  

**Objetivo:**

  

Predecir los gastos mensuales de los clientes para los próximos tres meses.

  

**Pasos:**

  

1. **Preparar Datos:**

• Agrupa las transacciones por cliente y mes, sumando los gastos (montos negativos).

• Crea una serie temporal para cada cliente.

2. **Seleccionar Modelo:**

• Considera modelos de series temporales como ARIMA, Prophet o incluso modelos basados en Machine Learning como LSTM si te sientes cómodo.

• Dado el número de clientes, puede ser eficiente utilizar un modelo global en lugar de uno por cliente.

3. **Entrenar el Modelo:**

• Divide tus datos en conjuntos de entrenamiento y validación.

• Asegúrate de no hacer trampa temporal (no usar datos futuros para predecir el pasado).

4. **Evaluación:**

• Utiliza el R2 Score para evaluar las predicciones.

5. **Generar Predicciones:**

• Predice los gastos para los próximos tres meses a partir de la última fecha de transacción de cada cliente.

• Guarda los resultados en el formato requerido en /predictions.

  

**Paso 8: Implementar Task 5 (Agente de IA)**

  

**Objetivo:**

Crear un agente que, dado un prompt en lenguaje natural, genera un informe en PDF utilizando las funciones de Task 2.


**Pasos:**

1. **Configurar Langchain y Ollama:**

• Instala Ollama y descarga el modelo llama3.2:1b.

• Asegúrate de que el modelo está funcionando localmente.

2. **Implementar el Agente:**

• En src/agent/agent.py, desarrolla la función run_agent().

• El agente debe:

• Extraer start_date y end_date del prompt.

• Invocar las funciones de Task 2 con los parámetros adecuados.

• Generar un informe basado en los resultados.

3. **Generar el Informe en PDF:**

• Utiliza una librería como reportlab o weasyprint para crear el PDF.

• Guarda el informe en /reports/ con un nombre descriptivo.

4. **Validación:**

• Ejecuta los tests en /tests/agent_test.py con python -m pytest tests/agent_test.py.

  

**Paso 9: Validación y Pruebas Finales**


• **Ejecutar Todos los Tests:**

• Asegúrate de que todos los tests pasan correctamente.

• **Revisión de Código:**

• Revisa tu código para mejorar legibilidad y eficiencia.

• Agrega comentarios y docstrings donde sea necesario.

• **Verificar Formatos:**

• Confirma que todos los archivos JSON y PDFs cumplen con los formatos requeridos.

  

**Paso 10: Preparar la Entrega**

  

• **Commit y Push:**

• Escribe mensajes de commit claros y descriptivos.

• Asegúrate de que todo el código y resultados están en el repositorio.

• **Verificar Instrucciones de Entrega:**

• Revisa las guías de envío para asegurarte de que no falta nada.
 

**Recursos Adicionales**


• **Manipulación de Datos:**

• Documentación de [Pandas](https://pandas.pydata.org/docs/).

• **Modelos de Machine Learning:**

• Documentación de [Scikit-learn](https://scikit-learn.org/stable/).

• **Series Temporales:**

• [Statsmodels](https://www.statsmodels.org/stable/tsa.html) para modelos ARIMA.

• [Prophet](https://facebook.github.io/prophet/) de Facebook.

• **Pruebas Unitarias:**

• Guía de [Pytest](https://docs.pytest.org/en/7.1.x/).

• **Generación de PDFs:**

• [ReportLab](https://www.reportlab.com/docs/reportlab-userguide.pdf).

• **Langchain y Ollama:**

• Documentación de [Langchain](https://langchain.readthedocs.io/en/latest/).

• Guía de [Ollama](https://ollama.ai/).


**Estoy Aquí para Ayudarte**

Si en algún momento tienes dudas o necesitas profundizar en algún tema, no dudes en preguntarme. Podemos revisar juntos conceptos, resolver problemas específicos o buscar recursos adicionales.

  ¡Manos a la obra y mucho ánimo en este reto!