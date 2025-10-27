### User Stories ###

## User Stories principales alineadas con los tres casos de uso centrales, las funcionalidades clave del sistema y posibles errores.

> Sos un experto planificador de proyectos. Dado el objetivo de producto LTI adjuntado y las funcionalidades principales determinadas en el mismo, define las historias de usuario principales siguiendo el formato  estándar tambien adjuntado.


### **Historia de Usuario 1: Crear y publicar una vacante asistida por IA**

**Título de la Historia de Usuario:**  
Como reclutador,  
quiero crear una nueva vacante con ayuda de IA para redactar una descripción inclusiva y atractiva,  
para que atraiga a candidatos calificados y se alinee con la marca empleadora.

**Criterios de Aceptación:**  
- El sistema permite ingresar título, requisitos, beneficios y ubicación del puesto.  
- La IA sugiere mejoras en tiempo real (lenguaje inclusivo, palabras clave, tono).  
- El reclutador puede aceptar, rechazar o editar las sugerencias antes de guardar.  
- La vacante puede publicarse en múltiples canales (LinkedIn, portal interno, etc.) con un solo clic.  

**Notas Adicionales:**  
- La funcionalidad debe soportar plantillas predefinidas por tipo de rol (técnico, comercial, etc.).  
- Se debe registrar en el log de auditoría quién creó y publicó la vacante y cuándo.

**Historias de Usuario Relacionadas:**  
- Gestionar etapas del pipeline de selección por vacante  
- Publicar vacante en canales externos vía integraciones

---

### **Historia de Usuario 2: Evaluar candidatos con scoring predictivo**

**Título de la Historia de Usuario:**  
Como reclutador,  
quiero ver una lista priorizada de candidatos con un puntaje de “fit” técnico y cultural generado por IA,  
para que pueda enfocar mi tiempo en los perfiles con mayor probabilidad de éxito.

**Criterios de Aceptación:**  
- El sistema muestra un listado de candidatos postulados a una vacante específica.  
- Cada candidato tiene un score visible (0–100) y una explicación breve del “por qué”.  
- Puedo filtrar/sortear por score, etapa del pipeline, fecha de postulación o skills clave.  
- El CV ha sido parseado automáticamente y los datos clave (experiencia, educación, skills) son visibles y editables.  

**Notas Adicionales:**  
- El scoring debe actualizarse si se edita el perfil del candidato o los requisitos de la vacante.  
- Se debe almacenar un snapshot del CV y del score en el momento de la evaluación para auditoría.

**Historias de Usuario Relacionadas:**  
- Parsear CVs automáticamente al recibir postulaciones  
- Mover candidatos entre etapas del pipeline  
- Ver historial de cambios de estado de una candidatura

---

### **Historia de Usuario 3: Comunicar actualizaciones del proceso a candidatos automáticamente**

**Título de la Historia de Usuario:**  
Como candidato,  
quiero recibir actualizaciones automáticas y personalizadas sobre mi estado en el proceso de selección,  
para que me sienta informado, valorado y comprometido con la empresa.

**Criterios de Aceptación:**  
- Al postularme, recibo un email de confirmación inmediato.  
- Cada vez que el reclutador cambia mi estado (ej. “entrevista programada”, “oferta enviada”), recibo una notificación vía email o portal.  
- Puedo consultar mi estado actual y próximos pasos en un portal interactivo.  
- El sistema permite responder preguntas frecuentes mediante un chatbot 24/7.  

**Notas Adicionales:**  
- Los mensajes deben ser personalizables por vacante y por etapa.  
- Las comunicaciones deben respetar las preferencias de contacto y consentimientos del candidato.

**Historias de Usuario Relacionadas:**  
- Gestionar consentimientos y preferencias de comunicación del candidato  
- Registrar todas las interacciones en un hilo de comunicación por candidatura

---

### **Historia de Usuario 4: Buscar candidatos mediante matching semántico**

**Título de la Historia de Usuario:**  
Como reclutador,  
quiero buscar candidatos en mi base de datos usando lenguaje natural o descripciones de roles,  
para encontrar perfiles relevantes incluso si no usan las mismas palabras clave que la vacante.

**Criterios de Aceptación:**  
- Puedo escribir una descripción libre (ej. “busco alguien que haya liderado migraciones a la nube”) y el sistema devuelve candidatos relevantes.  
- Los resultados incluyen un indicador de relevancia y destacan las coincidencias contextuales.  
- Puedo refinar la búsqueda con filtros (ubicación, años de experiencia, disponibilidad).  

**Notas Adicionales:**  
- El motor de búsqueda debe usar embeddings y soportar español/portugués.  
- Los resultados deben excluir candidatos que hayan retirado su consentimiento.

**Historias de Usuario Relacionadas:**  
- Normalizar y etiquetar skills en perfiles de candidatos  
- Detectar y agrupar candidatos duplicados

---

### **Historia de Usuario 5: Visualizar métricas y predicciones del proceso de reclutamiento**

**Título de la Historia de Usuario:**  
Como gerente de RRHH,  
quiero acceder a un dashboard con KPIs y predicciones del proceso de contratación,  
para tomar decisiones basadas en datos y mejorar continuamente el flujo de talento.

**Criterios de Aceptación:**  
- El dashboard muestra métricas clave: tiempo promedio de contratación, tasa de conversión por etapa, costo por contratación.  
- Incluye alertas inteligentes (ej. “esta vacante lleva 14 días sin candidatos calificados”).  
- Permite comparar métricas por equipo, región o tipo de rol.  
- Muestra predicciones de desempeño de candidatos contratados (basado en modelos de IA).  

**Notas Adicionales:**  
- Los datos deben actualizarse en tiempo cercano a real (máximo 1 hora de latencia).  
- El acceso al dashboard debe respetar permisos por rol (reclutador vs. gerente).

**Historias de Usuario Relacionadas:**  
- Exportar reportes en formato CSV/PDF  
- Configurar alertas personalizadas por vacante o equipo


> Analiza las funcionalidades existentes del sistema LTI para identificar los cinco problemas más comunes que los usuarios podrían enfrentar y sugiere mejoras. Solo enumera los problemas, no generes imformacion extra.

1. **Falta de transparencia en las decisiones de la IA**: los usuarios (reclutadores y candidatos) pueden no entender por qué un candidato recibe un determinado score o por qué una sugerencia de redacción fue hecha, lo que genera desconfianza.  

2. **Dificultad para corregir o sobrescribir resultados automáticos**: si el parsing de CV o el scoring predictivo comete errores, no hay un flujo claro ni herramientas intuitivas para ajustar manualmente los datos sin romper la trazabilidad.  

3. **Sobrecarga de notificaciones automáticas**: la comunicación masiva y automatizada puede volverse ruidosa o genérica, reduciendo su efectividad y dañando la experiencia del candidato.  

4. **Limitaciones en la personalización del pipeline por tipo de rol**: aunque el sistema permite etapas, no está optimizado para adaptar dinámicamente el flujo (etapas, pruebas, criterios) según el perfil del puesto (técnico vs. comercial, junior vs. senior).  

5. **Fragilidad en la detección de duplicados**: la lógica basada en hash de archivos y embeddings puede fallar con CVs ligeramente modificados o en formatos distintos, generando candidatos duplicados que contaminan el pipeline.


> De los 5 problemas mas comunes establecidos genera una historia de usuario para vada uno. Sigue el formato establecido.

### **Historia de Usuario 1: Entender las decisiones de la IA**

**Título de la Historia de Usuario:**  
Como reclutador,  
quiero ver una explicación clara y accesible de por qué la IA asignó un determinado score o hizo una sugerencia,  
para que pueda confiar en las recomendaciones y tomar decisiones informadas.

**Criterios de Aceptación:**  
- Al visualizar el score de un candidato, aparece un botón “Ver explicación” que muestra los factores clave (ej. “+15 por experiencia en Python”, “–5 por falta de liderazgo”).  
- En la redacción asistida de vacantes, cada sugerencia de IA incluye un ícono con tooltip que explica su propósito (ej. “Lenguaje inclusivo”, “Palabra clave para SEO”).  
- Las explicaciones usan lenguaje no técnico y son comprensibles para usuarios sin formación en IA.

**Notas Adicionales:**  
- Las explicaciones deben generarse junto con la predicción y almacenarse en el ApplicationEvent o VacancyHistory para auditoría.  
- No se deben exponer detalles técnicos del modelo (pesos, arquitectura), solo razones interpretables.

**Historias de Usuario Relacionadas:**  
- Evaluar candidatos con scoring predictivo  
- Crear y publicar una vacante asistida por IA

---

### **Historia de Usuario 2: Corregir resultados automáticos sin romper la trazabilidad**

**Título de la Historia de Usuario:**  
Como reclutador,  
quiero poder editar manualmente los datos extraídos por la IA (skills, experiencia, score) y que el sistema conserve un historial de los cambios,  
para que pueda ajustar errores sin perder la capacidad de auditar el proceso.

**Criterios de Aceptación:**  
- En el perfil del candidato, los campos parseados (ej. “Años de experiencia”, “Habilidades”) son editables con un clic.  
- Cada edición genera un registro en ApplicationHistory con tipo “manual_override” y muestra quién hizo el cambio y cuándo.  
- El sistema conserva el valor original (parseado por IA) como “versión inicial” en un campo de auditoría.

**Notas Adicionales:**  
- Los cambios manuales no deben afectar el modelo de scoring en tiempo real, pero sí deben usarse en futuras versiones del modelo (feedback loop).  
- El CV original y el parsed_snapshot deben permanecer intactos.

**Historias de Usuario Relacionadas:**  
- Evaluar candidatos con scoring predictivo  
- Parsear CVs automáticamente al recibir postulaciones

---

### **Historia de Usuario 3: Personalizar la frecuencia y contenido de las notificaciones automáticas**

**Título de la Historia de Usuario:**  
Como candidato,  
quiero poder elegir qué tipo de actualizaciones recibo y con qué frecuencia,  
para que no me sienta abrumado y mantenga una experiencia positiva con la empresa.

**Criterios de Aceptación:**  
- Al postularme, veo un panel de preferencias con opciones: “Recibir todos los mensajes”, “Solo cambios de etapa”, “Solo ofertas”.  
- Puedo modificar estas preferencias en cualquier momento desde el portal del candidato.  
- El sistema respeta mis elecciones y no envía mensajes fuera de lo configurado.

**Notas Adicionales:**  
- Las preferencias deben almacenarse en el perfil del candidato y respetarse en todos los canales (email, SMS, chat).  
- Mensajes críticos (ej. “Su oferta expira en 24h”) pueden tener una excepción configurable por el reclutador.

**Historias de Usuario Relacionadas:**  
- Comunicar actualizaciones del proceso a candidatos automáticamente  
- Gestionar consentimientos y preferencias de comunicación del candidato

---

### **Historia de Usuario 4: Adaptar dinámicamente el pipeline según el tipo de rol**

**Título de la Historia de Usuario:**  
Como reclutador,  
quiero que el sistema sugiera o aplique automáticamente un flujo de selección distinto según el tipo de vacante (técnico, comercial, junior, etc.),  
para que no tenga que configurar manualmente etapas y criterios cada vez.

**Criterios de Aceptación:**  
- Al crear una vacante, elijo un “tipo de rol” (ej. “Ingeniero backend”, “Ejecutivo de ventas”) y el sistema carga un pipeline predefinido.  
- Cada pipeline incluye etapas, pruebas sugeridas (ej. coding test, role play), y criterios de scoring ajustados.  
- Puedo personalizar el pipeline sugerido sin afectar la plantilla original.

**Notas Adicionales:**  
- Las plantillas de pipeline deben ser gestionables por administradores (CRUD).  
- El sistema debe registrar qué plantilla se usó en cada vacante para análisis posterior.

**Historias de Usuario Relacionadas:**  
- Gestionar etapas del pipeline de selección por vacante  
- Evaluar candidatos con scoring predictivo

---

### **Historia de Usuario 5: Revisar y fusionar candidatos duplicados detectados por el sistema**

**Título de la Historia de Usuario:**  
Como reclutador,  
quiero ver una lista de posibles candidatos duplicados agrupados por el sistema y poder fusionarlos o descartar la sugerencia con un solo clic,  
para mantener mi base de talento limpia y evitar esfuerzos redundantes.

**Criterios de Aceptación:**  
- El sistema muestra una pestaña “Duplicados sugeridos” con grupos de candidatos potencialmente repetidos.  
- Cada grupo incluye un score de similitud y los campos que coinciden (email, nombre, CV hash, embeddings).  
- Puedo fusionar dos perfiles (conservando el más completo) o marcar el grupo como “no duplicado”.

**Notas Adicionales:**  
- La fusión debe conservar todas las postulaciones, historial y consentimientos del perfil principal.  
- El sistema debe registrar la acción en AuditLog y ApplicationHistory.

**Historias de Usuario Relacionadas:**  
- Captura de Postulaciones con detección de duplicados  
- Gestionar consentimientos y privacidad de candidatos


> De todas las historias de usuarios generadas (historias de usuario principales, hsitorias de usuarios por problemas comunes), selecciona las mas relevantes para generar un backlog inicial. Solo mencionalas no hagas ningun analisis extra.

1. Crear y publicar una vacante asistida por IA  
2. Evaluar candidatos con scoring predictivo  
3. Comunicar actualizaciones del proceso a candidatos automáticamente  
4. Buscar candidatos mediante matching semántico  
5. Visualizar métricas y predicciones del proceso de reclutamiento  
6. Entender las decisiones de la IA  
7. Corregir resultados automáticos sin romper la trazabilidad  
8. Personalizar la frecuencia y contenido de las notificaciones automáticas  
9. Adaptar dinámicamente el pipeline según el tipo de rol  
10. Revisar y fusionar candidatos duplicados detectados por el sistema


> Valida las User Stories antes selecionadas, identificando posibles inconsistencias, lagunas o conflictos en los requisitos. Solo incluye la informacion pedida.

1. **Inconsistencia en la gestión de explicabilidad de la IA**:  
   La historia “Entender las decisiones de la IA” exige explicaciones interpretables, pero el modelo de datos no incluye un campo explícito para almacenar dichas explicaciones (ej. `explanation_json` en `Application` o `Vacancy`). Sin esto, no se puede garantizar trazabilidad ni auditoría de las razones mostradas al usuario.

2. **Laguna en la gestión de plantillas de pipeline por tipo de rol**:  
   La historia “Adaptar dinámicamente el pipeline según el tipo de rol” asume la existencia de plantillas reutilizables, pero el modelo de datos actual solo define `Stage` vinculado a una `Vacancy` (con `vacancy_id` nullable). No existe una entidad `PipelineTemplate` ni relación entre `Vacancy.type` y una plantilla predefinida.

3. **Conflicto en la edición manual de datos parseados**:  
   La historia “Corregir resultados automáticos sin romper la trazabilidad” requiere que los campos editables conserven el valor original y registren cambios en `ApplicationHistory`. Sin embargo, el modelo actual almacena un único `parsed_profile` (JSON) en `Candidate` o `Application`, sin mecanismo para versionar valores originales vs. manuales ni diferenciar su origen en el historial.

4. **Laguna en la detección y fusión de duplicados**:  
   La historia “Revisar y fusionar candidatos duplicados” presupone una funcionalidad de agrupamiento (`DuplicateGroup`) y fusión, pero el modelo de datos solo menciona `Attachment.hash` como mecanismo de deduplicación. No existe una entidad ni lógica para representar grupos de candidatos potencialmente duplicados ni para ejecutar una fusión segura con consolidación de postulaciones e historial.

5. **Inconsistencia en la personalización de notificaciones**:  
   La historia “Personalizar la frecuencia y contenido de las notificaciones automáticas” implica que las preferencias del candidato afectan todos los canales, pero el modelo de datos no incluye un campo en `Candidate` para registrar dichas preferencias (ej. `notification_preferences: jsonb`), ni el `Message` o `CommunicationThread` hace referencia a reglas de filtrado basadas en ellas.


> Dame una versión ajustada de estas historias ya corregidas.

### **1. Crear y publicar una vacante asistida por IA**

**Título de la Historia de Usuario:**  
Como reclutador,  
quiero crear una nueva vacante con ayuda de IA para redactar una descripción inclusiva y atractiva,  
para que atraiga a candidatos calificados y se alinee con la marca empleadora.

**Criterios de Aceptación:**  
- El sistema permite ingresar título, requisitos, beneficios y ubicación del puesto.  
- La IA sugiere mejoras en tiempo real (lenguaje inclusivo, palabras clave, tono).  
- El reclutador puede aceptar, rechazar o editar las sugerencias antes de guardar.  
- La vacante puede publicarse en múltiples canales (LinkedIn, portal interno, etc.) con un solo clic.  

**Notas Adicionales:**  
- Las sugerencias de IA deben almacenarse junto con la vacante como `ai_suggestions_snapshot` (JSON).  
- Se debe registrar en `AuditLog` quién creó y publicó la vacante y cuándo.

**Historias de Usuario Relacionadas:**  
- Gestionar etapas del pipeline de selección por vacante  
- Publicar vacante en canales externos vía integraciones

---

### **2. Evaluar candidatos con scoring predictivo**

**Título de la Historia de Usuario:**  
Como reclutador,  
quiero ver una lista priorizada de candidatos con un puntaje de “fit” técnico y cultural generado por IA,  
para que pueda enfocar mi tiempo en los perfiles con mayor probabilidad de éxito.

**Criterios de Aceptación:**  
- El sistema muestra un listado de candidatos postulados a una vacante específica.  
- Cada candidato tiene un `final_score` visible (0–100) y una explicación breve del “por qué”.  
- Puedo filtrar/sortear por score, etapa del pipeline, fecha de postulación o skills clave.  
- El CV ha sido parseado automáticamente y los datos clave (experiencia, educación, skills) son visibles y editables.  

**Notas Adicionales:**  
- El `parsed_profile` y el `final_score` se almacenan en `Application` como snapshots.  
- Se registra en `ApplicationHistory` el evento `score_update` con `model_version_id`.

**Historias de Usuario Relacionadas:**  
- Parsear CVs automáticamente al recibir postulaciones  
- Mover candidatos entre etapas del pipeline

---

### **3. Comunicar actualizaciones del proceso a candidatos automáticamente**

**Título de la Historia de Usuario:**  
Como candidato,  
quiero recibir actualizaciones automáticas y personalizadas sobre mi estado en el proceso de selección,  
para que me sienta informado, valorado y comprometido con la empresa.

**Criterios de Aceptación:**  
- Al postularme, recibo un email de confirmación inmediato.  
- Cada vez que el reclutador cambia mi estado, recibo una notificación vía email o portal.  
- Puedo consultar mi estado actual y próximos pasos en un portal interactivo.  
- El sistema permite responder preguntas frecuentes mediante un chatbot 24/7.  

**Notas Adicionales:**  
- Las preferencias de comunicación se almacenan en el perfil del candidato (`notification_preferences: jsonb`).  
- Cada mensaje queda registrado en `CommunicationThread` y `Message`.

**Historias de Usuario Relacionadas:**  
- Gestionar consentimientos y preferencias de comunicación del candidato  
- Registrar todas las interacciones en un hilo de comunicación por candidatura

---

### **4. Buscar candidatos mediante matching semántico**

**Título de la Historia de Usuario:**  
Como reclutador,  
quiero buscar candidatos en mi base de datos usando lenguaje natural o descripciones de roles,  
para encontrar perfiles relevantes incluso si no usan las mismas palabras clave que la vacante.

**Criterios de Aceptación:**  
- Puedo escribir una descripción libre y el sistema devuelve candidatos relevantes.  
- Los resultados incluyen un indicador de relevancia y destacan las coincidencias contextuales.  
- Puedo refinar la búsqueda con filtros (ubicación, años de experiencia, disponibilidad).  

**Notas Adicionales:**  
- Los embeddings se almacenan en `Candidate.last_embedding` y se indexan en `pgvector`.  
- La búsqueda respeta el consentimiento del candidato y excluye perfiles con `consent_withdrawn = true`.

**Historias de Usuario Relacionadas:**  
- Normalizar y etiquetar skills en perfiles de candidatos  
- Detectar y agrupar candidatos duplicados

---

### **5. Visualizar métricas y predicciones del proceso de reclutamiento**

**Título de la Historia de Usuario:**  
Como gerente de RRHH,  
quiero acceder a un dashboard con KPIs y predicciones del proceso de contratación,  
para tomar decisiones basadas en datos y mejorar continuamente el flujo de talento.

**Criterios de Aceptación:**  
- El dashboard muestra métricas clave: tiempo promedio de contratación, tasa de conversión por etapa, costo por contratación.  
- Incluye alertas inteligentes (ej. “esta vacante lleva 14 días sin candidatos calificados”).  
- Permite comparar métricas por equipo, región o tipo de rol.  
- Muestra predicciones de desempeño de candidatos contratados.  

**Notas Adicionales:**  
- Los datos provienen del Data Warehouse alimentado por eventos de Kafka.  
- El acceso al dashboard respeta los permisos definidos en `User.role`.

**Historias de Usuario Relacionadas:**  
- Exportar reportes en formato CSV/PDF  
- Configurar alertas personalizadas por vacante o equipo

---

### **6. Entender las decisiones de la IA**

**Título de la Historia de Usuario:**  
Como reclutador,  
quiero ver una explicación clara y accesible de por qué la IA asignó un determinado score o hizo una sugerencia,  
para que pueda confiar en las recomendaciones y tomar decisiones informadas.

**Criterios de Aceptación:**  
- Al visualizar el score de un candidato, aparece un botón “Ver explicación” que muestra los factores clave.  
- En la redacción asistida de vacantes, cada sugerencia incluye un tooltip con su propósito.  
- Las explicaciones usan lenguaje no técnico y son comprensibles.  

**Notas Adicionales:**  
- Las explicaciones se generan en el servicio de inferencia y se almacenan en `Application.explanation_json` o `Vacancy.ai_suggestions_snapshot`.  
- No se exponen detalles técnicos del modelo.

**Historias de Usuario Relacionadas:**  
- Evaluar candidatos con scoring predictivo  
- Crear y publicar una vacante asistida por IA

---

### **7. Corregir resultados automáticos sin romper la trazabilidad**

**Título de la Historia de Usuario:**  
Como reclutador,  
quiero poder editar manualmente los datos extraídos por la IA (skills, experiencia, score) y que el sistema conserve un historial de los cambios,  
para que pueda ajustar errores sin perder la capacidad de auditar el proceso.

**Criterios de Aceptación:**  
- En el perfil del candidato, los campos parseados son editables con un clic.  
- Cada edición genera un registro en `ApplicationHistory` con tipo `manual_override`.  
- El sistema conserva el valor original como `parsed_snapshot` en `Application`.  

**Notas Adicionales:**  
- Los cambios manuales no invalidan el modelo, pero se registran para feedback loop.  
- El CV original y el `parsed_snapshot` permanecen intactos.

**Historias de Usuario Relacionadas:**  
- Evaluar candidatos con scoring predictivo  
- Parsear CVs automáticamente al recibir postulaciones

---

### **8. Personalizar la frecuencia y contenido de las notificaciones automáticas**

**Título de la Historia de Usuario:**  
Como candidato,  
quiero poder elegir qué tipo de actualizaciones recibo y con qué frecuencia,  
para que no me sienta abrumado y mantenga una experiencia positiva con la empresa.

**Criterios de Aceptación:**  
- Al postularme, veo un panel de preferencias con opciones predefinidas.  
- Puedo modificar estas preferencias en cualquier momento desde el portal del candidato.  
- El sistema respeta mis elecciones y no envía mensajes fuera de lo configurado.  

**Notas Adicionales:**  
- Las preferencias se almacenan en `Candidate.notification_preferences` (JSONB).  
- Mensajes críticos pueden tener una excepción configurable por el reclutador.

**Historias de Usuario Relacionadas:**  
- Comunicar actualizaciones del proceso a candidatos automáticamente  
- Gestionar consentimientos y preferencias de comunicación del candidato

---

### **9. Adaptar dinámicamente el pipeline según el tipo de rol**

**Título de la Historia de Usuario:**  
Como reclutador,  
quiero que el sistema sugiera o aplique automáticamente un flujo de selección distinto según el tipo de vacante (técnico, comercial, junior, etc.),  
para que no tenga que configurar manualmente etapas y criterios cada vez.

**Criterios de Aceptación:**  
- Al crear una vacante, elijo un “tipo de rol” y el sistema carga un pipeline predefinido.  
- Cada pipeline incluye etapas, pruebas sugeridas y criterios de scoring ajustados.  
- Puedo personalizar el pipeline sugerido sin afectar la plantilla original.  

**Notas Adicionales:**  
- Las plantillas se gestionan como entidades `PipelineTemplate` con relación a `Vacancy.type`.  
- El sistema registra qué plantilla se usó en `Vacancy.pipeline_template_id`.

**Historias de Usuario Relacionadas:**  
- Gestionar etapas del pipeline de selección por vacante  
- Evaluar candidatos con scoring predictivo

---

### **10. Revisar y fusionar candidatos duplicados detectados por el sistema**

**Título de la Historia de Usuario:**  
Como reclutador,  
quiero ver una lista de posibles candidatos duplicados agrupados por el sistema y poder fusionarlos o descartar la sugerencia con un solo clic,  
para mantener mi base de talento limpia y evitar esfuerzos redundantes.

**Criterios de Aceptación:**  
- El sistema muestra una pestaña “Duplicados sugeridos” con grupos de candidatos.  
- Cada grupo incluye un score de similitud y los campos que coinciden.  
- Puedo fusionar dos perfiles (conservando el más completo) o marcar el grupo como “no duplicado”.  

**Notas Adicionales:**  
- La fusión conserva todas las postulaciones, historial y consentimientos del perfil principal.  
- Se registra la acción en `AuditLog` y se crea un `DuplicateGroup` con estado resuelto.

**Historias de Usuario Relacionadas:**  
- Captura de Postulaciones con detección de duplicados  
- Gestionar consentimientos y privacidad de candidatos


> Realiza una revisión de las User Stories seleccionadas, proporcionando recomendaciones para mejorar la claridad, coherencia y completitud de las historias. Aplicalas cuando corresponda.

### **1. Crear y publicar una vacante asistida por IA**

**Título de la Historia de Usuario:**  
Como reclutador,  
quiero crear una nueva vacante con ayuda de IA para redactar una descripción inclusiva y atractiva,  
para que atraiga a candidatos calificados y se alinee con la marca empleadora.

**Criterios de Aceptación:**  
- Puedo ingresar título, ubicación, tipo de contrato, requisitos y beneficios.  
- La IA sugiere mejoras en tiempo real sobre lenguaje inclusivo, claridad y palabras clave relevantes.  
- Puedo aceptar, rechazar o editar cada sugerencia antes de guardar la descripción final.  
- Al publicar, el sistema distribuye la vacante a los canales seleccionados (LinkedIn, portal interno, etc.) y registra cada publicación en `Posting`.

**Notas Adicionales:**  
- Las sugerencias de IA y la versión final se almacenan en `Vacancy.ai_suggestions_snapshot` (JSON).  
- El evento de publicación queda registrado en `AuditLog` con `action = "vacancy.published"`.

**Historias de Usuario Relacionadas:**  
- Adaptar dinámicamente el pipeline según el tipo de rol  
- Publicar vacante en canales externos vía integraciones

---

### **2. Evaluar candidatos con scoring predictivo**

**Título de la Historia de Usuario:**  
Como reclutador,  
quiero ver una lista priorizada de candidatos con un puntaje de “fit” técnico y cultural generado por IA,  
para que pueda enfocar mi tiempo en los perfiles con mayor probabilidad de éxito.

**Criterios de Aceptación:**  
- El sistema muestra los candidatos postulados a una vacante, ordenados por `final_score` (0–100).  
- Cada candidato muestra un resumen de su perfil con experiencia, educación y skills extraídos del CV.  
- Al hacer clic en un candidato, veo una explicación interpretable de su score (ej. “+12 por liderazgo en equipos remotos”).  
- Puedo filtrar por etapa, score mínimo, ubicación o skills clave.

**Notas Adicionales:**  
- El `parsed_profile` y `final_score` se almacenan como snapshots en `Application`.  
- La explicación del score se guarda en `Application.explanation_json` y se genera en el servicio de inferencia.

**Historias de Usuario Relacionadas:**  
- Parsear CVs automáticamente al recibir postulaciones  
- Entender las decisiones de la IA

---

### **3. Comunicar actualizaciones del proceso a candidatos automáticamente**

**Título de la Historia de Usuario:**  
Como candidato,  
quiero recibir actualizaciones automáticas y personalizadas sobre mi estado en el proceso de selección,  
para que me sienta informado, valorado y comprometido con la empresa.

**Criterios de Aceptación:**  
- Al postularme, recibo inmediatamente un email de confirmación con un enlace a mi portal de candidato.  
- Cada cambio de etapa en mi candidatura (ej. “entrevista programada”) desencadena una notificación vía email o portal.  
- Puedo ver mi estado actual, próximos pasos y mensajes anteriores en el portal del candidato.  
- El sistema respeta mis preferencias de comunicación (configurables en el portal).

**Notas Adicionales:**  
- Las preferencias se almacenan en `Candidate.notification_preferences` (JSONB).  
- Cada mensaje se registra en `CommunicationThread` y `Message`, con `sender_type = "system"`.

**Historias de Usuario Relacionadas:**  
- Personalizar la frecuencia y contenido de las notificaciones automáticas  
- Gestionar consentimientos y preferencias de comunicación del candidato

---

### **4. Buscar candidatos mediante matching semántico**

**Título de la Historia de Usuario:**  
Como reclutador,  
quiero buscar candidatos en mi base de datos usando lenguaje natural o descripciones de roles,  
para encontrar perfiles relevantes incluso si no usan las mismas palabras clave que la vacante.

**Criterios de Aceptación:**  
- Puedo escribir una consulta en lenguaje natural (ej. “busco un ingeniero que haya migrado sistemas a AWS”).  
- El sistema devuelve candidatos ordenados por relevancia semántica, con un indicador visual de similitud.  
- Los resultados excluyen candidatos que hayan retirado su consentimiento (`consent_withdrawn = true`).  
- Puedo refinar los resultados con filtros estructurados (ubicación, años de experiencia, disponibilidad).

**Notas Adicionales:**  
- Los embeddings se almacenan en `Candidate.last_embedding` y se indexan en `pgvector`.  
- La búsqueda se ejecuta contra el vector store y respeta los permisos del usuario.

**Historias de Usuario Relacionadas:**  
- Normalizar y etiquetar skills en perfiles de candidatos  
- Revisar y fusionar candidatos duplicados detectados por el sistema

---

### **5. Visualizar métricas y predicciones del proceso de reclutamiento**

**Título de la Historia de Usuario:**  
Como gerente de RRHH,  
quiero acceder a un dashboard con KPIs y predicciones del proceso de contratación,  
para tomar decisiones basadas en datos y mejorar continuamente el flujo de talento.

**Criterios de Aceptación:**  
- El dashboard muestra métricas clave: tiempo promedio de contratación, tasa de conversión por etapa, costo por contratación.  
- Incluye alertas proactivas (ej. “Vacante X lleva 14 días sin candidatos calificados”).  
- Permite segmentar los datos por equipo, región, tipo de rol o reclutador.  
- Muestra predicciones de desempeño de candidatos contratados (bajo modelo de IA).

**Notas Adicionales:**  
- Los datos provienen del Data Warehouse alimentado por eventos de Kafka.  
- El acceso está restringido por rol: solo `admin` y `hiring_manager` pueden ver el dashboard.

**Historias de Usuario Relacionadas:**  
- Exportar reportes en formato CSV/PDF  
- Configurar alertas personalizadas por vacante o equipo

---

### **6. Entender las decisiones de la IA**

**Título de la Historia de Usuario:**  
Como reclutador,  
quiero ver una explicación clara y accesible de por qué la IA asignó un determinado score o hizo una sugerencia,  
para que pueda confiar en las recomendaciones y tomar decisiones informadas.

**Criterios de Aceptación:**  
- Al visualizar el score de un candidato, veo un botón “Ver por qué” que despliega los factores clave (ej. “+15 por experiencia en Python”).  
- En la redacción de vacantes, cada sugerencia de IA incluye un ícono con tooltip explicativo (ej. “Inclusividad: evita términos de género”).  
- Las explicaciones usan lenguaje no técnico y evitan referencias a algoritmos o pesos del modelo.

**Notas Adicionales:**  
- Las explicaciones se generan en el servicio de inferencia y se almacenan en `Application.explanation_json` o `Vacancy.ai_suggestions_snapshot`.  
- No se exponen detalles técnicos del modelo (arquitectura, embeddings, etc.).

**Historias de Usuario Relacionadas:**  
- Evaluar candidatos con scoring predictivo  
- Crear y publicar una vacante asistida por IA

---

### **7. Corregir resultados automáticos sin romper la trazabilidad**

**Título de la Historia de Usuario:**  
Como reclutador,  
quiero poder editar manualmente los datos extraídos por la IA (skills, experiencia, score) y que el sistema conserve un historial de los cambios,  
para que pueda ajustar errores sin perder la capacidad de auditar el proceso.

**Criterios de Aceptación:**  
- En el perfil del candidato, los campos parseados (ej. “Años de experiencia”, “Habilidades”) son editables con un clic.  
- Cada edición genera un evento en `ApplicationHistory` con `event_type = "manual_override"`.  
- El sistema conserva el valor original en `Application.parsed_snapshot` y no lo sobrescribe.

**Notas Adicionales:**  
- Los cambios manuales no invalidan el modelo, pero se registran para feedback loop en futuros entrenamientos.  
- El CV original y su hash permanecen intactos en `Attachment`.

**Historias de Usuario Relacionadas:**  
- Evaluar candidatos con scoring predictivo  
- Parsear CVs automáticamente al recibir postulaciones

---

### **8. Personalizar la frecuencia y contenido de las notificaciones automáticas**

**Título de la Historia de Usuario:**  
Como candidato,  
quiero poder elegir qué tipo de actualizaciones recibo y con qué frecuencia,  
para que no me sienta abrumado y mantenga una experiencia positiva con la empresa.

**Criterios de Aceptación:**  
- Al postularme, veo un panel con opciones: “Recibir todos los mensajes”, “Solo cambios de etapa”, “Solo ofertas”.  
- Puedo modificar estas preferencias en cualquier momento desde el portal del candidato.  
- El sistema respeta mis elecciones y no envía mensajes fuera de lo configurado, salvo excepciones críticas (ej. “Su oferta expira en 24h”).

**Notas Adicionales:**  
- Las preferencias se almacenan en `Candidate.notification_preferences` (JSONB).  
- Las excepciones críticas son configurables por el reclutador al crear la vacante.

**Historias de Usuario Relacionadas:**  
- Comunicar actualizaciones del proceso a candidatos automáticamente  
- Gestionar consentimientos y preferencias de comunicación del candidato

---

### **9. Adaptar dinámicamente el pipeline según el tipo de rol**

**Título de la Historia de Usuario:**  
Como reclutador,  
quiero que el sistema sugiera o aplique automáticamente un flujo de selección distinto según el tipo de vacante (técnico, comercial, junior, etc.),  
para que no tenga que configurar manualmente etapas y criterios cada vez.

**Criterios de Aceptación:**  
- Al crear una vacante, selecciono un “tipo de rol” (ej. “Ingeniero backend”, “Ejecutivo de ventas”).  
- El sistema carga automáticamente un pipeline predefinido con etapas, pruebas sugeridas y criterios de scoring.  
- Puedo personalizar el pipeline sugerido sin afectar la plantilla original.

**Notas Adicionales:**  
- Las plantillas se gestionan como entidades `PipelineTemplate` con relación a `Vacancy.type`.  
- El sistema registra qué plantilla se usó en `Vacancy.pipeline_template_id`.

**Historias de Usuario Relacionadas:**  
- Gestionar etapas del pipeline de selección por vacante  
- Evaluar candidatos con scoring predictivo

---

### **10. Revisar y fusionar candidatos duplicados detectados por el sistema**

**Título de la Historia de Usuario:**  
Como reclutador,  
quiero ver una lista de posibles candidatos duplicados agrupados por el sistema y poder fusionarlos o descartar la sugerencia con un solo clic,  
para mantener mi base de talento limpia y evitar esfuerzos redundantes.

**Criterios de Aceptación:**  
- El sistema muestra una pestaña “Duplicados sugeridos” con grupos de candidatos potencialmente repetidos.  
- Cada grupo incluye un score de similitud y los campos que coinciden (email, nombre, hash del CV, embeddings).  
- Puedo fusionar dos perfiles (conservando el más completo) o marcar el grupo como “no duplicado”.

**Notas Adicionales:**  
- La fusión conserva todas las postulaciones, historial y consentimientos del perfil principal.  
- Se registra la acción en `AuditLog` y se crea una entrada en `DuplicateGroup` con estado resuelto.

**Historias de Usuario Relacionadas:**  
- Captura de Postulaciones con detección de duplicados  
- Gestionar consentimientos y privacidad de candidatos


### Backlog de producto ###

> Raliza la priorización del Backlog de Producto LTI, para ello considera las historias de usuario seleccionadas anteriormente. Estima considerando los siguentes factores para la Priorización del Backlog (genera una tabla markdown):
> 1-Impacto en el usuario y valor del negocio.
> 2-Urgencia basada en tendencias del mercado y feedback de usuarios.
> 3-Complejidad y esfuerzo estimado de implementación.
> 4-Riesgos y dependencias entre tareas.


- **Impacto en el usuario y valor del negocio** (Alto / Medio / Bajo)  
- **Urgencia** (Alta / Media / Baja)  
- **Complejidad y esfuerzo** (Alto / Medio / Bajo)  
- **Riesgos y dependencias** (Alto / Medio / Bajo)

La priorización final se expresa como **Prioridad (1 = más alta, 10 = más baja)**, determinada por una ponderación cualitativa que favorece alto impacto, alta urgencia y baja complejidad/riesgo.

| # | Historia de Usuario | Impacto | Urgencia | Complejidad | Riesgos/Dependencias | Prioridad |
|---|----------------------|---------|----------|-------------|------------------------|-----------|
| 1 | Crear y publicar una vacante asistida por IA | Alto | Alta | Medio | Medio (depende de LLM + integraciones) | **1** |
| 2 | Evaluar candidatos con scoring predictivo | Alto | Alta | Alto | Alto (depende de parsing, embeddings, modelo de scoring) | **2** |
| 3 | Comunicar actualizaciones del proceso a candidatos automáticamente | Alto | Alta | Bajo | Bajo (usa infra de mensajería existente) | **3** |
| 4 | Buscar candidatos mediante matching semántico | Alto | Media | Alto | Alto (requiere vector DB, embeddings, indexación) | **5** |
| 5 | Visualizar métricas y predicciones del proceso de reclutamiento | Medio | Media | Alto | Alto (depende de data pipeline y warehouse) | **7** |
| 6 | Entender las decisiones de la IA | Medio | Alta | Bajo | Bajo (explicabilidad se genera en inferencia) | **4** |
| 7 | Corregir resultados automáticos sin romper la trazabilidad | Medio | Media | Medio | Medio (requiere versionado de snapshots y ApplicationHistory) | **6** |
| 8 | Personalizar la frecuencia y contenido de las notificaciones automáticas | Medio | Alta | Bajo | Bajo (extensión de preferencias en Candidate) | **8** |
| 9 | Adaptar dinámicamente el pipeline según el tipo de rol | Medio | Media | Medio | Medio (requiere entidad `PipelineTemplate`) | **9** |
|10 | Revisar y fusionar candidatos duplicados detectados por el sistema | Bajo | Baja | Alto | Alto (requiere lógica de agrupamiento y fusión segura) | **10** |

---

### Criterios aplicados en la ponderación:

- **Impacto alto**: historias que tocan los **3 casos de uso principales** (gestión de vacantes, evaluación de candidatos, comunicación).
- **Urgencia alta**: funcionalidades esperadas en un ATS moderno (IA explicativa, comunicación automática, redacción asistida), respaldadas por tendencias de UX y feedback de reclutadores/candidatos.
- **Complejidad baja**: tareas que aprovechan componentes ya definidos (mensajería, ApplicationHistory, Candidate.preferences).
- **Riesgos bajos**: ausencia de dependencias críticas o de modelos no disponibles.

Este orden permite **entregar valor temprano** (MVP en 1–3), **reforzar confianza en la IA** (historias 6 y 7), y **escalar con inteligencia** (historias 4, 5, 9, 10) en iteraciones posteriores.



### Genera los Tickets de trabajo ###

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


### **1. Diseñar flujo de creación de vacante con panel de redacción asistida por IA**  
**Tipo:** UX/UI  
**Descripción:**  
Diseñar la interfaz de creación de vacante que incluya: campos para título, ubicación, tipo de contrato, requisitos y beneficios; y un panel lateral o integrado que muestre sugerencias de IA en tiempo real (con acciones: aceptar, rechazar, editar).  
**Criterios de Aceptación:**  
- Wireframes y prototipo interactivo aprobados por Product y reclutadores piloto.  
- Diseño accesible (WCAG 2.1 AA) y responsive (desktop + tablet).  
- Indicadores visuales claros para sugerencias (iconos, tooltips, estado de cada sugerencia).  
**Dependencias:** Ninguna.

---

### **2. Implementar formulario de creación de vacante en frontend**  
**Tipo:** Frontend  
**Descripción:**  
Desarrollar el formulario de creación de vacante con validación de campos obligatorios, soporte para edición enriquecida (requisitos y beneficios), y estado de borrador guardado localmente.  
**Criterios de Aceptación:**  
- Formulario funcional con campos: título (texto), ubicación (autocomplete), tipo de contrato (select), requisitos (editor WYSIWYG), beneficios (editor WYSIWYG).  
- Los cambios se guardan como borrador cada 30 segundos o al salir del campo.  
- Compatible con navegadores soportados (Chrome, Firefox, Safari último año).  
**Dependencias:** Ticket #1 (diseño UX/UI).

---

### **3. Crear endpoint backend para recibir y almacenar borradores de vacante**  
**Tipo:** Backend  
**Descripción:**  
Implementar API REST para crear y actualizar borradores de vacante (`POST /vacancies/draft`, `PATCH /vacancies/{id}/draft`).  
**Criterios de Aceptación:**  
- Endpoint acepta payload con campos de la vacante y persiste en tabla `vacancy` con `status = 'draft'`.  
- Valida campos obligatorios y formato.  
- Devuelve `201 Created` o `200 OK` con ID de vacante.  
**Dependencias:** Ninguna.

---

### **4. Desarrollar servicio de sugerencias de IA para redacción de vacantes**  
**Tipo:** Backend / IA  
**Descripción:**  
Crear un microservicio (o módulo) que reciba un texto de descripción de vacante y devuelva sugerencias estructuradas sobre lenguaje inclusivo, claridad y palabras clave.  
**Criterios de Aceptación:**  
- Expone endpoint `POST /ai/suggestions` que recibe `{title, requirements, benefits}`.  
- Retorna JSON con array de sugerencias: `{id, type, original_text, suggested_text, explanation, position}`.  
- Soporta español y portugués.  
- Usa modelo de lenguaje afinado (fine-tuned) o reglas validadas por lingüistas.  
**Dependencias:** Disponibilidad del modelo de IA (puede ser mock inicial).

---

### **5. Integrar sugerencias de IA en tiempo real en el formulario de vacante**  
**Tipo:** Frontend  
**Descripción:**  
Conectar el formulario de creación de vacante con el servicio de IA para mostrar sugerencias mientras el usuario escribe (con debounce de 1.5s).  
**Criterios de Aceptación:**  
- Al escribir en requisitos o beneficios, se llama al endpoint de IA tras 1.5s de inactividad.  
- Las sugerencias aparecen en el panel de IA con botones “Aceptar”, “Rechazar”, “Editar”.  
- Las acciones del usuario se reflejan inmediatamente en el editor.  
**Dependencias:** Tickets #2 y #4.

---

### **6. Persistir sugerencias de IA y versión final en Vacancy**  
**Tipo:** Backend / Base de datos  
**Descripción:**  
Al guardar la vacante (como borrador o publicada), almacenar las sugerencias aplicadas y el texto final en los campos `ai_suggestions_snapshot` (JSON) y `description` (texto consolidado).  
**Criterios de Aceptación:**  
- Tabla `vacancy` incluye columna `ai_suggestions_snapshot JSONB NOT NULL DEFAULT '{}'`.  
- Al guardar, el backend serializa las sugerencias aceptadas/editadas y el texto resultante.  
- El campo `description` contiene el texto final listo para publicar.  
**Dependencias:** Tickets #3 y #5.

---

### **7. Implementar selección y publicación en canales externos**  
**Tipo:** Frontend + Backend  
**Descripción:**  
Agregar UI para seleccionar canales de publicación (LinkedIn, portal interno, etc.) y backend que orqueste la publicación vía Integration Service.  
**Criterios de Aceptación:**  
- Checkbox o selector múltiple de canales disponibles (configurables por tenant).  
- Al hacer clic en “Publicar”, el frontend envía lista de canales seleccionados.  
- Backend llama al Integration Service para cada canal y registra resultado en tabla `posting`.  
**Dependencias:** Existencia del Integration Service (puede usar mock inicial).

---

### **8. Registrar publicación de vacante en AuditLog**  
**Tipo:** Backend  
**Descripción:**  
Al publicar una vacante, registrar un evento en `AuditLog` con `entity_type = 'Vacancy'`, `action = 'vacancy.published'`, y metadatos relevantes.  
**Criterios de Aceptación:**  
- Se inserta un registro en `audit_log` con `entity_id = vacancy.id`, `by_user_id`, `timestamp`, y `details` con canales publicados.  
- El evento es inmutable y visible en el historial de auditoría.  
**Dependencias:** Ticket #7.

---

### **9. Crear tabla Posting y relación con Vacancy**  
**Tipo:** Base de datos  
**Descripción:**  
Definir y migrar la tabla `posting` según el modelo de datos de LTI-GM.md, con relación 1:N desde `vacancy`.  
**Criterios de Aceptación:**  
- Tabla `posting` con campos: `id`, `vacancy_id` (FK), `channel_name`, `external_post_id`, `status`, `published_at`, `meta` (JSONB).  
- Índice en `vacancy_id` y `status`.  
- Migración ejecutada en entorno de staging y producción.  
**Dependencias:** Ninguna.

---

### **10. Escribir pruebas automatizadas para flujo de creación y publicación**  
**Tipo:** Testing (QA)  
**Descripción:**  
Implementar suite de pruebas E2E y unitarias para validar el flujo completo: creación, sugerencias de IA, publicación y auditoría.  
**Criterios de Aceptación:**  
- Pruebas E2E cubren: creación de vacante → sugerencias → publicación → verificación en `posting` y `audit_log`.  
- Mock del servicio de IA para pruebas deterministas.  
- Cobertura mínima del 80% en lógica de backend crítica (guardado, publicación).  
**Dependencias:** Tickets #2, #3, #4, #5, #6, #7, #8, #9.




