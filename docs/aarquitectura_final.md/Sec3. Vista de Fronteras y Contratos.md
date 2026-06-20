# Manejo de la ¨Caja Rota¨ en el Sistema de Gestion y Registro de Citas Psicologicas

Si el contenedor de la Base de Datos MySQL pierde la conexión o deja de funcionar temporalmente durante aproximadamente diez minutos, el primer componente afectado será el Backend API, ya que depende directamente de la base de datos para consultar, registrar y actualizar la información de pacientes, psicólogos y citas médicas. Como consecuencia, acciones como iniciar sesión, agendar una nueva cita, modificar horarios o consultar el historial clínico no podrán completarse exitosamente. Sin embargo, el Frontend continuará operativo y accesible para el usuario, evitando que la aplicación se cierre o deje de responder por completo.
Cuando el Backend detecte el fallo al intentar ejecutar una consulta mediante JDBC/SQL, capturará la excepción correspondiente (por ejemplo, SQLException o DatabaseException) mediante bloques de manejo de errores. En lugar de propagar el error hasta provocar la caída del sistema, el Backend devolverá una respuesta controlada al Frontend, como un HTTP 503 (Service Unavailable), indicando que el servicio no está disponible temporalmente. El Frontend interpretará esta respuesta y mostrará un mensaje amigable al usuario, por ejemplo:

"En este momento no es posible procesar su solicitud debido a una falla temporal del sistema. Ninguna cita ha sido registrada ni modificada. Por favor, inténtelo nuevamente en unos minutos."
Adicionalmente, el sistema implementará varias estrategias para evitar un colapso total:

- Captura y manejo de excepciones: todas las operaciones críticas estarán protegidas mediante bloques try-catch para interceptar errores relacionados con la base de datos.
- Registro de eventos (logs): el Backend almacenará información detallada del incidente para facilitar el diagnóstico y la recuperación del servicio.
- Mensajes de retroalimentación claros: el usuario siempre será informado sobre el estado de la operación, evitando incertidumbre o duplicidad de acciones.
- Reintentos automáticos de conexión: el Backend podrá intentar restablecer la conexión con la base de datos después de intervalos cortos de tiempo.
- Preservación de la integridad de los datos: si una operación no puede completarse, esta será cancelada antes de modificar la información, garantizando que no existan citas incompletas, duplicadas o inconsistentes.

De esta manera, aunque la Base de Datos represente la "caja rota" del sistema, la falla queda aislada en el componente afectado. El Frontend continúa funcionando, el Backend responde de forma controlada y los usuarios reciben información oportuna sobre el problema, cumpliendo con los atributos de calidad de disponibilidad, tolerancia a fallos y confiabilidad que se esperan en un sistema de gestión de citas psicológicas.
