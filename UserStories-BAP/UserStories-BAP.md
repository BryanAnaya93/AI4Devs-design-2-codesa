# 📌 Historias de Usuario - ATS (Applicant Tracking System)

## 🏗️ Introducción  
Este documento describe las **historias de usuario principales** para el **módulo ATS** del sistema **LTI (Learning & Talent Intelligence)**. Estas historias representan funcionalidades clave que permiten **optimizar el proceso de reclutamiento**, desde la postulación hasta la evaluación de candidatos.

---

## 📌 1️⃣ Historia de Usuario: Filtrado Automático de CVs  
**ID:** HU-ATS-001  
**Título:** Como reclutador, quiero que el sistema filtre automáticamente los CVs de los candidatos para identificar a los más adecuados según los requisitos de la vacante.  

### **Criterios de Aceptación:**  
✅ El sistema debe aceptar archivos en formatos estándar (**PDF, DOCX, TXT**).  
✅ La IA debe analizar experiencia, habilidades y palabras clave en el CV en relación con la descripción del puesto.  
✅ Se debe generar un **puntaje de compatibilidad** basado en criterios configurables por el reclutador.  
✅ Los candidatos deben ser clasificados automáticamente en **"Alto ajuste", "Medio ajuste" y "Bajo ajuste"**.  
✅ Se debe permitir la configuración de **criterios personalizados** de filtrado (años de experiencia, educación, certificaciones).  
✅ El reclutador debe poder revisar y ajustar manualmente las clasificaciones si lo considera necesario.  
✅ Se debe notificar a los reclutadores cuando haya **candidatos con un puntaje alto** para una vacante abierta.  
✅ El resultado del análisis debe almacenarse en el **perfil del candidato** y ser accesible en el ATS.  

### **Definición de Hecho (DoD)**  
✔ Código implementado y probado con al menos **5 tipos de CVs distintos**.  
✔ Puntajes de compatibilidad validados en base a diferentes perfiles de vacantes.  
✔ Integración con la base de datos de postulaciones completada.  
✔ Pruebas de rendimiento con carga de **+100 CVs simultáneamente**.

### **Notas adicionales (Posibles problemas y recomendaciones)**  
⚠ **Posibles problemas:**  
- **Falsos negativos:** La IA podría rechazar buenos candidatos si el CV no contiene ciertas palabras clave.  
- **Errores en formatos de CV:** Algunos documentos pueden tener problemas de parsing si no están bien estructurados.  
- **Falta de transparencia:** El reclutador podría no confiar en los criterios de evaluación de la IA.  

💡 **Recomendaciones:**  
- Permitir que el reclutador revise y ajuste manualmente las clasificaciones de los candidatos.  
- Agregar una funcionalidad de **explicabilidad** para que la IA muestre por qué un candidato fue clasificado de cierta manera.  
- Implementar un proceso de **revisión manual** para candidatos con puntajes medios o dudosos.  


---

## 📌 2️⃣ Historia de Usuario: Evaluación Predictiva de Candidatos  
**ID:** HU-ATS-002  
**Título:** Como reclutador, quiero que el sistema evalúe predictivamente a los candidatos para conocer su probabilidad de éxito en la empresa.  

### **Criterios de Aceptación:**  
✅ El sistema debe comparar al candidato con **perfiles exitosos previos** de la empresa.  
✅ La IA debe analizar tanto **habilidades técnicas** como **ajuste cultural** con base en datos de empleados actuales.  
✅ Se debe generar un informe detallado que incluya:  
   - **Porcentaje de adecuación al puesto.**  
   - **Nivel de coincidencia con empleados exitosos previos.**  
   - **Riesgo de baja permanencia en la empresa.**  
✅ La evaluación debe actualizarse automáticamente si se agregan nuevas **entrevistas, pruebas técnicas o feedback de reclutadores**.  
✅ El reclutador debe poder filtrar candidatos según **probabilidad de éxito** y realizar comparaciones entre ellos.  
✅ Se debe permitir exportar el informe en **PDF y CSV** para su revisión.  

### **Definición de Hecho (DoD)**  
✔ Algoritmo de predicción entrenado con datos históricos de empleados exitosos.  
✔ Generación de informes en PDF y visualización en el ATS.  
✔ Resultados de evaluación almacenados en la base de datos.  
✔ Pruebas con al menos **50 candidatos** para validar la precisión.  

### **Notas adicionales (Posibles problemas y recomendaciones)**  
⚠ **Posibles problemas:**  
- **Sesgos en los datos históricos:** Si los datos de empleados previos contienen sesgos, la IA podría replicarlos en futuras evaluaciones.  
- **Falta de flexibilidad:** El modelo predictivo podría no adaptarse a nuevas tendencias en contratación.  
- **Dificultad para interpretar los resultados:** El reclutador podría no entender por qué un candidato tiene cierto puntaje.  

💡 **Recomendaciones:**  
- Implementar auditorías periódicas para detectar sesgos en los datos.  
- Permitir ajustes manuales y feedback humano para mejorar el modelo.  
- Explicar en lenguaje natural los factores que llevaron a cada puntuación de compatibilidad.  


---

## 📌 3️⃣ Historia de Usuario: Gestión de Postulaciones  
**ID:** HU-ATS-003  
**Título:** Como candidato, quiero poder postularme a una vacante de manera sencilla y recibir confirmación de mi aplicación.  

### **Criterios de Aceptación:**  
✅ El candidato debe poder cargar su **CV, carta de presentación y documentos adicionales** en un formulario intuitivo.  
✅ La postulación debe quedar registrada en la base de datos del ATS con un estado inicial de **"En revisión"**.  
✅ Se debe enviar un **correo de confirmación automática** con los detalles de la postulación y los siguientes pasos.  
✅ El sistema debe permitir que el candidato **haga seguimiento de su postulación** y reciba actualizaciones de estado (**"Revisión", "Entrevista programada", "Rechazado", "Aceptado"**).  
✅ El reclutador debe poder visualizar todas las postulaciones en un **dashboard** con opciones de filtrado por vacante, estado y fecha de postulación.  

### **Definición de Hecho (DoD)**  
✔ Interfaz de usuario implementada y probada en **web y móvil**.  
✔ Postulaciones almacenadas correctamente en la base de datos.  
✔ Notificación automática enviada tras cada postulación.  
✔ Validación de carga masiva de **+500 postulaciones simultáneas**.  

### **Notas adicionales (Posibles problemas y recomendaciones)**  
⚠ **Posibles problemas:**  
- **Carga de documentos pesados:** Si los archivos adjuntos son muy grandes, pueden ralentizar el sistema.  
- **Experiencia de usuario confusa:** Si la interfaz no es intuitiva, los candidatos podrían abandonar la postulación.  
- **Notificaciones poco claras:** El candidato podría no entender en qué estado está su postulación.  

💡 **Recomendaciones:**  
- Establecer un **límite de tamaño para archivos adjuntos** y optimización automática.  
- Implementar una **barra de progreso** clara para que los candidatos vean su estado de postulación.  
- Ofrecer una **sección de preguntas frecuentes (FAQ)** sobre el proceso de postulación. 

---

## 📌 4️⃣ Historia de Usuario: Programación Automática de Entrevistas  
**ID:** HU-ATS-004  
**Título:** Como reclutador, quiero que el sistema me ayude a programar entrevistas con los candidatos de manera automática.  

### **Criterios de Aceptación:**  
✅ El sistema debe sugerir **fechas y horas óptimas** según la disponibilidad del reclutador y el candidato.  
✅ Se debe enviar **invitaciones de calendario** por correo y recordatorios automáticos **24 horas antes de la entrevista**.  
✅ La IA debe priorizar candidatos con mejor puntaje de compatibilidad al momento de asignar horarios.  
✅ Se debe permitir que los reclutadores **reprogramen entrevistas** fácilmente en caso de conflictos de agenda.  
✅ Integración con plataformas externas como **Google Calendar y Outlook** para sincronizar eventos.  
✅ Se debe permitir la programación tanto de **entrevistas en vivo** como de **entrevistas grabadas con preguntas predefinidas**.  

### **Definición de Hecho (DoD)**  
✔ Algoritmo de programación automática implementado y probado.  
✔ Integración funcional con Google Calendar y Outlook.  
✔ Envío de notificaciones automáticas validadas.  
✔ Pruebas con al menos **20 entrevistas programadas automáticamente**.  

### **Notas adicionales (Posibles problemas y recomendaciones)**  
⚠ **Posibles problemas:**  
- **Conflictos de agenda:** Puede haber errores si el calendario del candidato o reclutador no está actualizado.  
- **Candidatos que no responden:** Algunos candidatos pueden ignorar las invitaciones o no asistir a las entrevistas.  
- **Integración con calendarios externos:** Problemas técnicos con Google Calendar o Outlook pueden afectar la sincronización.  

💡 **Recomendaciones:**  
- Implementar **recordatorios automáticos** por correo y notificaciones.  
- Permitir que los candidatos **confirmen o reprogramen** la entrevista desde la plataforma.  
- Probar la integración con diferentes versiones de calendarios antes del despliegue.

---

## 📌 5️⃣ Historia de Usuario: Análisis de Métricas de Contratación  
**ID:** HU-ATS-005  
**Título:** Como gerente de RRHH, quiero poder acceder a reportes sobre la eficiencia del proceso de selección para tomar mejores decisiones.  

### **Criterios de Aceptación:**  
✅ El sistema debe generar métricas sobre:  
   - **Tiempo promedio de contratación.**  
   - **Fuentes de reclutamiento más efectivas (portales de empleo, referencias, etc.).**  
   - **Conversión de candidatos (de postulantes a empleados contratados).**  
   - **Desempeño de candidatos después de ser contratados (si se integran con HRIS).**  
✅ Los reportes deben poder filtrarse por **departamento, puesto y periodo de tiempo**.  
✅ Se debe visualizar un **dashboard interactivo** con gráficos dinámicos y comparativos.  
✅ Exportación de reportes en **PDF y CSV** para compartir con otros equipos.  

### **Definición de Hecho (DoD)**  
✔ Dashboard con gráficos interactivos implementado.  
✔ Cálculo de métricas validadas con datos reales.  
✔ Función de exportación a PDF y CSV operativa.  
✔ Pruebas con al menos **3 meses de datos históricos**.  

### **Notas adicionales (Posibles problemas y recomendaciones)**  
⚠ **Posibles problemas:**  
- **Carga lenta de reportes con grandes volúmenes de datos.**  
- **Falta de personalización:** Los gerentes pueden querer métricas adicionales no incluidas por defecto.  
- **Dificultad para interpretar datos complejos.**  

💡 **Recomendaciones:**  
- Optimizar la generación de reportes para que carguen en **menos de 3 segundos**.  
- Permitir a los usuarios **personalizar los filtros y métricas** del dashboard.  
- Ofrecer **visualizaciones intuitivas** como gráficos dinámicos y resúmenes ejecutivos. 

---

# 📌 Priorización de Historias de Usuario - ATS (RICE)

## 🏗️ Introducción  
La metodología **RICE** nos ayuda a priorizar funcionalidades en función de su **alcance, impacto, confianza y esfuerzo**. A continuación, se presenta la priorización de las historias de usuario del **ATS de LTI**, clasificadas en **Alta, Media y Baja** prioridad.

---

# PRODUCT BACKLOG

---

## 📊 Tabla de Priorización RICE  

| ID Historia  | Descripción | Alcance (1-10) | Impacto (1-10) | Confianza (%) | Esfuerzo (días/persona) | Puntuación RICE | Prioridad Final |
|-------------|-------------|----------------|----------------|---------------|--------------------------|-----------------|----------------|
| **HU-ATS-003** | Gestión de Postulaciones | 9 | 9 | 90% | 6 | **121.5** | 🔴 **Alta** |
| **HU-ATS-001** | Filtrado Automático de CVs | 8 | 8 | 85% | 7 | **77.7** | 🔴 **Alta** |
| **HU-ATS-004** | Programación Automática de Entrevistas | 7 | 7 | 80% | 6 | **65.3** | 🟡 **Media** |
| **HU-ATS-005** | Análisis de Métricas de Contratación | 6 | 6 | 75% | 5 | **54.0** | 🟡 **Media** |
| **HU-ATS-002** | Evaluación Predictiva de Candidatos | 5 | 7 | 70% | 9 | **27.2** | 🟢 **Baja** |

---

## 📌 Justificación de la Priorización

### 🔴 **Alta Prioridad**
- **HU-ATS-003 - Gestión de Postulaciones** 🚀  
  - **(RICE: 121.5)**  
  - **Motivo:** Es la funcionalidad base del ATS, necesaria para que los candidatos puedan postularse. Sin esta función, el sistema carece de propósito.  
  - **Alcance (9):** Impacta a todos los usuarios del sistema (candidatos y reclutadores).  
  - **Impacto (9):** Sin ella, los reclutadores no pueden recibir candidatos.  
  - **Confianza (90%):** Tecnologías ya probadas y de implementación clara.  
  - **Esfuerzo (6 días/persona):** Desarrollo moderado.  

- **HU-ATS-001 - Filtrado Automático de CVs** 🏆  
  - **(RICE: 77.7)**  
  - **Motivo:** Ahorra tiempo a los reclutadores al procesar grandes volúmenes de CVs.  
  - **Alcance (8):** Aplica a todos los candidatos y reclutadores.  
  - **Impacto (8):** Reduce tiempos de selección significativamente.  
  - **Confianza (85%):** Algoritmos de IA requieren ajustes pero son viables.  
  - **Esfuerzo (7 días/persona):** Implementación más compleja por el procesamiento de texto y machine learning.  

---

### 🟡 **Media Prioridad**
- **HU-ATS-004 - Programación Automática de Entrevistas** 📅  
  - **(RICE: 65.3)**  
  - **Motivo:** Agiliza la programación de entrevistas, pero no es una funcionalidad crítica desde el inicio.  
  - **Alcance (7):** Aplica a reclutadores y candidatos seleccionados.  
  - **Impacto (7):** Reduce el trabajo manual de coordinación.  
  - **Confianza (80%):** Integraciones con calendarios pueden tener desafíos.  
  - **Esfuerzo (6 días/persona):** Moderado debido a las integraciones con calendarios externos.  

- **HU-ATS-005 - Análisis de Métricas de Contratación** 📊  
  - **(RICE: 54.0)**  
  - **Motivo:** Ayuda a los gerentes a optimizar procesos, pero no es una funcionalidad crítica inicial.  
  - **Alcance (6):** Aplica solo a gerentes de RRHH.  
  - **Impacto (6):** Mejora la toma de decisiones, pero su ausencia no bloquea otras funciones.  
  - **Confianza (75%):** Se puede basar en datos ya almacenados.  
  - **Esfuerzo (5 días/persona):** Menor esfuerzo en comparación con otras funcionalidades.  

---

### 🟢 **Baja Prioridad**
- **HU-ATS-002 - Evaluación Predictiva de Candidatos** 🤖  
  - **(RICE: 27.2)**  
  - **Motivo:** Es una mejora estratégica que optimiza la selección, pero no es esencial en la primera versión.  
  - **Alcance (5):** Aplica solo a los reclutadores en etapa de decisión final.  
  - **Impacto (7):** Reduce sesgos en la selección y mejora la calidad de contratación.  
  - **Confianza (70%):** Modelos predictivos requieren validación con datos reales.  
  - **Esfuerzo (9 días/persona):** Alto debido al entrenamiento de modelos de IA.  

---

## 

📌 **Resumen de Prioridades:**  
- 🔴 **Alta:** Implementar de inmediato las funcionalidades críticas (Postulaciones y Filtrado de CVs).  
- 🟡 **Media:** Programación de entrevistas y métricas pueden añadirse tras las funciones esenciales.  
- 🟢 **Baja:** Evaluación predictiva es una mejora futura, pero no urgente.  

Esta priorización **optimiza la entrega de valor**, asegurando que el **ATS de LTI** tenga primero las funcionalidades esenciales para operar.  

---

# 📌 Desglose Técnico - Programación Automática de Entrevistas

## 🏗️ Introducción  
Este documento desglosa la historia de usuario **HU-ATS-004 - Programación Automática de Entrevistas** en **tickets técnicos**, organizados por su rol en el desarrollo.  
Se han identificado **nueve tickets** cubriendo **frontend, backend, base de datos, DevOps, QA y documentación**.

---

## 📊 Tabla de Tickets Técnicos  

| ID | Título | Tipo | Estimación | Dependencias | Descripción | Criterios de Aceptación | Requisitos Técnicos |
|----|--------|------|------------|--------------|-------------|-------------------------|---------------------|
| **HIST-04-1** | Crear UI de selección de fechas y horarios | Frontend | 5 | Ninguna | Implementar en React un selector de fechas y horarios para candidatos y reclutadores. | - Permitir selección de fechas y horarios disponibles <br> - Validaciones de horarios no disponibles | React, Tailwind, FullCalendar.js |
| **HIST-04-2** | Implementar API de disponibilidad de entrevistas | Backend | 5 | HIST-04-1 | Desarrollar un endpoint REST para gestionar disponibilidad de entrevistas. | - Endpoint `/interviews/availability` funcional <br> - Pruebas unitarias con Jest | Node.js, Express, PostgreSQL |
| **HIST-04-3** | Modelar tabla de disponibilidad en base de datos | Database | 3 | Ninguna | Crear tabla `availability_slots` en PostgreSQL con estructura optimizada. | - Tabla creada con índices <br> - Relaciones correctas en BD | PostgreSQL, Sequelize ORM |
| **HIST-04-4** | Implementar lógica de asignación automática de entrevistas | Backend | 8 | HIST-04-2, HIST-04-3 | Algoritmo que busque la mejor combinación de horarios disponibles. | - Algoritmo funcionando con test de carga <br> - Asignación en menos de 2s | Node.js, Express, Redis (para caché) |
| **HIST-04-5** | Integración con Google Calendar y Outlook | Backend | 8 | HIST-04-4 | Conectar la funcionalidad con API de Google Calendar y Outlook. | - Creación automática de eventos <br> - Manejo de errores en integración | Google API, Microsoft Graph API |
| **HIST-04-6** | Desarrollar notificaciones automáticas de confirmación | Backend | 5 | HIST-04-4 | Implementar envío de correos y notificaciones push a candidatos y reclutadores. | - Notificaciones enviadas por email y en la UI <br> - Logs auditables | Nodemailer, Firebase Push |
| **HIST-04-7** | Pruebas unitarias y de integración | Testing | 5 | HIST-04-2, HIST-04-4 | Crear pruebas en Jest para endpoints de disponibilidad y asignación. | - 90% de cobertura de código <br> - Casos de prueba con fallos simulados | Jest, Supertest |
| **HIST-04-8** | Desplegar cambios en entornos de staging y producción | DevOps | 3 | HIST-04-5, HIST-04-6 | Configurar pipelines en GitHub Actions para CI/CD. | - Despliegue exitoso en staging <br> - Rollback automatizado en fallos | Docker, Kubernetes, GitHub Actions |
| **HIST-04-9** | Documentar API de entrevistas en Swagger | Documentation | 2 | HIST-04-2, HIST-04-4 | Agregar documentación en Swagger para endpoints de disponibilidad y asignación. | - Swagger generado correctamente <br> - Accesible desde `/docs` | Swagger, OpenAPI |

---

## 📌 🔗 Diagrama de Dependencias entre Tickets  

```mermaid
graph TD;
    HIST-04-1["Frontend: UI Selección de Fechas"] --> HIST-04-2["Backend: API Disponibilidad"];
    HIST-04-2 --> HIST-04-3["DB: Modelado Tabla Disponibilidad"];
    HIST-04-2 --> HIST-04-4["Backend: Asignación Automática"];
    HIST-04-4 --> HIST-04-5["Integración con Google/Outlook"];
    HIST-04-4 --> HIST-04-6["Backend: Notificaciones"];
    HIST-04-2 --> HIST-04-7["Testing: Pruebas Unitarias"];
    HIST-04-4 --> HIST-04-7;
    HIST-04-5 --> HIST-04-8["DevOps: Despliegue en Staging"];
    HIST-04-6 --> HIST-04-8;
    HIST-04-2 --> HIST-04-9["Documentación API Swagger"];
    HIST-04-4 --> HIST-04-9;
```

## 📌 🔄 Orden Recomendado de Implementación
1️⃣ Base de Datos (HIST-04-3): Crear la estructura de disponibilidad de entrevistas.
2️⃣ Backend Inicial (HIST-04-2): Desarrollar API de disponibilidad de horarios.
3️⃣ Frontend Inicial (HIST-04-1): Implementar selector de fechas en React.
4️⃣ Algoritmo de Asignación (HIST-04-4): Lógica de búsqueda de mejores horarios.
5️⃣ Integraciones Externas (HIST-04-5, HIST-04-6): Conectar con Google/Outlook y enviar notificaciones.
6️⃣ Pruebas (HIST-04-7): Garantizar cobertura del código.
7️⃣ DevOps (HIST-04-8): Despliegue en staging y producción.
8️⃣ Documentación (HIST-04-9): Redactar y publicar API en Swagger.

## 📌 ⚠ Riesgos Técnicos Identificados
Sincronización de Horarios:

Los calendarios de candidatos y reclutadores pueden no estar actualizados.
Mitigación: Validación en tiempo real antes de asignar entrevistas.
Problemas con API Externas (Google/Outlook):

La API de Google Calendar/Microsoft Outlook puede tener restricciones o tiempos de respuesta lentos.
Mitigación: Manejo de errores con reintentos y fallback manual.
Rendimiento del Algoritmo de Asignación:

Si hay muchos candidatos y pocos horarios, la búsqueda de asignaciones podría ser lenta.
Mitigación: Implementación de caching con Redis para acelerar consultas.