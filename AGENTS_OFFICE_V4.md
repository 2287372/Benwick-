# Agents Office V4 — plan de automatización

Este documento adapta el concepto de una oficina de agentes a **Benwick- / AI Command Center**. La interfaz actual es un prototipo: las integraciones y ejecuciones descritas aquí no se consideran activas hasta configurarlas y probarlas.

## Objetivo

Coordinar 35 perfiles de agente en 8 equipos desde un panel móvil, empezando por flujos gratuitos o con nivel gratuito y manteniendo aprobación humana para acciones sensibles.

## Los 8 equipos y 35 agentes

1. **Operaciones (5):** Coordinador de tareas, Planificador de calendario, Asistente de correo, Organizador de archivos, Generador de informes.
2. **Marketing (5):** Estratega de contenido, Redactor de redes, Especialista SEO, Analista de campañas, Redactor publicitario.
3. **Desarrollo (4):** Asistente de código, Revisor de cambios, Probador, Documentador.
4. **Investigación (4):** Buscador de fuentes, Analista de datos, Resumidor, Redactor de informes.
5. **Finanzas (4):** Clasificador de gastos, Asistente de presupuestos, Analista de tendencias, Generador de informes financieros.
6. **Ventas (4):** Investigador de prospectos, Asistente CRM, Redactor de contacto, Preparador de propuestas.
7. **Creatividad (5):** Guionista, Editor de video, Diseñador gráfico, Redactor de subtítulos, Revisor de marca.
8. **Soporte (4):** Clasificador de tickets, Redactor de respuestas, Analista de incidencias, Revisor de satisfacción.

**Total: 35 perfiles.** Son funciones planeadas, no 35 agentes autónomos ya conectados.

## Flujos de automatización propuestos

### A. Producción de video
1. Recibir brief, objetivo, duración y plataforma.
2. Proponer guion, estructura de escenas y subtítulos.
3. Preparar una lista de edición y exportación.
4. Guardar los archivos de trabajo en la carpeta de proyecto de Drive cuando se conecte una integración autorizada.
5. Solicitar aprobación humana antes de publicar o modificar archivos finales.

La IA puede ayudar a planificar y redactar; la edición/renderizado real requiere una herramienta compatible y acceso configurado.

### B. Organización de archivos en la nube
1. Detectar archivos nuevos en una carpeta autorizada.
2. Clasificarlos por cliente, campaña, fecha y tipo.
3. Proponer el destino y evitar nombres duplicados.
4. Registrar cada movimiento.
5. Mover solo cuando las reglas estén probadas; pedir confirmación para borrar, sobrescribir o compartir.

### C. Soporte al cliente e informes diarios
1. Recibir tickets desde una fuente conectada.
2. Clasificar tema, urgencia y equipo responsable.
3. Preparar borradores de respuesta y escalar casos sensibles.
4. Generar un resumen diario de volumen, temas repetidos y pendientes.
5. No enviar respuestas ni cerrar tickets automáticamente hasta que el usuario active y pruebe esa política.

### D. Planificación de ofertas para anuncios
1. Recoger brief, público, objetivo, presupuesto y fechas.
2. Proponer variantes de oferta, textos y creatividades.
3. Revisar consistencia con la marca y restricciones de la plataforma.
4. Preparar un plan para revisión humana.
5. Nunca lanzar campañas, cambiar presupuestos ni publicar anuncios sin aprobación explícita.

## Control de sesión (problema que hay que prevenir)

- Cada ejecución debe tener un identificador de sesión y un estado: pendiente, en curso, requiere aprobación, completada o fallida.
- Guardar el resumen de entradas/salidas y la hora; evitar almacenar contraseñas, tokens o datos sensibles en registros.
- Limitar cada ejecución a las herramientas necesarias y a carpetas/cuentas autorizadas.
- Añadir botón de detener/cancelar y evitar que dos ejecuciones modifiquen el mismo archivo a la vez.
- Reintentar errores temporales con límites; no repetir automáticamente acciones irreversibles.
- Solicitar aprobación humana para enviar mensajes externos, borrar/sobrescribir archivos, publicar contenido, cambiar presupuestos o compartir datos.
- Guardar claves API solo en secretos del servidor o del proveedor de automatización, nunca en el archivo index.html ni en Git.

## Arquitectura inicial recomendada

1. **Panel web:** el archivo index.html actual, adaptado para mostrar equipos, estado de flujos y registro de ejecuciones.
2. **Capa de automatización:** comenzar con flujos sencillos en una herramienta con plan gratuito o con GitHub Actions para tareas de repositorio; GitHub Actions no reemplaza un servidor de agentes siempre activo.
3. **Modelo de IA:** conectar Claude u otro proveedor mediante un backend/servicio seguro; no incluir claves en el navegador público.
4. **Conectores:** añadir Google Drive, Gmail, Calendar, herramienta de tickets y editor de video uno por uno, con permisos mínimos.
5. **Registro y pruebas:** usar datos ficticios primero y verificar cada flujo antes de permitir acciones reales.

## Orden de implementación

- [ ] Paso 1: publicar y comprobar que el panel actual carga desde Android.
- [ ] Paso 2: añadir las ocho áreas y el catálogo de 35 perfiles a la interfaz.
- [ ] Paso 3: construir un registro de tareas/ejecuciones con estados.
- [ ] Paso 4: implementar un flujo de prueba que solo genere un informe ficticio.
- [ ] Paso 5: conectar Drive con permisos mínimos y probar clasificación sin mover archivos.
- [ ] Paso 6: activar movimientos con confirmación y registro.
- [ ] Paso 7: añadir borradores de soporte y reporte diario.
- [ ] Paso 8: añadir planificación de videos y anuncios con aprobación humana.

## Criterio de éxito

La oficina se considerará automatizada solo cuando un flujo real se haya conectado, probado con datos de prueba, documentado y mostrado correctamente en el panel. Los iconos, estados de demostración y perfiles por sí solos no prueban una conexión activa.
