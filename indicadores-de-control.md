# Indicadores de control y estándares de desempeño (Entrega 4)

El **control** compara lo que realmente ocurre con un estándar y corrige los desvíos. Estos indicadores sirven para la auditoría técnica del sistema una vez implementado. Si un indicador no alcanza su estándar, el responsable analiza la causa y se registra una tarea correctiva en el tablero.

| Código | Indicador | Estándar | Cómo se mide | Frecuencia y responsable |
|---|---|---|---|---|
| IC-1 | Tiempo de guardado de un suceso | Al menos el 95% de los guardados tarda menos de 2 segundos | Pruebas de carga y registro de tiempos en producción | Antes de implementar y luego mensual; equipo de desarrollo |
| IC-2 | Tiempo de consultas y reportes | Menos de 5 segundos con al menos 9.000 registros | Consultas de prueba sobre una base cargada | Antes de implementar y luego trimestral; equipo de desarrollo |
| IC-3 | Automatización del puntaje | 100% de las intervenciones con puntaje calculado por el sistema dentro de los 3 meses de la implementación | Intervenciones con registro de productividad ÷ intervenciones cerradas | Mensual; Supervisor |
| IC-4 | Completitud de los registros | 100% de los sucesos con todos los campos obligatorios completos | Sucesos completos ÷ sucesos totales | Mensual; Encargado de Turno / Sala |
| IC-5 | Tiempo entre el registro y el despacho de un móvil | A fijar con la Dirección luego de medir una línea base durante las primeras 4 semanas de uso | Diferencia entre `fecha_hora_despacho` y `fecha_hora` del suceso | Mensual; Supervisor |
| IC-6 | Seguridad y acceso a los datos | 0 accesos de usuarios sin el rol autorizado y 100% de los cambios con registro de actividad (usuario, fecha y acción) | Revisión de accesos y del registro de actividad | Trimestral; Supervisión de Técnica con la Asesoría Legal |
| IC-7 | Calidad del software | 100% de los casos de prueba críticos aprobados antes de implementar (registro, despacho, cierre y puntaje) | Resultado de las pruebas de calidad | Antes de implementar; QA / Tester |
