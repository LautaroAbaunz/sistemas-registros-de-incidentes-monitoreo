# Historias de usuario (Entrega 4)

Formato: *Como [rol], quiero [funcionalidad], para [beneficio]*. Estados en el tablero: **Por Hacer**, **En Progreso**, **Listo**.

## HU-1: Registrar un suceso

**Como** operador de monitoreo, **quiero** registrar un suceso con su fecha y hora, su tipo de evento y el medio por el que llegó la novedad, **para** que quede documentado y pueda solicitar un móvil al Despacho.

Criterios de aceptación:

1. Al guardar, el sistema asigna un `numero_de_suceso` único y deja el estado en *abierto*.
2. No permite guardar si faltan `fecha_hora`, `tipo_evento` o `ingreso_de_novedad`.
3. `ingreso_de_novedad` solo admite los medios previamente establecidos.
4. El sistema confirma el guardado en menos de 2 segundos en al menos el 95% de los casos.
5. El suceso queda visible para el Despacho y se puede buscar por su número.

## HU-2: Cerrar la intervención desde la patrulla

**Como** personal de patrulla (móvil en calle), **quiero** registrar el resultado de la intervención del suceso que me asignaron, **para** que el suceso se cierre y se pueda calcular la productividad.

Criterios de aceptación:

1. El móvil ve el suceso que se le asignó, con su tipo de evento y su fecha y hora.
2. Registra el resultado (positivo o negativo) y, si corresponde, observaciones de lo constatado.
3. Al registrar el resultado se guarda la `fecha_hora_cierre` y el suceso pasa a estado *cerrado*.
4. Si no hay móvil disponible, el Despacho reasigna uno cuando haya uno libre.

## HU-3: Ver la productividad por operador y por guardia

**Como** supervisor, **quiero** ver el puntaje acumulado por operador y por guardia en un período, **para** evaluar el desempeño con datos objetivos, sin cargar planillas a mano.

Criterios de aceptación:

1. El puntaje (2 por detección simple, 5 por intervención positiva) se calcula automáticamente al cerrar la intervención.
2. El reporte muestra los puntos acumulados por operador y por guardia en el período elegido.
3. El reporte responde en menos de 5 segundos con 9.000 registros.
4. Solo los roles de supervisión acceden al reporte.
