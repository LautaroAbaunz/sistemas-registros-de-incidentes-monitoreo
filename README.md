
# Sistema Web de Registro de Incidentes de Monitoreo y Gestión de Intervenciones Operativas

Proyecto del **Trabajo Práctico Integrador y Progresivo (TPI)** de *Organización Empresarial*, Tecnicatura Universitaria en Programación a Distancia (TUP AD), Universidad Tecnológica Nacional (UTN).

## Descripción del sistema

Sistema web de gestión interna para el Centro de Monitoreo de la Secretaría de Seguridad del Municipio de Pilar. El operador registra cada novedad (un *suceso*), se gestiona el despacho de un móvil de patrullaje o de guardia urbana, se asienta el resultado de la intervención y el sistema calcula automáticamente la productividad de cada operador y de cada guardia (2 puntos por detección simple y 5 por intervención positiva), en reemplazo de la carga manual en planillas.

La detección por video (cámaras, lectores de patentes y alertas de videoanálisis) queda **fuera del alcance**: se considera un insumo externo. El proyecto se concentra en la lógica administrativa y operativa que ocurre a partir de que llega la novedad.

## Integrantes

- Abaunz Lautaro

## Enlaces

- Tablero de gestión (GitHub Projects): (https://github.com/users/LautaroAbaunz/projects/3/views/1)
- Documentación técnica: carpeta [`docs/`](docs/)

## Contenido de `docs/`

| Archivo | Qué contiene |
|---|---|
| [`planificacion-y-diagnostico.md`](docs/planificacion-y-diagnostico.md) | Sistema abierto, FODA, objetivo y metas, diagrama de Gantt (Entregas 1 y 2) |
| [`organigrama.md`](docs/organigrama.md) | Organigrama del área técnica con la Asesoría Legal como staff (Entrega 3) |
| [`diccionario-de-datos.md`](docs/diccionario-de-datos.md) | Cuatro entidades con sus campos, tipos y restricciones (Entrega 3) |
| [`bpmn-proceso.md`](docs/bpmn-proceso.md) | Diagrama BPMN del proceso con pools, lanes y compuertas (Entrega 4) |
| [`historias-de-usuario.md`](docs/historias-de-usuario.md) | Tres historias de usuario con criterios de aceptación (Entrega 4) |
| [`indicadores-de-control.md`](docs/indicadores-de-control.md) | Indicadores y estándares de desempeño para la auditoría técnica (Entrega 4) |

## Flujo de trabajo del repositorio

- `main` contiene la versión revisada de la documentación.
- Cada documento se trabaja en una **rama secundaria** (`feature/diccionario-datos`, `feature/bpmn-proceso`, `feature/historias-usuario`, `feature/indicadores-control`) y se incorpora a `main` mediante un **Pull Request** con revisión de un par (auto revicion en este caso ya que me encuentro desarrollandolo de manera individual).
- Los **mensajes de commit** siguen el formato `tipo: descripción en presente`, por ejemplo `docs: agrega diccionario de datos con cuatro entidades`.
- Cada historia de usuario es un *Issue* y se vincula con el Pull Request que la resuelve.

## Indicadores de control

Los indicadores y estándares para auditar el sistema están en [`docs/indicadores-de-control.md`](docs/indicadores-de-control.md).

## Declaración de Uso de IA
 
Se usó un asistente de IA generativa  como apoyo para estructurar y redactar borradores. No reemplazó el criterio propio: el caso, los datos y las decisiones surgen del trabajo real del autor en el Centro de Monitoreo de la Secretaría de Seguridad de Pilar. Los valores numéricos de las metas y de los indicadores son **estimaciones de diseño**, no mediciones reales de la Secretaría.

### Prompts utilizados y por qué

| Entrega | Qué se le pidió (resumen) | Para qué | Control crítico |

| 1 | Pasar la consigna y la devolución de la profesora y pedir correcciones | Reordenar el modelado como sistema abierto (entradas, procesos, salidas, retroalimentación, límites y ambiente), armar el esquema de bloques y acotar el software a un sistema web de registro de incidentes | Se contrastó el borrador con el conocimiento propio del Centro de Monitoreo y se corrigieron datos |
| 2 | Pedir un borrador de FODA, objetivo y metas, y Gantt sobre el sistema acotado | Tener un primer borrador de la matriz, de las metas y del cronograma | Se verificó que el FODA separara factores internos del equipo técnico de factores externos, y se ajustaron los valores de las metas |
| 3 | Pasar la foto del organigrama real y tras integrar al equipo y staff correspondiente | con el fin de pasar el organigrama real de una foto a de forma digital acorde a los demás cuadros | se contrasto el resultado con el organigrama real de acuerdo a el manual de procedimientos operativos y experiencia propia |
| 4 | Un borrador del diagrama BPMN, de la documentación del repositorio, de las historias de usuario y de los indicadores | Tener una base para completar la entrega | se reviso y modifico este borrador

### Correcciones humanas sobre los resultados de la IA

1. **Cantidad de cámaras:** el borrador tomó "150 cámaras" como total, pero ese dato correspondía a lo que mira cada operador; se corrigió a unas 3.000 cámaras en total.
2. **Entradas y salidas:** se agregaron los botones de pánico y las alarmas como vías de ingreso de novedades, y la medición de productividad por guardia, que el borrador no contemplaba.
3. **Misión y control:** se agregó el área de salud entre las áreas con las que se coordina y los auditores entre las instancias de control.
4. **Metas:** la IA propuso 50.000 registros como valor de diseño; se reemplazó por 9.000, y se precisó que el tiempo de 2 segundos aplica luego de que el operador redacta el suceso.
5. **FODA:** se sumó a la estrategia de supervivencia la previsión de contar con documentación suficiente para retomar el proyecto si se detiene.
6. **Entrega 3:** la primera versión se elaboró sin esta asistencia, usando otra herramienta de IA para el cuadro del organigrama y el primer planteo de la tabla, y se adaptó con datos reales del trabajo (medios de ingreso como GUP, GUM, 911 y LPR, y ejemplos de eventos).

### Limitaciones reconocidas

- Los tiempos, cantidades y estándares de las metas y de los indicadores son estimaciones de diseño.
- Los roles de usuario y los campos del diccionario de datos son propuestas que deberían validarse con el área.
