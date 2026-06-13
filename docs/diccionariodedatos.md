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
