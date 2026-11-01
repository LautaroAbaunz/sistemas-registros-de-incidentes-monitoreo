# Proceso de negocio en BPMN (Entrega 4)

Proceso que el sistema web automatiza: **registro y gestión de un suceso**, desde que llega una novedad hasta que se cierra y se asigna el puntaje.

![Diagrama BPMN](img/bpmn-proceso.png)

## Pool y lanes

- **Un único pool:** la Secretaría de Seguridad. El origen de la novedad (llamados al 911, botones de pánico, aplicación de alertas, alarmas, cámaras y lectores de patentes) se representa con el evento de inicio.
- **Tres lanes:** Operador de monitoreo, Sistema web (comportamiento automatizado, tareas sombreadas) y Despacho / Móvil en calle.

## Flujo estándar

1. Llega o se detecta una novedad y el operador la verifica.
2. Si es un hecho real, el operador la registra en el sistema web y el sistema guarda el suceso con su número y estado *abierto*.
3. El operador solicita un móvil al Despacho, que lo despacha a constatar el hecho.
4. El Despacho / Móvil en calle registra el resultado de la intervención.
5. El sistema registra los puntos (5 si la intervención fue positiva, 2 si fue una detección simple) y cierra el suceso.

## Compuertas exclusivas de decisión (excepciones)

| Compuerta | Si la respuesta es "No" |
|---|---|
| ¿Es un hecho real? | La novedad se descarta y el proceso termina sin registrar un suceso |
| ¿Hay móvil disponible? | El Despacho reasigna un móvil cuando haya uno libre y vuelve a consultar la disponibilidad |
| ¿Intervención positiva? | Se registran 2 puntos (detección simple) en lugar de 5 |

## Articulación con el diccionario de datos

| Tarea del BPMN | Lane | Entidad y campos que usa |
|---|---|---|
| Registrar el suceso en el sistema web | Operador | Suceso: fecha_hora, tipo_evento, ingreso_de_novedad, id_operador |
| Guardar el suceso | Sistema web | Suceso: numero_de_suceso (se genera) y estado = abierto |
| Despachar el móvil a constatar el hecho | Despacho / Móvil en calle | Intervencion_Movil: numero_de_suceso, movil_asignado, fecha_hora_despacho; Suceso: estado = en curso |
| Reasignar un móvil cuando haya uno libre | Despacho / Móvil en calle | Intervencion_Movil: movil_asignado |
| Registrar el resultado de la intervención | Despacho / Móvil en calle | Intervencion_Movil: observaciones, resultado, fecha_hora_cierre |
| Registrar 5 o 2 puntos y cerrar el suceso | Sistema web | Registro_Productividad: id_operador, id_intervencion, puntos, fecha; Suceso: estado = cerrado |
