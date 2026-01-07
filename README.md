## Análisis de Deserción de Clientes (Churn) - TelecomX 📉
Este repositorio contiene un análisis exhaustivo de la deserción de clientes (Churn) para la empresa de telecomunicaciones ficticia TelecomX. El objetivo principal es identificar los factores clave que influyen en que los clientes decidan abandonar el servicio, y proponer estrategias accionables para mitigar esta tasa de abandono.

## 🚀  Objetivo del Proyecto
El desafío de la deserción de clientes es crítico en el sector de las telecomunicaciones. Este proyecto busca:

Comprender el perfil de los clientes que desertan y los que permanecen.
Identificar las variables numéricas y categóricas que tienen un mayor impacto en la decisión de un cliente de cancelar su servicio.
Proponer recomendaciones estratégicas basadas en los hallazgos para mejorar la retención de clientes.
## 💾 Fuente de Datos
Los datos fueron extraídos de un archivo JSON público alojado en GitHub:

URL del JSON: https://raw.githubusercontent.com/ingridcristh/challenge2-data-science-LATAM/refs/heads/main/TelecomX_Data.json

## 🛠️ Pasos Realizados en el Notebook
1. Extracción y Carga de Datos

Se cargaron los datos directamente desde la URL del archivo JSON.
Se utilizó pd.json_normalize para aplanar la estructura anidada del JSON, convirtiendo campos como customer, phone, internet y account en columnas individuales (customer.gender, phone.PhoneService, etc.).

2. Tratamiento y Limpieza de Datos

Renombramiento de Columnas: Todas las columnas fueron renombradas a nombres más legibles y en español (ej. Churn a Deserción, customer.gender a Género, account.Charges.Total a Cargos_totales).
Gestión de Valores Nulos y Vacíos:
Se identificaron cadenas vacías ('') en algunas columnas (Deserción, Cargos_totales) y se reemplazaron por np.nan para un manejo consistente de los valores faltantes.
La columna Cargos_totales se convirtió de tipo object a float64, manejando posibles errores de conversión (errors='coerce').
Se eliminaron las filas que contenían valores NaN en las columnas Deserción y Cargos_totales para asegurar la integridad de los datos clave (reduciendo el dataset de 7267 a 7032 registros).
Creación de Nuevas Variables: Se creó la columna Cuentas_Diarias calculando los Cargos_mensuales divididos por 30.
Traducción de Categorías: Se tradujeron los valores categóricos al español en varias columnas (ej. Male/Female a Hombre/Mujer, tipos de contrato, métodos de pago, servicios de internet).

3. Análisis Exploratorio de Datos (EDA)

Se realizó un análisis descriptivo y visual extenso para identificar patrones:

Tasa General de Deserción: Se encontró una tasa de deserción del 26.6%.
Análisis por Variables Numéricas:
Antigüedad: Los clientes que desertan tienen una antigüedad promedio significativamente menor (17.98 meses) que los que permanecen (37.65 meses).
Cargos Mensuales: Los clientes que desertan tienden a tener cargos mensuales promedio más altos ($74.44) que los que no desertan ($61.31).
Cargos Totales: Los clientes que desertan tienen cargos totales promedio más bajos ($1531.80) que los que no desertan ($2555.34).
Análisis por Variables Categóricas:
Contrato: Los contratos mensuales muestran la tasa de deserción más alta (42.71%), frente a contratos anuales (11.28%) y bianuales (2.85%).
Método de Pago: El cheque electrónico se asocia con la tasa de deserción más alta (45.29%).
Dependientes: Los clientes sin dependientes tienen una tasa de deserción más alta (31.28%) que aquellos con dependientes (15.53%).
Género: No se encontró una diferencia significativa en la tasa de deserción por género.


## 📊 Conclusiones e Insights Principales

El análisis de deserción revela que los clientes más propensos a abandonar el servicio se caracterizan por:

Ser clientes relativamente nuevos: Una baja antigüedad es un fuerte indicador de deserción.
Tener contratos mensuales: La flexibilidad de los contratos mensuales conlleva un mayor riesgo de abandono.
Utilizar el Cheque Electrónico como método de pago: Sugiere una menor vinculación o posibles problemas en el proceso de pago.
Pagar cargos mensuales más altos: Indica una posible sensibilidad al precio o una percepción de falta de valor por el coste.
No tener dependientes: Los clientes sin responsabilidades familiares pueden tener menos ataduras con el servicio.
Estos hallazgos son fundamentales para entender los puntos de fricción y las características de los clientes en riesgo.

## 💡 Recomendaciones Estratégicas
Basado en los insights obtenidos, se proponen las siguientes estrategias para reducir la deserción:

Programas de Fidelización para Clientes Nuevos: Implementar incentivos y seguimiento proactivo durante los primeros 12-18 meses de servicio para fortalecer el vínculo y asegurar la satisfacción.
Promoción de Contratos a Largo Plazo: Ofrecer descuentos y beneficios exclusivos para incentivar la migración de contratos mensuales a planes anuales o bianuales.
Revisión del Proceso de Pago Electrónico: Investigar las causas de la alta deserción asociada al cheque electrónico y considerar incentivos para que los clientes adopten métodos de pago más estables y automáticos.
Evaluación de la Relación Precio-Valor: Para clientes con cargos mensuales elevados, asegurar que perciben un valor proporcional a su gasto, mediante ofertas personalizadas o mejora en la comunicación del valor de los servicios.
Ofertas Dirigidas a Clientes sin Dependientes: Desarrollar campañas y paquetes específicos que resalten beneficios relevantes para este segmento, como flexibilidad o servicios de entretenimiento individual.

## 💻 Tecnologías Utilizadas
Python
Pandas (para manipulación y análisis de datos)
Matplotlib (para visualizaciones)
Seaborn (para visualizaciones estadísticas)


