# **Análisis de las Operaciones Realizadas por el Call Center de un Banco**

En este proyecto, se me asignó la tarea de definir, construir y presentar un Dashboard que permita medir los niveles de calidad de servicio, eficiencia y productividad del Call Center de un banco para el año 1990. Para ello, se proporicionó un dataset con todas las llamadas realizadas a lo largo del año y se pidió definir los KPIs adecuados para poder medir los objetivos propuestos.

Cabe resaltar que el principal objetivo del proyecto es demostrar conocimientos en el uso de librerías como Pandas, Matplotlib y Seaborn para la visualización y menejo de datos en Python, así como en el uso de herramientas como Google Loocker y Power Bi para el diseño de Dashboars interactivos.

## **Preguntas**

Asimismo, se solicitó hacer una análisis de los datos proporcionados para responder de forma escritas las siguientes preguntas de negocio:

* ¿Cuál es el nivel de servicio para los clientes Prioritarios?
* ¿Damos un mejor servicio que a los clientes normales?
* ¿Qué volumen de llamadas atendemos?
* ¿Cuáles son los cuellos de botella? ¿En qué días? ¿En qué bandas horarias?
* ¿Cómo es la eficiencia y productividad de nuestros agentes?
* ¿Hay clientes recurrentes en el uso del servicio?
* ¿Cuáles son los tipos de servicio más recurrentes?

## **Análisis Escrito**

El análisis completo se encuentra disponible en el archivo [Analist.ipynb](https://github.com/Rickhersd/Call_center_data_analist/blob/main/Analist.ipynb) en la raíz del proyecto, e incluye la explicación detallada del procedimiento junto a las gráficas obtenidas.

De igual forma, además de responder las preguntas plateadas, se obtuvieron las siguientes conclusiones:

1. **Calidad de los datos**: Se identificaron numerosas inconsistencias en los datos proporcionados por el Call Center. Se detectaron algunos outliers con facilidad, pero otro grupo significativo de posibles outliers no pudo ser claramente clasificado debido al alto volumen de llamadas. Además, se encontraron categorías mal escritas en los registros.

2. **Servicio a clientes de alta prioridad**: Se confirmó que los clientes de alta prioridad reciben un mejor servicio en comparación con los clientes regulares en cuanto a los tiempos de cola. Sin embargo, se considera que se puede mejorar aún más, apuntando a un tiempo de espera promedio entre 20 y 25 segundos, en lugar de los 32 segundos actuales.

3. **Cuellos de botella**: No se identificaron cuellos de botella significativos en las bandas horarias.

4. **Llamadas fuera del horario laboral**: Se detectaron llamadas que ocurrieron fuera del horario laboral, es decir, después del cierre y antes de la apertura del Call Center. Sería necesario revisar la razón de esto, por si es algun fallo en el sistema de registro.

5. **Volumen de llamadas**: El Call Center atiende un volumen de llamadas que oscila entre 31,000 y 42,000 llamadas mensuales, con un promedio de 36001 llamadas por mes.

6. **Pérdida de volumen en ciertos meses**: Se observó una disminución considerable del volumen de llamadas en los meses de Abril y Septiembre, donde se registró una pérdida de más del 15% con respecto al mes anterior con una drástica corrección al mes siguiente.

7. **Productividad de los agentes**: La información dada por el dataset y el diccionario de datos es muy inconsistente entre sí, con muchos datos mal escritos y outliers. Asimismo, el servicio dado por los agentes tampoco se consideró rápido, en especialmente para los clientes de alta prioridad, los cuales tuvieron llamadas en promedio de hasta tres minutos y medio.

8. **Sistema de retroalimentación**: Se recomendó instalar un sistema de retroalimientación en el que los usuarios puedan evaluar la caldiad del servicio del agente para que el Call Center tenga más control sobre la calidad individual de cada uno. Por ejemplo: encuestas por operadora o formularios web al finalizar la llamada.

9. **Actualización del Diccionario de Datos**: Se encontró que parte de los datos proporcionados en el Diccionario de Datos no coinciden con los datos presentes en el Dataset, como el volumen de llamadas mensual o el total de llamadas al año. Por lo tanto, se sugiere actualizar el diccionario para mantenerlo coherente con los datos reales.

10. **Demanda de servicios**: Se identificó que el servicio "Regular" es el más destacado en el Call Center, seguido por los servicios para clientes potenciales, consultas por internet y actividades de acciones. El servicio dado en inglés es el menos demandado.

11. **Clientes recurrentes**: Se confirmó la existencia de clientes regulares, algunos con más de 25 llamadas realizadas durante el año, e incluso se encontraron clientes con más de 100 llamadas. También se detectaron clientes con una actividad sospechosa al tener más de 200 llamadas realizadas durante el año, lo que sugiere la necesidad de revisar el sistema para verificar la identificación adecuada de los clientes o posibles problemas en el sistema.

## **Dashboard**

Se subirá próximamente