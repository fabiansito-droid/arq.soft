# Infraestructura de Despliegue del Sistema

## Descripción General

El **Sistema de Gestión y Registro de Citas Psicológicas** será desplegado en un entorno de **computación en la nube**, bajo una arquitectura distribuida compuesta por servidores independientes y aislados. Esta infraestructura permite que cada componente del sistema opere de manera autónoma, facilitando la administración, el mantenimiento y la escalabilidad de la aplicación.

Cada uno de los contenedores identificados en el Diagrama C4 Nivel 2 se ejecutará en una instancia específica, comunicándose mediante protocolos seguros y estandarizados.

---

## Esquema Conceptual de la Infraestructura

```text
                  Pacientes y Psicólogos
                           │
                           │ HTTPS
                           ▼
        ┌─────────────────────────────────┐
        │       Servidor Frontend         │
        │      React + TypeScript         │
        └─────────────────────────────────┘
                           │
                    HTTPS / JSON
                           ▼
        ┌─────────────────────────────────┐
        │       Servidor Backend API      │
        │      Java 17 + Spring Boot      │
        └─────────────────────────────────┘
                 │                  │
        JDBC/SQL │                  │ REST API / SMTP
                 ▼                  ▼
┌────────────────────────┐  ┌────────────────────────┐
│ Servidor Base de Datos │  │ Servicio Externo de    │
│       MySQL 8.0        │  │ Correo Electrónico/SMS │
└────────────────────────┘  └────────────────────────┘
```

---

## Componentes de la Infraestructura

### Frontend Web

- **Tecnología:** React + TypeScript.
- **Función:** Proporcionar la interfaz gráfica para que pacientes y psicólogos puedan registrarse, iniciar sesión, gestionar citas y consultar información del sistema.
- **Despliegue:** Servidor web independiente accesible mediante HTTPS.

### Backend API

- **Tecnología:** Java 17 + Spring Boot.
- **Función:** Gestionar la lógica de negocio, autenticación, validaciones y procesamiento de las solicitudes enviadas desde el Frontend.
- **Despliegue:** Servidor de aplicaciones independiente.

### Base de Datos

- **Tecnología:** MySQL 8.0.
- **Función:** Almacenar de manera persistente la información de pacientes, psicólogos, citas y demás registros del sistema.
- **Despliegue:** Instancia dedicada de base de datos con acceso restringido únicamente al Backend.

### Servicios Externos

- **Tecnología:** API de correo electrónico o SMS.
- **Función:** Enviar recordatorios, confirmaciones y notificaciones relacionadas con las citas psicológicas.
- **Despliegue:** Servicios administrados por proveedores externos.

---

## Justificación de la Infraestructura Seleccionada

Se optó por una infraestructura basada en la nube con servidores independientes debido a los beneficios que ofrece para un sistema de gestión de citas psicológicas.

En primer lugar, esta arquitectura mejora la **escalabilidad**, ya que permite aumentar los recursos de cada componente de manera individual según las necesidades del sistema. Por ejemplo, si existe un incremento en el número de usuarios, es posible ampliar la capacidad del Backend sin afectar el funcionamiento del Frontend o de la Base de Datos.

Asimismo, proporciona una mayor **disponibilidad y tolerancia a fallos**, puesto que una falla en uno de los servidores no implica la interrupción total del servicio. Cada componente permanece aislado, facilitando la detección y recuperación de errores.

Finalmente, esta infraestructura favorece el **mantenimiento, la seguridad y la flexibilidad**, permitiendo realizar actualizaciones independientes, restringir el acceso a componentes críticos y garantizar el acceso remoto al sistema desde diferentes ubicaciones. Estas características resultan fundamentales para ofrecer un servicio confiable y preparado para el crecimiento futuro de la plataforma.

---

## Conclusión

La implementación de una arquitectura distribuida en la nube representa una solución adecuada para el Sistema de Gestión y Registro de Citas Psicológicas, ya que permite construir una aplicación escalable, segura, disponible y fácil de mantener, alineada con las buenas prácticas de diseño arquitectónico propuestas por el Modelo C4.
