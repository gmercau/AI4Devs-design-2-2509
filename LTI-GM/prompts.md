### Prompts Creación del Backlog de Producto LTI:

## User Stories ##

### prompt 1
> Sos un experto planificador de proyectos. Dado el objetivo de producto LTI adjuntado y las funcionalidades principales determinadas en el mismo, define las historias de usuario principales siguiendo el formato  estándar tambien adjuntado.

### prompt 2
> Analiza las funcionalidades existentes del sistema LTI para identificar los cinco problemas más comunes que los usuarios podrían enfrentar y sugiere mejoras. Solo enumera los problemas, no generes imformacion extra.

### prompt 3
> De los 5 problemas mas comunes establecidos genera una historia de usuario para vada uno. Sigue el formato establecido.

### prompt 4
> De todas las historias de usuarios generadas (historias de usuario principales, hsitorias de usuarios por problemas comunes), selecciona las mas relevantes para generar un backlog inicial. Solo mencionalas no hagas ningun analisis extra.

### prompt 5
> Valida las User Stories antes selecionadas, identificando posibles inconsistencias, lagunas o conflictos en los requisitos. Solo incluye la informacion pedida.

### prompt 6
> Dame una versión ajustada de estas historias ya corregidas.

### prompt 7
> Realiza una revisión de las User Stories seleccionadas, proporcionando recomendaciones para mejorar la claridad, coherencia y completitud de las historias. Aplicalas cuando corresponda.


## Backlog de producto ##

### prompt 1
> Raliza la priorización del Backlog de Producto LTI, para ello considera las historias de usuario seleccionadas anteriormente. Estima considerando los siguentes factores para la Priorización del Backlog (genera una tabla markdown):
> 1-Impacto en el usuario y valor del negocio.
> 2-Urgencia basada en tendencias del mercado y feedback de usuarios.
> 3-Complejidad y esfuerzo estimado de implementación.
> 4-Riesgos y dependencias entre tareas.


## Genera los Tickets de trabajo ##

### prompt 1
> A partir de la siguiente historia de usuario para el sistema LTI, genera una lista de tickets de trabajo técnicos y detallados que un equipo multidisciplinario (frontend, backend, QA, UX) pueda implementar. Cada ticket debe incluir:

> Título claro y específico
> Descripción del trabajo a realizar
> Tipo de ticket (frontend, backend, base de datos, UX/UI, testing, infraestructura, etc.)
> Criterios de aceptación mínimos y verificables
> Dependencias (si las hay)
> Historia de usuario:

> Crear y publicar una vacante asistida por IA
> Título de la Historia de Usuario:
> Como reclutador,
> quiero crear una nueva vacante con ayuda de IA para redactar una descripción inclusiva y atractiva,
> para que atraiga a candidatos calificados y se alinee con la marca empleadora.

> Criterios de Aceptación:

> Puedo ingresar título, ubicación, tipo de contrato, requisitos y beneficios.
> La IA sugiere mejoras en tiempo real sobre lenguaje inclusivo, claridad y palabras clave relevantes.
> Puedo aceptar, rechazar o editar cada sugerencia antes de guardar la descripción final.
> Al publicar, el sistema distribuye la vacante a los canales seleccionados (LinkedIn, portal interno, etc.) y registra cada publicación en Posting.
> Notas Adicionales:

> Las sugerencias de IA y la versión final se almacenan en Vacancy.ai_suggestions_snapshot (JSON).
> El evento de publicación queda registrado en AuditLog con action = "vacancy.published".
