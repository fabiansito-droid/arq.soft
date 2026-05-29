# Estilo macro o estilo interno
El estilo macro permite mostrar de manera sencilla.
- Como interactuan los usuarios con el sistema.
- El flujo general de informacion.
- Las partes principales del software.
- La relacion entre interfaz, logica y base de datos.

# Cajas Estándar del Boceto Informal

## 1. Actor / Usuario

Representa a las personas que interactúan con el sistema.

Ejemplos:
- Paciente
- Psicólogo
- Administrador

---

## 2. Interfaz de Entrada

Es la capa visual donde los usuarios realizan acciones dentro del sistema.

Ejemplos:
- Página web
- Aplicación móvil
- Formularios de registro y citas

---

## 3. Procesador Central (Lógica de Negocio)

Es el núcleo del sistema encargado de:
- Registrar citas
- Validar horarios disponibles
- Gestionar pacientes
- Administrar usuarios
- Controlar reglas del sistema

---

## 4. Gestor de Persistencia

Es la capa encargada de la comunicación con la base de datos.

Funciones:
- Guardar información
- Consultar registros
- Actualizar datos
- Eliminar registros

---

## 5. Almacenamiento Físico

Es el lugar donde se almacenan permanentemente los datos del sistema.

Tecnologías sugeridas:
- MySQL
- PostgreSQL
- Firebase

---

# Boceto General del Sistema
Se encuentra en carpeta docs como - 
# Atributos de Calidad

# Justificacion 
El estilo macro cumple con los atributos de calidad porque divide el sistema en capas organizadas y desacopladas. Esto permite que el software de gestion de citas psicologicas sea mas seguro, escalable, mantenible y facil de comprender, ademas de facilitar futuras mejoras y nuevas funcionalidades.
