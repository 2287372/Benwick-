# Agents Office V4 — AI Command Center

Panel móvil en español para organizar una oficina conceptual de 35 perfiles de IA en ocho equipos.

## Archivos principales

- `index.html`: panel web, directorio de agentes, tareas, sesiones de prueba, flujos planificados e integraciones.
- `AGENTS_OFFICE_V4.md`: plan técnico, mapa de equipos, automatizaciones propuestas y medidas de seguridad.

## Funciones disponibles en esta versión

- Panel responsive para Android y escritorio.
- Directorio de 35 perfiles en ocho equipos.
- Búsqueda de agentes y filtro por equipo.
- Crear, asignar, completar y eliminar tareas.
- Registro manual de sesiones y pruebas de flujos.
- Catálogo de ocho automatizaciones planificadas.
- Estado visible de integraciones aún no conectadas.
- Persistencia local de tareas y sesiones mediante el almacenamiento del navegador.

## Importante

Esta versión es un prototipo de interfaz y organización. **No** conecta todavía Claude, Gmail, Google Drive, Calendar, plataformas de tickets ni editores de video; tampoco ejecuta agentes autónomos o trabajos en segundo plano. El botón de prueba registra una prueba manual y no ejecuta un servicio externo.

Los datos se guardan localmente en el navegador del dispositivo y no se sincronizan entre dispositivos. No guardes secretos, contraseñas, tokens ni información sensible en el panel.

## Cómo probarlo

1. Abre el sitio publicado o el archivo `index.html` en un navegador.
2. Entra en **35 agentes** para buscar perfiles y filtrar equipos.
3. En **Tareas**, crea una tarea y asígnala a un perfil.
4. Marca la tarea como completada para actualizar el panel.
5. En **Automatizaciones**, usa “Registrar prueba manual” para crear una entrada en el historial de sesiones.
6. En **Integraciones**, revisa qué servicios requieren conexión.

## Próximos pasos de desarrollo

1. Añadir backend seguro y autenticación.
2. Configurar proveedor de IA sin exponer claves en el frontend.
3. Añadir conectores OAuth para Google Drive/Gmail/Calendar con permisos mínimos.
4. Implementar un motor de automatización, estados reales, reintentos limitados y registros.
5. Probar cada flujo con datos ficticios y exigir aprobación humana para acciones externas o irreversibles.

Consulta [AGENTS_OFFICE_V4.md](AGENTS_OFFICE_V4.md) para el plan completo.
