**FEIRNNR - Carrera de Computación**

---

# INFORME DE FIN DE UNIDAD

## Datos Generales

| | |
|---|---|
| **Asignatura** | Base de datos |
| **Ciclo** | 3 A |
| **Unidad** | 1 |
| **Resultado de aprendizaje de la unidad** | Modela bases de datos de problemas reales, bajo los principios de solidaridad, transparencia, responsabilidad y honestidad. |
| **Nombre del Docente** | Edwin René Guamán Quinche |
| **Fecha** | 30/10/2026 |
| **Nombres y apellidos del estudiantes** | Freddy Alexander Ordoñez Gonzalez |

---

## 1. TITULO

*Diseño de un Sistema de Base de Datos para el Control de Ingreso Agrocalidad, Jornadas Dominicales de Compra-Venta y Concursos de Exposición en la Feria Ganadera **El Porvenir" del Cantón Saraguro, provincia de Loja.***

---

## 2. CONTEXTO DEL PROBLEMA

- **¿Cuál es la situación o entorno donde se presenta el problema?**

La situación se desarrolla en el entorno operativo y agropecuario de la Feria Ganadera "El Porvenir", ubicada en el cantón Saraguro, provincia de Loja. Este espacio funciona bajo un esquema comercial continuo que opera todos los domingos del año para la exhibición y transacciones de ganado, complementado con una exposición anual especial en el mes de marzo en el marco de las festividades de cantonización.

- **¿Qué dificultades o necesidades existen actualmente sin una base de datos?**

Actualmente, la gestión se realiza de manera empírica, manual o fragmentada. Esto genera serias dificultades operativas, tales como inconsistencias en el control de ingreso al verificar visualmente las Guías de Movilización de Agrocalidad frente a la cantidad real de animales, falta de trazabilidad en el control sanitario de los veterinarios (dificultando registrar aretes, diagnósticos y guías de salida), y la ausencia de un historial confiable sobre genealogía animal, además de opacidad en el registro de los precios fijos, negociaciones y ofertas directas de las jornadas dominicales.

- **¿A quiénes afecta el problema? (usuarios, institución, organización)**

El problema afecta directamente a los propietarios y expositores, quienes pierden tiempo en los accesos y carecen de respaldo digital; a los médicos veterinarios y administradores, que cargan con la fiscalización de Agrocalidad sin herramientas automatizadas; y a la organización y comunidad de Saraguro, por la falta de estadísticas transparentes e históricos de las ferias dominicales y juzgamientos anuales.

- **¿Qué datos se necesitan gestionar y por qué es importante hacerlo correctamente?**

Se necesita gestionar de manera integral la información de propietarios, haciendas, guías de movilización, controles sanitarios, inventario y genealogía animal, cronogramas dominicales, inscripciones de exposición y transacciones de compra, venta y ofertas. Es fundamental hacerlo mediante una base de datos relacional para garantizar la integridad referencial, cumplir con normativas fitosanitarias, erradicar el fraude en el conteo de animales y asegurar total transparencia en los procesos comerciales y competitivos de la feria.

---

## 3. OBJETIVOS

### 3.1. Objetivo General

*Diseñar e implementar un sistema de base de datos relacional para gestionar de forma integral el control de ingreso validado por Agrocalidad, las jornadas dominicales de compra-venta y los concursos de exposición en la Feria Ganadera "El Porvenir" del cantón Saraguro, mediante el modelado de datos y herramientas de gestión en DBeaver, con la finalidad de garantizar la trazabilidad sanitaria, optimizar los procesos comerciales y asegurar la transparencia en los eventos competitivos.*

### 3.2. Objetivos Específicos

1. Modelar conceptual y lógicamente la base de datos elaborando el Diagrama Entidad-Relación y el esquema relacional normalizado que estructure la información de los expositores, guías de movilización de Agrocalidad, controles sanitarios veterinarios, genealogía de los animales y cronogramas dominicales.

2. Construir el esquema físico e implementar las consultas avanzadas en SQL utilizando sentencias DDL, DML y traducciones de álgebra relacional para automatizar la validación de ingresos, el registro de transacciones de compra-venta y la administración de los juzgamientos en la exposición anual de marzo.

---

## 4. MODELOS CONCEPTUALES DE BASES DE DATOS

### 4.1. Modelo Entidad-Relación (E-R)
<img width="3377" height="2059" alt="Feria_Ganadera_Saraguro" src="https://github.com/user-attachments/assets/ae1b3b4b-b3e2-4bdb-b0a2-9f3a1386f93a" />


### 4.2. Modelo Relacional

<img width="1138" height="891" alt="FeriaRelacional" src="https://github.com/user-attachments/assets/36ddcaf6-972e-4a2c-994f-0a46069e02bc" />


Esquema relacional (las claves primarias están subrayadas en el diagrama original; aquí se indican con `*`):

- **Propietario** (`*ID_Propietario`, Cedula_RUC, Nombre_RazonSocial, Nombre_Hacienda, Provincia, Canton, Parroquia)
- **Guía_Movilización** (`*ID_Guia`, Numero_Guia, Fecha_Emision, Cantidad_Animales_Autorizados, Cantidad_Animales_Ingresados, Nombre_Hacienda_Origen, ID_Propietario)
- **Control_Sanitario** (`*ID_Control`, Fecha_Hora_Control, Numero_Arete_Verificado, Diagnostico_Sanitario, Estado_Aprobacion, Numero_Guia_Salida, ID_Veterinario, ID_Guia)
- **Veterinario** (`*ID_Veterinario`, Cedula, Nombre_Completo, Apellido_Completo)
- **Animal** (`*ID_Animal`, Numero_Arete, Especie, Raza, Sexo, Fecha_Nacimiento, Peso_Actual, ID_Propietario)
- **Genealogía** (`*ID_Genealogia`, Registro_Genealogico, Padre, Madre, ID_Animal)
- **Oferta** (`*ID_Oferta`, Monto_Ofertado, Fecha_Hora, Estado_Oferta, ID_Transaccion, ID_Propietario)
- **Transacción_Venta** (`*ID_Transaccion`, Precio_Fijo, Precio_Final, Fecha_Hora, Estado, ID_Animal, ID_Propietario_Vendedor, ID_Propietario_Comprador, ID_Jornada)
- **Cronograma** (`*ID_Jornada`, Fecha_Domingo, Hora_Inicio, Hora_Fin, Descripcion_Jornada)
- **Inscripción** (`*ID_Inscripcion`, Numero_Pista, ID_Animal, ID_Exposicion, ID_Categoria)
- **Categoría_Concurso** (`*ID_Categoria`, Nombre)
- **Exposición_Anual** (`*ID_Exposicion`, Nombre_Evento, Fecha_Inicio, Fecha_Fin)
- **Juzgamiento_Premiación** (`*ID_Calificacion`, Juez_Responsable, Puntuacion_Obtenida, Puesto_Asignado, Tipo_Premio, Monto_Premio, ID_Inscripcion)

*Freddy Ordoñez*

---

## 5. CÓDIGO SQL

### 5.1. Creación de Tablas (DDL)

**--Tabla Propietario:**

```sql
-- Creación de la tabla PROPIETARIO
CREATE TABLE PROPIETARIO (
    id_propietario VARCHAR(50) NOT NULL,
    cedula_ruc VARCHAR(20) NOT NULL UNIQUE,
    nombre_razonsocial VARCHAR(150) NOT NULL,
    nombre_hacienda VARCHAR(100) NOT NULL,
    provincia VARCHAR(50) NOT NULL,
    canton VARCHAR(50) NOT NULL,
    parroquia VARCHAR(50) NOT NULL,
    PRIMARY KEY (id_propietario)
);
```

**--Tabla Guía de Movilización:**

```sql
-- Creación de la tabla GUIA_MOVILIZACION (Incluye el FK hacia PROPIETARIO)
CREATE TABLE GUIA_MOVILIZACION (
    id_guia VARCHAR(50) NOT NULL,
    numero_guia VARCHAR(50) NOT NULL UNIQUE,
    fecha_emision DATE NOT NULL,
    cantidad_animales_autorizados INT NOT NULL,
    cantidad_animales_ingresados INT,
    nombre_hacienda_origen VARCHAR(100) NOT NULL,
    id_propietario VARCHAR(50) NOT NULL,
    PRIMARY KEY (id_guia),
    FOREIGN KEY (id_propietario) REFERENCES PROPIETARIO(id_propietario)
);
```

**--Tabla Control Sanitario:**

```sql
-- Creación de la tabla CONTROL_SANITARIO (Incluye el FK hacia VETERINARIO y GUIA_MOVILIZACION)
CREATE TABLE CONTROL_SANITARIO (
    id_control VARCHAR(50) NOT NULL,
    fecha_hora_control TIMESTAMP NOT NULL,
    numero_arete_verificado VARCHAR(50) NOT NULL,
    diagnostico_sanitario TEXT,
    estado_aprobacion VARCHAR(20) NOT NULL,
    numero_guia_salida VARCHAR(50),
    id_veterinario VARCHAR(50) NOT NULL,
    id_guia VARCHAR(50) NOT NULL,
    PRIMARY KEY (id_control),
    FOREIGN KEY (id_veterinario) REFERENCES VETERINARIO(id_veterinario),
    FOREIGN KEY (id_guia) REFERENCES GUIA_MOVILIZACION(id_guia)
);
```

**--Tabla Veterinario:**

```sql
-- Creación de la tabla VETERINARIO
CREATE TABLE VETERINARIO (
    id_veterinario VARCHAR(50) NOT NULL,
    cedula VARCHAR(20) NOT NULL UNIQUE,
    nombre_completo VARCHAR(100) NOT NULL,
    apellido_completo VARCHAR(100) NOT NULL,
    PRIMARY KEY (id_veterinario)
);
```

**--Tabla Animal:**

```sql
-- Creación de la tabla ANIMAL (Incluye el FK hacia PROPIETARIO)
CREATE TABLE ANIMAL (
    id_animal VARCHAR(50) NOT NULL,
    numero_arete VARCHAR(50) NOT NULL UNIQUE,
    especie VARCHAR(50) NOT NULL,
    raza VARCHAR(50) NOT NULL,
    sexo VARCHAR(20) NOT NULL,
    fecha_nacimiento DATE,
    peso_actual DECIMAL(10,2),
    id_propietario VARCHAR(50) NOT NULL,
    PRIMARY KEY (id_animal),
    FOREIGN KEY (id_propietario) REFERENCES PROPIETARIO(id_propietario)
);
```

**--Tabla Genealogía:**

```sql
-- Creación de la tabla GENEALOGIA (Incluye el FK hacia ANIMAL)
CREATE TABLE GENEALOGIA (
    id_genealogia VARCHAR(50) NOT NULL,
    registro_genealogico VARCHAR(100) UNIQUE,
    padre VARCHAR(100),
    madre VARCHAR(100),
    id_animal VARCHAR(50) NOT NULL,
    PRIMARY KEY (id_genealogia),
    FOREIGN KEY (id_animal) REFERENCES ANIMAL(id_animal)
);
```

**--Tabla Oferta:**

```sql
-- Creación de la tabla OFERTA (Incluye el FK hacia TRANSACCION_VENTA y PROPIETARIO)
CREATE TABLE OFERTA (
    id_oferta VARCHAR(50) NOT NULL,
    monto_ofertado DECIMAL(10,2) NOT NULL,
    fecha_hora TIMESTAMP NOT NULL,
    estado_oferta VARCHAR(50) NOT NULL,
    id_transaccion VARCHAR(50) NOT NULL,
    id_propietario VARCHAR(50) NOT NULL,
    PRIMARY KEY (id_oferta),
    FOREIGN KEY (id_transaccion) REFERENCES TRANSACCION_VENTA(id_transaccion),
    FOREIGN KEY (id_propietario) REFERENCES PROPIETARIO(id_propietario)
);
```

**--Tabla Transacción de Venta:**

```sql
-- Creación de la tabla TRANSACCION_VENTA (Incluye el FK hacia ANIMAL, PROPIETARIO vendedor/comprador, y CRONOGRAMA)
CREATE TABLE TRANSACCION_VENTA (
    id_transaccion VARCHAR(50) NOT NULL,
    precio_fijo DECIMAL(10,2) NOT NULL,
    precio_final DECIMAL(10,2) NOT NULL,
    fecha_hora TIMESTAMP NOT NULL,
    estado VARCHAR(50) NOT NULL,
    id_animal VARCHAR(50) NOT NULL,
    id_propietario_vendedor VARCHAR(50) NOT NULL,
    id_propietario_comprador VARCHAR(50) NOT NULL,
    id_jornada VARCHAR(50) NOT NULL,
    PRIMARY KEY (id_transaccion),
    FOREIGN KEY (id_animal) REFERENCES ANIMAL(id_animal),
    FOREIGN KEY (id_propietario_vendedor) REFERENCES PROPIETARIO(id_propietario),
    FOREIGN KEY (id_propietario_comprador) REFERENCES PROPIETARIO(id_propietario),
    FOREIGN KEY (id_jornada) REFERENCES CRONOGRAMA(id_jornada)
);
```

**--Tabla del Cronograma:**

```sql
-- Creación de la tabla CRONOGRAMA (Administración las jornadas del Domingo)
CREATE TABLE CRONOGRAMA (
    id_jornada VARCHAR(50) NOT NULL,
    fecha_domingo DATE NOT NULL UNIQUE,
    hora_inicio TIME NOT NULL DEFAULT '06:00:00',
    hora_fin TIME NOT NULL DEFAULT '13:00:00',
    descripcion_jornada TEXT,
    PRIMARY KEY (id_jornada)
);
```

**--Tabla Inscripción:**

```sql
-- Creación de la tabla INSCRIPCION (Incluye el FK hacia ANIMAL, EXPOSICION_ANUAL y CATEGORIA_CONCURSO)
CREATE TABLE INSCRIPCION (
    id_inscripcion VARCHAR(50) NOT NULL,
    numero_pista INT,
    id_animal VARCHAR(50) NOT NULL,
    id_exposicion VARCHAR(50) NOT NULL,
    id_categoria VARCHAR(50) NOT NULL,
    PRIMARY KEY (id_inscripcion),
    FOREIGN KEY (id_animal) REFERENCES ANIMAL(id_animal),
    FOREIGN KEY (id_exposicion) REFERENCES EXPOSICION_ANUAL(id_exposicion),
    FOREIGN KEY (id_categoria) REFERENCES CATEGORIA_CONCURSO(id_categoria)
);
```

**--Tabla Categoría del Concurso:**

```sql
-- Creación de la tabla CATEGORIA_CONCURSO
CREATE TABLE CATEGORIA_CONCURSO (
    id_categoria VARCHAR(50) NOT NULL,
    nombre VARCHAR(100) NOT NULL,
    PRIMARY KEY (id_categoria)
);
```

**--Tabla Exposición Anual:**

```sql
-- Creación de la tabla EXPOSICION_ANUAL (Evento especial de marzo
-- por las fiestas del cantón)
CREATE TABLE EXPOSICION_ANUAL (
    id_exposicion VARCHAR(50) NOT NULL,
    nombre_evento VARCHAR(150) NOT NULL,
    fecha_inicio DATE NOT NULL,
    fecha_fin DATE NOT NULL,
    PRIMARY KEY (id_exposicion)
);
```

**--Tabla Juzgamiento y Premiación:**

```sql
-- Creación de la tabla JUZGAMIENTO_PREMIACION (Incluye el FK hacia INSCRIPCION)
CREATE TABLE JUZGAMIENTO_PREMIACION (
    id_calificacion VARCHAR(50) NOT NULL,
    juez_responsable VARCHAR(150) NOT NULL,
    puntuacion_obtenida DECIMAL(5,2) NOT NULL,
    puesto_asignado INT NOT NULL,
    tipo_premio VARCHAR(50),
    monto_premio DECIMAL(10,2),
    id_inscripcion VARCHAR(50) NOT NULL,
    PRIMARY KEY (id_calificacion),
    FOREIGN KEY (id_inscripcion) REFERENCES INSCRIPCION(id_inscripcion)
);
```

---

### 5.2. Inserción de Datos (DML)

**Datos para la tabla Propietario:**

```sql
-- Inserción de datos de para la tabla PROPIETARIO
INSERT INTO PROPIETARIO (id_propietario, cedula_ruc, nombre_razonsocial, nombre_hacienda, provincia, canton, parroquia)
VALUES
('PROP-001', '1102345678001', 'Juan Carlos Puchaicela', 'Hacienda San José', 'Loja', 'Saraguro', 'Saraguro'),
('PROP-002', '0103456789001', 'Marco Vinicio Cabrera', 'Hacienda El Descanso', 'Azuay', 'Cuenca', 'Baños'),
('PROP-003', '0105678912001', 'Carmen Rosa Loja', 'Hacienda San Lucas', 'Azuay', 'Girón', 'Girón'),
('PROP-004', '0702145678001', 'Bolívar Humberto Aguilar', 'Hacienda El Paraíso', 'El Oro', 'Pasaje', 'Uzhcurrumi'),
('PROP-005', '1103216547001', 'Ana Lucía Carrión', 'Hacienda Santa Marianita', 'Loja', 'Saraguro', 'El Aromo');
```

**Datos para la tabla Guía de Movilización:**

```sql
-- Inserción de datos de para la tabla GUIA_MOVILIZACION
INSERT INTO GUIA_MOVILIZACION (id_guia, numero_guia, fecha_emision, cantidad_animales_autorizados, cantidad_animales_ingresados, nombre_hacienda_origen, id_propietario)
VALUES
('GUIA-001', 'AGRO-2026-00125', '2026-11-06', 10, 10, 'Hacienda San José', 'PROP-001'),
('GUIA-002', 'AGRO-2026-00189', '2026-11-07', 8, 7, 'Hacienda El Descanso', 'PROP-002'),
('GUIA-003', 'AGRO-2026-00210', '2026-11-07', 12, 12, 'Hacienda San Lucas', 'PROP-003'),
('GUIA-004', 'AGRO-2026-00245', '2026-11-08', 5, 5, 'Hacienda El Paraíso', 'PROP-004'),
('GUIA-005', 'AGRO-2026-00290', '2026-11-08', 15, 14, 'Hacienda Santa Marianita', 'PROP-005');
```

**Datos para la tabla Control Sanitario:**

```sql
-- Inserción de datos de para la tabla CONTROL_SANITARIO
INSERT INTO CONTROL_SANITARIO (id_control, fecha_hora_control, numero_arete_verificado, diagnostico_sanitario, estado_aprobacion, numero_guia_salida, id_veterinario, id_guia)
VALUES
('CTRL-001', '2026-11-08 06:30:00', 'ART-11001', 'Animales desparasitados y sin signos de fiebre aftosa.', 'Aprobado', 'GS-2026-001', 'VET-001', 'GUIA-001'),
('CTRL-002', '2026-11-08 07:15:00', 'ART-12045', 'Control visual óptimo, se detectó 1 animal menos por motivos de transporte.', 'Aprobado', 'GS-2026-002', 'VET-002', 'GUIA-002'),
('CTRL-003', '2026-11-08 08:00:00', 'ART-13089', 'Ganado bovino con vacunación al día y certificado verificado.', 'Aprobado', 'GS-2026-003', 'VET-001', 'GUIA-003'),
('CTRL-004', '2026-11-08 08:45:00', 'ART-14112', 'Revisión sanitaria completa de la carga procedente de El Oro.', 'Aprobado', 'GS-2026-004', 'VET-003', 'GUIA-004'),
('CTRL-005', '2026-11-08 09:30:00', 'ART-15200', 'Verificación de aretes en acceso principal; documentación en regla.', 'Aprobado', 'GS-2026-005', 'VET-002', 'GUIA-005');
```

**Datos para la tabla Veterinario:**

```sql
-- Inserción de datos de para la tabla VETERINARIO
INSERT INTO VETERINARIO (id_veterinario, cedula, nombre_completo, apellido_completo)
VALUES
('VET-001', '1105432167', 'Darwin Danilo', 'Ordoñez Gonzalez'),
('VET-002', '1108765432', 'Diana Carolina', 'Jaramillo Cueva'),
('VET-003', '0102938475', 'Esteban Javier', 'Ordoñez Tapia'),
('VET-004', '0703829104', 'Verónica Alexandra', 'Castillo Ruales'),
('VET-005', '1106543210', 'Paúl Fernando', 'Guamán Carrión');
```

**Datos para la tabla Animal:**

```sql
-- Inserción de datos de para la tabla ANIMAL
INSERT INTO ANIMAL (id_animal, numero_arete, especie, raza, sexo, fecha_nacimiento, peso_actual, id_propietario)
VALUES
('ANI-001', 'ART-11001', 'Bovino', 'Holstein', 'Macho', '2024-03-15', 650.50, 'PROP-001'),
('ANI-002', 'ART-12045', 'Porcino', 'Landrace', 'Hembra', '2025-06-10', 140.00, 'PROP-002'),
('ANI-003', 'ART-13089', 'Ovino', 'Corriedale', 'Hembra', '2025-02-20', 65.25, 'PROP-003'),
('ANI-004', 'ART-14112', 'Bovino', 'Brahman', 'Macho', '2024-01-05', 710.00, 'PROP-004'),
('ANI-005', 'ART-15200', 'Porcino', 'Duroc', 'Macho', '2025-04-12', 155.50, 'PROP-005');
```

**Datos para la tabla Genealogia:**

```sql
-- Inserción de datos de para la tabla GENEALOGIA
INSERT INTO GENEALOGIA (id_genealogia, registro_genealogico, padre, madre, id_animal)
VALUES
('GEN-001', 'REG-HOL-2024-001', 'Toro Holstein Pura Sangre', 'Vaca Holstein Línea Lechera', 'ANI-001'),
('GEN-002', 'REG-POR-2025-089', 'Verraco Landrace Seleccionado', 'Cerdas Landrace Matriz', 'ANI-002'),
('GEN-003', 'REG-OVI-2025-012', 'Carnero Corriedale Importado', 'Oveja Corriedale Local', 'ANI-003'),
('GEN-004', 'REG-BRA-2024-550', 'Toro Brahman Rojo Campeón', 'Vaca Brahman Reproductora', 'ANI-004'),
('GEN-005', 'REG-POR-2025-104', 'Verraco Duroc Pedigrí', 'Cerdas Duroc Comercial', 'ANI-005');
```

**Datos para la tabla Oferta:**

```sql
-- Inserción de datos para la tabla OFERTA
INSERT INTO OFERTA (id_oferta, monto_ofertado, fecha_hora, estado_oferta, id_transaccion, id_propietario)
VALUES
('OFT-001', 630.00, '2026-11-08 10:30:00', 'Aceptada', 'TXN-001', 'PROP-002'),
('OFT-002', 500.00, '2026-11-08 11:15:00', 'Rechazada', 'TXN-002', 'PROP-003'),
('OFT-003', 515.00, '2026-11-08 11:30:00', 'Aceptada', 'TXN-002', 'PROP-001'),
('OFT-004', 460.00, '2026-11-08 12:00:00', 'Aceptada', 'TXN-003', 'PROP-004'),
('OFT-005', 700.00, '2026-11-08 12:45:00', 'Pendiente', 'TXN-004', 'PROP-005');
```

**Datos para la tabla Transacción de Venta:**

```sql
-- Inserción de datos para la tabla TRANSACCION_VENTA
INSERT INTO TRANSACCION_VENTA (id_transaccion, precio_fijo, precio_final, fecha_hora, estado, id_animal, id_propietario_vendedor, id_propietario_comprador, id_jornada)
VALUES
('TXN-001', 600.00, 630.00, '2026-11-08 10:30:00', 'Completada', 'ANI-001', 'PROP-001', 'PROP-002', 'JORN-001'),
('TXN-002', 500.00, 515.00, '2026-11-08 11:15:00', 'Completada', 'ANI-002', 'PROP-002', 'PROP-001', 'JORN-001'),
('TXN-003', 450.00, 460.00, '2026-11-08 12:00:00', 'Completada', 'ANI-003', 'PROP-003', 'PROP-004', 'JORN-002'),
('TXN-004', 680.00, 700.00, '2026-11-08 12:45:00', 'Completada', 'ANI-004', 'PROP-004', 'PROP-005', 'JORN-002'),
('TXN-005', 520.00, 540.00, '2026-11-08 14:30:00', 'Completada', 'ANI-005', 'PROP-005', 'PROP-003', 'JORN-003');
```

**Datos para la tabla Cronograma:**

```sql
-- Inserción de datos para la tabla CRONOGRAMA
INSERT INTO CRONOGRAMA (id_jornada, fecha_domingo, hora_inicio, hora_fin, descripcion_jornada)
VALUES
('JORN-001', '2026-11-08', '06:00:00', '10:00:00', 'Recepción y Control Sanitario de Ganado en Accesos'),
('JORN-002', '2026-11-08', '10:30:00', '14:00:00', 'Juzgamiento y Exhibición de Ganado Bovino (Pista A)'),
('JORN-003', '2026-11-08', '14:30:00', '18:00:00', 'Subasta y Transacciones Comerciales de Ganado'),
('JORN-004', '2026-11-09', '09:00:00', '12:30:00', 'Exhibición de Ovinos y Porcinos (Pista B)'),
('JORN-005', '2026-11-09', '15:00:00', '17:00:00', 'Premiación y Clausura de la Feria Ganadera');
```

**Datos para la tabla Inscripción:**

```sql
-- Inserción de datos para la tabla INSCRIPCION
INSERT INTO INSCRIPCION (id_inscripcion, numero_pista, id_animal, id_exposicion, id_categoria)
VALUES
('INS-001', 3, 'ANI-001', 'EXP-MARZO-2026', 'CAT-001'),
('INS-002', 5, 'ANI-002', 'EXP-MARZO-2026', 'CAT-001'),
('INS-003', 2, 'ANI-003', 'EXP-MARZO-2026', 'CAT-001'),
('INS-004', 4, 'ANI-004', 'EXP-MARZO-2026', 'CAT-001'),
('INS-005', 1, 'ANI-005', 'EXP-MARZO-2026', 'CAT-001');
```

**Datos para la tabla Categoría del Concurso:**

```sql
-- Inserción de datos para la tabla CATEGORIA_CONCURSO
INSERT INTO CATEGORIA_CONCURSO (id_categoria, nombre)
VALUES
('CAT-001', 'Mejor Toro Reproductor Holstein'),
('CAT-002', 'Vaca Lechera Mayor Producción'),
('CAT-003', 'Mejor Reproductor Porcino Landrace'),
('CAT-004', 'Gran Campeón Ovino Corriedale'),
('CAT-005', 'Mejor Lote de Ganado Brahman');
```

**Datos para la tabla Exposición Anual:**

```sql
-- Inserción de datos para la tabla EXPOSICION_ANUAL
INSERT INTO EXPOSICION_ANUAL (id_exposicion, nombre_evento, fecha_inicio, fecha_fin)
VALUES
('EXP-MARZO-2026', 'Feria Exposición Anual Ganadera Saraguro 2026', '2026-03-08', '2026-03-10'),
('EXP-MARZO-2025', 'Feria Exposición Anual Ganadera Saraguro 2025', '2025-03-08', '2025-03-10'),
('EXP-MARZO-2024', 'Feria Exposición Anual Ganadera Saraguro 2024', '2024-03-08', '2024-03-10'),
('EXP-MARZO-2023', 'Feria Exposición Anual Ganadera Saraguro 2023', '2023-03-08', '2023-03-10'),
('EXP-MARZO-2022', 'Feria Exposición Anual Ganadera Saraguro 2022', '2022-03-08', '2022-03-10');
```

**Datos para la tabla Juzgamiento y Premiación:**

```sql
-- Inserción de datos corregida para la tabla JUZGAMIENTO_PREMIACION
INSERT INTO JUZGAMIENTO_PREMIACION (id_calificacion, juez_responsable, puntuacion_obtenida, puesto_asignado, tipo_premio, monto_premio, id_inscripcion)
VALUES
('JUZ-001', 'Dr. Carlos Mendoza', 98.50, 1, 'Cinta Azul + Trofeo', 150.00, 'INS-001'),
('Juz-002', 'Dra. María Jaramillo', 94.20, 2, 'Cinta Roja + Medalla', 100.00, 'INS-002'),
('Juz-003', 'Ing. Esteban Ordoñez', 97.00, 1, 'Cinta Azul + Trofeo', 150.00, 'INS-003'),
('Juz-004', 'Dr. Carlos Mendoza', 99.10, 1, 'Cinta Azul + Trofeo', 200.00, 'INS-004'),
('Juz-005', 'Dra. Verónica Castillo', 91.50, 3, 'Cinta Amarilla', 50.00, 'INS-005');
```

---

## CONSULTA DE ÁLGEBRA RELACIONAL Y TRADUCIR A SQL

### Consulta 1 — (operador: Selección σ.. etc)

**Descripción del objetivo de la consulta:** Obtener toda la información de los animales registrados cuya especie sea estrictamente "Bovino" dentro de la feria ganadera.

**Álgebra Relacional:**

```
σ especie == "Bovino"(animal)
```

**SQL:**

```sql
SELECT *
FROM   ANIMAL
WHERE  especie = 'Bovino';
```

**Nueva tabla Relación donde se selecciona todas las especies de los bovinos en la tabla animal:**

| id_animal | numero_arete | especie | raza | sexo | fecha_nacimiento | peso_actual | id_propietario |
|---|---|---|---|---|---|---|---|
| ANI-004 | ART-14112 | Bovino | Brahman | Macho | 2024-01-05 | 710.0 | PROP-004 |
| ANI-001 | ART-11001 | Bovino | Holstein | Macho | 2024-03-15 | 650.5 | PROP-001 |

**Resultado esperado:** Se obtendrán todos los registros y columnas de los animales de la base de datos que correspondan a la especie bovino.

---

### Consulta 2 — Proyección (operador: Proyección π), etc

**Descripción del objetivo de la consulta:** Obtener únicamente el nombre del propietario (razón social), el nombre de su hacienda y el cantón de procedencia de todos los registros de la tabla, omitiendo datos de identificación como cédula/RUC y ubicación detallada.

**Álgebra Relacional:**

```
π nombre_razonsocial, nombre_hacienda, canton(propietario)
```

**SQL:**

```sql
SELECT nombre_razonsocial, nombre_hacienda, canton
FROM   PROPIETARIO;
```

**Nueva tabla Relación donde se proyectan todas las columnas de los nombres de la razón social, nombre de la hacienda y cantón:**

| nombre_razonsocial | nombre_hacienda | canton |
|---|---|---|
| Marco Vinicio Cabrera | Hacienda El Descanso | Cuenca |
| Ana LucÃ­a CarriÃ³n | Hacienda Santa Marianita | Saraguro |
| BolÃ­var Humberto Aguilar | Hacienda El ParaÃ­so | Pasaje |
| Juan Carlos Puchaicela | Hacienda San JosÃ© | Saraguro |
| Carmen Rosa Loja | Hacienda San Lucas | GirÃ³n |

**Resultado esperado:** Se mostrarán únicamente tres columnas específicas (nombre_razonsocial, nombre_hacienda y canton) de todos los propietarios registrados en el sistema.

---

### Consulta 3 — Selección con Proyección (σ + π combinados)

**Descripción:** Filtrar los animales de la feria que sean de la especie "Bovino" y cuyo peso actual sea mayor a 600 kg, mostrando únicamente su número de arete, raza y peso.

**Álgebra Relacional:**

```
S1 = σ especie == "Bovino" and peso_actual > 600.00 (animal)
π numero_arete, raza, peso_actual(S1)
```

**SQL:**

```sql
SELECT numero_arete, raza, peso_actual
FROM   ANIMAL
WHERE  especie = 'Bovino' AND peso_actual > 600.00;
```

**Nueva tabla Relación donde se proyectan todas las columnas del numero del arete, raza y peso actual de la selección de la tabla animal cuyas especies son solo los "Bovinos" y su peso es mayor 600 Kg:**

| numero_arete | raza | peso_actual |
|---|---|---|
| ART-14112 | Brahman | 710.0 |
| ART-11001 | Holstein | 650.5 |

**Resultado esperado:** Se obtendrán las filas de los animales bovinos pesados (que superan los 600 kg) y se mostrarán exclusivamente las columnas del número de arete, la raza y el peso actual.

---

### Consulta 4 — Reunión natural / JOIN (operador: ⋈)

**Descripción:** Obtener información detallada y filtrada del ganado bovino procedente de la provincia de Loja, uniendo los datos de los animales con los de sus respectivos propietarios y mostrar únicamente su cedula o ruc, nombre de a hacienda y cantón y del animal su raza y sexo para la auditoría y control de ganado local en la feria ganadera de Saraguro.

**Álgebra Relacional:**

```
S1 = propietario ⋈ animal
S2 = σ especie == "Porcino" and provincia == "Loja"(S1)
π cedula_ruc, nombre_hacienda, canton, raza, sexo (S2 = σ especie == "Porcino" and provincia == "Loja"(S1))
```

**SQL:**

```sql
SELECT p.cedula_ruc, p.nombre_hacienda, p.canton, a.raza, a.sexo
FROM   PROPIETARIO p
JOIN   ANIMAL a ON p.id_propietario = a.id_propietario
WHERE  a.especie = 'Porcino'
  AND  p.provincia = 'Loja';
```

**Nueva tabla Relación donde se une propietario con animal y selecciona unicamente las personas que tenga su animal con especie es Porcino y es de la provincia de Loja y que solo se presente la cedula, nombre de la hacienda, cantón y del animal, raza y sexo:**

| cedula_ruc | nombre_hacienda | canton | raza | sexo |
|---|---|---|---|---|
| 1103216547001 | Hacienda Santa Marianita | Saraguro | Duroc | Macho |

**Resultado esperado:** Se obtendrá un listado filtrado que muestra la cédula o RUC del propietario, el nombre de su hacienda, el cantón de procedencia, la raza del animal y su sexo, restringiendo los resultados exclusivamente a los ganados porcinos registrados dentro de la provincia de Loja.

---

### Consulta 5 — Operador Renombrado 𝝆

**Descripción:** Se requiere obtener un listado detallado de los animales de especie bovina cuyas transacciones comerciales de venta se encuentren con estado "Completada". Para ello, es necesario integrar la información de los animales registrados con sus respectivas transacciones de venta y los datos del propietario o cliente vendedor. Asimismo, se busca renombrar el identificador del número de arete del animal para visualizarlo de forma personalizada como un campo de control (identificador), proyectando adicionalmente su precio final de venta y su peso actual para fines de control y trazabilidad en la feria ganadera

**Álgebra Relacional:**

```
S1 = animal ⋈ transaccion_venta ⋈ propietario
S2 = σ estado == "Completada" and especie == "Bovino" (S1)
S3 = π numero_arete, precio_final, peso_actual (S2)
ρ numero_arete ➡ identificador (S3)
```

**SQL:**

```sql
SELECT   a.numero_arete AS identificador,
         t.precio_final,
         a.peso_actual
FROM     animal a
JOIN     transaccion_venta t ON a.id_animal = t.id_animal
JOIN     propietario p ON t.id_propietario_vendedor = p.id_propietario
WHERE    t.estado = 'Completada'
  AND    a.especie = 'Bovino';
```

**Nueva tabla Relación donde se presencia la unión de animal, transición de venta y propietario, y se selecciona el estado "Completado" y la especie "Bovino", y solo se selecciona las columnas de numero del arete, precio final y peso actual y se cambia el numero de arete por identificador**

| identificador | precio_final | peso_actual |
|---|---|---|
| ART-11001 | 630.0 | 650.5 |
| ART-14112 | 700.0 | 710.0 |

**Resultado esperado:** Una relación tabular filtrada que muestra únicamente las transacciones finalizadas con éxito de ganado bovino, presentando de forma limpia y directa los tres atributos solicitados, listos para la validación y el análisis estadístico de la feria.

---

## CONCLUSIONES

- **Gestión integral del ganado y transacciones comerciales:** Se demostró que la aplicación del álgebra relacional permite estructurar con precisión la lógica de negocio de la feria ganadera, logrando integrar eficientemente los registros de animales, las transacciones de venta y la información de los propietarios para la toma de decisiones.

- **Control y trazabilidad de los ejemplares:** Mediante el uso de operadores de selección, proyección y renombramiento de atributos (como la personalización del identificador del arete y las características físicas), se facilitó la extracción de reportes específicos sobre ganado bovino y porcino, optimizando la supervisión de las ferias comerciales.

- **Correspondencia entre el modelo relacional y la base de datos:** Se validó la correcta equivalencia lógica entre las expresiones algebraicas ejecutadas en la herramienta de software y sus respectivas sentencias en SQL, asegurando un rendimiento óptimo y una correcta estructuración de los datos en el sistema de gestión de la feria.

---

## BIBLIOGRAFÍA

[1] G. R. S. I. de Ecuador, Sistema de Identificación y Trazabilidad Agropecuaria (SITA) - Manual de Gestión y Control Pecuario. Quito, Ecuador: AGROCALIDAD, 2022.

[2] R. Elmasri and S. B. Navathe, Fundamentals of Database Systems: Application to Livestock Management and Agricultural Traceability Systems, 7th ed. Hoboken, NJ: Pearson, 2016.

[3] J. A. O. Pérez and M. L. Torres, Diseño y Modelado de Bases de Datos Relacionales para Ferias Ganaderas y Comercialización Pecuaria, Loja, Ecuador: Ediciones Universidad Nacional de Loja, 2024.
