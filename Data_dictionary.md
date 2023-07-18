# "Anonymous Bank" Call-Center DataSet

Este documento describe caso de negocio basado en un Call Center de un Banco: “Anonymous Bank” en Israel. El dataset contiene las llamadas registradas durante 12 meses (desde el 01/01/99 hasta el 31/12/99).

## Descripción General

El call center de "Anonymous Bank" provee varios servicios diferentes:
- Información y transacciones sobre cheques y cuentas de ahorros, de sus clientes bancarios.
- Respuesta de voz generada por computadora con información sobre las cuentas de los clientes (a través del dispositivo VRU = Voice Response Unit (unidad de respuesta de voz). Una unidad de respuesta de voz (VRU) es un sistema de contestador telefónico automático que posee un hardware y software que permite a la persona que llama navegar a través de una serie de mensajes pregrabados y utilizar un menú de opciones mediante los botones de un teléfono o el reconocimiento de voz.)
- Brindar información a prospectos de clientes. 
- Soporte a los clientes del web-site de "Anonymous Bank" (clientes que acceden al Home Banking)

## Capacidad del Call Center

El call center esta conformado por:
- 8 posiciones de agentes para llamadas de clientes y prospectos
- 1 posición de supervisor
- 5 posiciones de agentes para llamadas para soporte de internet home banking (en un cuarto adjac room)

## Horario de atención

Durante los dias de semana (Domingo a Jueves), el call center atiende desde las 7:00am a la medianoche. 

Durante el fin de semana (Viernes a Sábado), cierra a las 14 hs del Viernes y reabre a las 20:00 del Sábado.

El servicio automático (VRU) opera los 7 días de la semana, 24 horas al día (7x24).

## Descripción de la Estructura de Datos
El dataset contiene toda la información del Call Centre de un año calendario: Enero 1999 a Diciembre 1999.

Cada registro / fila del dataset, contiene una llamada (entre 20,000 a 30,000 llamadas por mes).

Cada registro / fila contiene 17 campos / columnas, de los cuales se describe su contenido a continuación:

1. **vru+line - 6 dígitos**: Cada llamada telefónica entrante es ruteada a través del VRU. Hay 6 VRUs etiquetados desde  AA01 a AA06. Cada VRU tiene varias líneas etiquetadas de 1 a 16. Hay un total de 65 líneas. Cada llamada es asignada a un número de VRU y a un número de línea.
2. **Call_id - 5 dígitos**: A cada llamada telefónica entrante se le asigna un “call id”. Aunque son diferentes, los identificadores no son necesariamente consecutivos por estar asignado a diferentes VRUs.
3. **Customer_id - 0 a 12 dígitos**: Es la identificación del cliente. Es única por cliente; si el ID es cero, es porque el sistema no pudo identificar a la persona que realiza la llamada (por ejemplo para el caso de los prospectos no se identifican).
4. **Priority - 1 digito**:
- Hay dos tipos de prioridades: 0 y 1 indican clientes no identificados o clientes regulares (los detallaremos más adelante), 2 indica clientes de Alta Prioridad.
- Los clientes son servidos en orden según el “Tiempo en Cola” ("Time in Queue").
- A los clientes de Alta Prioridad se les asigna un tiempo de espera de 1.5 minutos al comienzo de su llamada (esto les permite avanzar en la posición de la cola de llamadas). También están exentos de pagar un fee mensual, que los clientes regulares deben pagar.
- No se ha informado a los clientes sobre la existencia de prioridades.
- Hasta Agosto de 1996, todos los clientes tenían la misma prioridad: 0. Las prioridades 1 y 2 fueron incorporadas el 1° de Agosto de 1996. Todavía hay clientes con prioridad 0, pero son tratados como si fueran de prioridad 1. (se definió que los clientes con prioridad 0 corresponden a clientes de prioridad 1 que no realizaron Upgrade a Alta Prioridad (prioridad 2).
- Debido a un error en el sistema, el cliente I.D. no fue registrado para aquellos que no esperaron en la cola, Por lo tanto, su prioridad es 0.
6. **Type(2 digits)**: Hay 6 tipos diferentes de servicio:
- PS = Actividad Regular
- PE = Actividad Regular en inglés
- IN = Actividad / Consulta por internet
- NE = Actividad por Acciones (stock exchange)
- NW = Cliente potencial (prospecto) solicitando información
- TT = clientes que dejan un mensaje pidiendo al banco que le devuelvan su llamado pero que cuando el sistema automático devuelve el llamado, el agente pasó a estado “ocupado”, dejando al cliente en espera en la cola.
6. **Date - 6 dígitos**: año-mes-día
7. **vru_entry - 6 dígitos**: Hora en que la llamada telefónica ingresa al call center. Más específicamente, cada cliente que llama debe identificarse primero lo que se realiza proporcionando a la VRU la ID del cliente. Por lo tanto, esta es la hora en que la llamada ingresa a la VRU.
8. **vru_exit - 6 dígitos**: Hora de salida de la VRU: 
- A la cola
- O directamente para recibir el servicio.
- O para dejar el Sistema (abandono).
9. **vru_time - 1 a 3 dígitos**: Tiempo (en segundos) de espera en la VRU (calculada como vru_time= exit_time – entry_time).
10. **q_start - 6 dígitos**: Hora en la que se une a la cola. (la llamada queda “en espera”). Este valor es 00:00:00, para clientes que llegan a ponerse en la cola (abandonan cuando están en la VRU).
11. **q_exit - 6 digits**: Tiempo (en segundos) en salir de la cola: ya sea porque recibe el servicio o por qué abandona el llamado.
12. **q_time - 1 to 3 digits**: Tiempo de espera en la cola (calculado por q_time = q_exit – q_start)
13. **Outcome - 4,5 o 7 digitos**: Hay tres posibles salidas por cada llamada:
- AGENT: se dio servicio
- HANG: se cortó la llamada y no se dió servicio
- PHANTOM: una llamada en la que virtualmente se ignora lo que sucedió(afortu- nadamente son pocas llamadas en esta situación).
14. **ser_start - 6 digitos**:Hora de comienzo del servicio por un agente.
15. **ser_exit - 6 digitos**: Hora del servicio del servicio por un agente.
16. **ser_time - 1 to 3 digitos**: Duración del servicio en segundos (calculada como ser_time = ser_exit – ser_start)
17. **Server - text**: Nombre del cliente que atendió la llamada. Este campo es NO_SERVER, si el servicio no fue provisto.
