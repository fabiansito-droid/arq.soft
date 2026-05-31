Imagen de Diagrama de Contexto //Nivel 1. Se encuentra en carpeta docs
Imagen de Diagrama de Contenedores //Nivel 2. Se encuentra en carpeta docs

&& Analisis de la Caja Rota.

¿Que ocurre con el Backend y Frotend?
  El Backend no podra consultar ni guardar informacion relacionada con citas, pendientes o psicologos. El
  Frotend seguira funcionando visualmente, pero no podra recuperar ni almacenar datos.
  
¿Como se entera el usuario?
  Se mostrara un mensaje como: 
  "El sistema se ecneuntra temporalmente fuera de servicio. Intente nuevamente en unos minutos."
  
¿Que estrategias usaran?
* Manejo de excepciones en Spring Boot.
* Mensajes de error amigables.
* Reintentos automaticos de conexion a la base de datos.
* Evitar que el sistema completo se bloquee.

&& Diccionario de Contenedores.
* Contenedor       * Tecnologia             * Responsabilidad Principal                             * Despliegue Local
  Frontend         React + TypeScript        Mostrar formularios y citas                              localhost:3000
  Backend API      Java 17 + Spring Boot     Gestionar reglas de negocio y citas                      localhost:8080
  Base de Datos    My SQL 8.0                Almacenar informacion de pacientes, psicologos y citas   localhost:3306
