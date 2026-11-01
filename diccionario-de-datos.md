# Diccionario de datos inicial (Entrega 3)

Cuatro entidades relacionadas entre sí. **PK** es la clave primaria (identifica de forma única cada registro) y **FK** la clave foránea (guarda el identificador de otra entidad para vincularlas).

## Suceso

| Campo | Tipo de dato | Longitud / restricción | Descripción funcional |
|---|---|---|---|
| numero_de_suceso | Integer | PK, único | Identifica cada suceso y permite llevar la cuenta de las novedades registradas |
| fecha_hora | DateTime | Obligatorio | Momento en que se registró la novedad |
| tipo_evento | String | Hasta 60 caracteres, obligatorio; modalidad previamente establecida | Tipo de novedad detectada (por ejemplo, ingreso en finca, tentativa de robo o emergencia civil por quema de pastizales) |
| estado | String | Obligatorio (abierto, en curso o cerrado) | Situación actual del suceso |
| ingreso_de_novedad | String | Obligatorio; solo los medios previamente establecidos | Medio por el cual se tomó conocimiento del hecho (Operador, GUP, GUM, 911, LPR, etc.) |
| id_operador | Integer | FK a Operador, obligatorio | Operador que registró el suceso |

## Operador

| Campo | Tipo de dato | Longitud / restricción | Descripción funcional |
|---|---|---|---|
| id_operador | Integer | PK, autoincremental | Identificador único del operador en el sistema |
| nombre_completo | String | Hasta 100 caracteres, obligatorio | Nombre y apellido del operador |
| cargo | String | Hasta 40 caracteres, obligatorio | Cargo del operador dentro de la sala de monitoreo |
| guardia | String | Hasta 20 caracteres, obligatorio | Guardia a la que pertenece; permite medir la productividad por guardia |
| activo | Boolean | Obligatorio, por defecto verdadero | Indica si el operador está en actividad y puede registrar sucesos |

## Intervencion_Movil

| Campo | Tipo de dato | Longitud / restricción | Descripción funcional |
|---|---|---|---|
| id_intervencion | Integer | PK, autoincremental | Identificador único de la intervención |
| numero_de_suceso | Integer | FK a Suceso, obligatorio | Suceso que originó el despacho |
| movil_asignado | String | Hasta 20 caracteres, obligatorio | Identificación del móvil policial o de guardia urbana despachado |
| fecha_hora_despacho | DateTime | Obligatorio | Momento en que se despacha el móvil; comparado con la fecha del suceso, permite medir el tiempo de respuesta |
| fecha_hora_cierre | DateTime | Vacío hasta que se asienta el resultado | Momento en que se registra el resultado de la intervención |
| resultado | String | Positivo o negativo; vacío hasta el cierre | Resultado de la intervención |
| observaciones | String | Hasta 255 caracteres, opcional | Detalle de lo constatado por el móvil |

## Registro_Productividad

| Campo | Tipo de dato | Longitud / restricción | Descripción funcional |
|---|---|---|---|
| id_registro | Integer | PK, autoincremental | Identificador único del registro de puntaje |
| id_operador | Integer | FK a Operador, obligatorio | Operador al que se le asigna el puntaje |
| id_intervencion | Integer | FK a Intervencion_Movil, único, obligatorio | Intervención que origina el puntaje; cada intervención genera un solo registro |
| puntos | Integer | Solo 2 o 5; lo calcula el sistema | Puntos asignados: 2 por detección simple y 5 por intervención positiva |
| fecha | Date | Obligatorio | Fecha en que se asigna el puntaje; permite sumar por período, por operador y por guardia |

## Relaciones

Un Operador registra muchos Sucesos; un Suceso puede tener una o más Intervenciones de móvil; y cada Intervención genera un único Registro de productividad, que se asigna al operador que registró el suceso.
