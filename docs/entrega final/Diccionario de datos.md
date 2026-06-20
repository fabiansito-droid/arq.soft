# Diccionario de Datos

## Tabla: Paciente

| Campo | Tipo | Longitud | PK | FK | Nulo | Descripción |
|--------|------|-----------|----|----|----|-------------|
| id_paciente | INT | 11 | Sí | No | No | Identificador único del paciente |
| nombre | VARCHAR | 100 | No | No | No | Nombre completo del paciente |
| fecha_nacimiento | DATE | - | No | No | No | Fecha de nacimiento |
| sexo | VARCHAR | 20 | No | No | No | Género del paciente |
| telefono | VARCHAR | 15 | No | No | Sí | Número telefónico |
| correo | VARCHAR | 100 | No | No | Sí | Correo electrónico 
| direccion | VARCHAR | 200 | No | No | Sí | Direccion del paciente |

## Tabla: Psicologo

| Campo | Tipo | Longitud | PK | FK | Nulo | Descripción |
|--------|------|-----------|----|----|----|-------------|
| id_psicologo | INT | 11 | Sí | No | No | Identificador del psicologo |
| nombre | VARCHAR | 100 | No | No | No | Nombre completo del psicologo |
| especialidad | VARCHAR | 100 | No | No | No | Especialidad psicologica |
| telefono | VARCHAR | 15 | No | No | Sí | Número telefónico |
| correo | VARCHAR | 100 | No | No | Sí | Correo electrónico |
| cedula_profesional | VARCHAR | 50 | No | No | No | Numero de cedula profesional |

## Tabla: Usuario

| Campo | Tipo | Longitud | PK | FK | Nulo | Descripción |
|--------|------|-----------|----|----|----|-------------|
| id_usuario | INT | 11 | Sí | No | No | Identificador del usuario |
| nombre_usuario | VARCHAR | 50 | No | No | No | Usuario de acceso |
| contraseña | VARCHAR | 255 | No | No | No | Contraseña encriptada |
| rol | VARCHAR | 20 | No | No | No | Administrados, Recepcionista o Psicologo |
| estado | BOOLEAN | - | No | No | No | Estado de la cuenta |

## Tabla: Cita

| Campo | Tipo | Longitud | PK | FK | Nulo | Descripción |
|--------|------|-----------|----|----|----|-------------|
| id_cita | INT | 11 | Sí | No | No | Identificador de la cita |
| id_paciente | INT | 11 | No | Si | No | Paciente que recibe atencion |
| id_psicologo | INT | 11 | No | Si | No | Psicologo asignado |
| fecha | DATE | - | No | No | No | Fecha de la cita |
| hora | TIME | - | No | No | No | Hora programada |
| estado | VARCHAR | 20 | No | No | No | Programada, Cancelada o Completada |
| observaciones | TEXT | - | No | No | Si | Comentarios sobre la cita |

## Tabla: Historial_Clinico

| Campo | Tipo | Longitud | PK | FK | Nulo | Descripción |
|--------|------|-----------|----|----|----|-------------|
| id_historial | INT | 11 | Sí | No | No | Identificador del historial |
| id_paciente | INT | 11 | No | Si | No | Paciente relacionado |
| id_psicologo | INT | 11 | No | Si | No | Psicologo responsable |
| fecha_registro | DATE | - | No | No | No | Fecha del registro |
| diagnostico | TEXT | - | No | No | No | Diagnostico psicologico |
| tratamiento | TEXT | - | No | No | Si | Tratamiento recomendado |
| notas | TEXT | - | No | No | Si | Observaciones adicionales |

## Tabla: Pago

| Campo | Tipo | Longitud | PK | FK | Nulo | Descripción |
|--------|------|-----------|----|----|----|-------------|
| id_pago | INT | 11 | Sí | No | No | Identificador del pago |
| id_cita | INT | 11 | No | Si | No | Cita asociada |
| fecha_pago | DATE | - | No | No | No | Fecha del pago |
| monto | DECIMAL | 10.2 | No | No | No | Monto pagado |
| metodo_pago | VARCHAR | 30 | No | No | No | Efectivo, Tarjeta o Transferencia |
| estado_pago | VARCHAR | 20 | No | No | No | Pendiente o Pagado |
