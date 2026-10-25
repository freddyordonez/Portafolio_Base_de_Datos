<div align="center">

# 💻 Scripts SQL (DDL)

*Repositorio de los scripts de creación de bases de datos para cada ejercicio.*

</div>
---

## 🗄️ Ejemplo 1: Sistema de Biblioteca

### 📋 Tablas Creadas
* `Socio`: Almacena la información de los socios registrados en la biblioteca.
* `Libro`: Registra los libros disponibles, fechas de retiro y devolución, y la relación con el socio.
* `Autor`: Contiene los datos de los autores y su vinculación con los libros.

### 🖼️ Captura de las Tablas / Base de Datos

#### 👤 Tabla Socio
<img width="1316" height="668" alt="image" src="https://github.com/user-attachments/assets/8ec94b4f-3a88-4506-8370-ba552f4199f3" />

#### 📖 Tabla Libro
<img width="1097" height="677" alt="image" src="https://github.com/user-attachments/assets/6f65b990-7914-48bd-842e-a80c914c0164" />


#### ✍️ Tabla Autor
<img width="1297" height="644" alt="image" src="https://github.com/user-attachments/assets/a97b67df-7078-4e67-be62-e08243874565" />

### ⚙️ Código SQL
```sql
-- Tabla Socio
CREATE TABLE Socio (
    id_socio VARCHAR(20) PRIMARY KEY,
    nombre VARCHAR(50) NOT NULL
);

-- Tabla Libro (con claves foráneas hacia Socio)
CREATE TABLE Libro (
    id_libro VARCHAR(20) PRIMARY KEY,
    titulo VARCHAR(100) NOT NULL,
    fecha_retiro DATE,
    fecha_devolucion DATE,
    id_socio VARCHAR(20),
    CONSTRAINT fk_libro_socio FOREIGN KEY (id_socio) REFERENCES Socio(id_socio)
);

-- Tabla Autor (con claves foráneas hacia Libro)
CREATE TABLE Autor (
    id_autor VARCHAR(20) PRIMARY KEY,
    nombre_autor VARCHAR(50) NOT NULL,
    id_libro VARCHAR(20),
    CONSTRAINT fk_autor_libro FOREIGN KEY (id_libro) REFERENCES Libro(id_libro)
);

```
---

## 🗄️ Ejemplo 2: Pedidos de Restaurante

### 📋 Tablas Creadas
* `Cliente`: Almacena la información de los clientes del restaurante.
* `Mesero`: Almacena los datos del personal de meseros que atienden los pedidos.
* `Pedido`: Registra la información de cada pedido realizado (precio, cantidad) y sus relaciones con el cliente y el mesero.
* `Plato`: Contiene los detalles de los platos asociados a un pedido específico.
* `Categoria`: Clasifica y vincula los platos según su categoría correspondiente.

### 🖼️ Captura de las Tablas

#### 👤 Tabla Cliente
<img width="839" height="602" alt="image" src="https://github.com/user-attachments/assets/64ad65e0-2df3-4b82-802b-810c7fc0e06f" />


#### 🧑‍🍳 Tabla Mesero
<img width="745" height="615" alt="image" src="https://github.com/user-attachments/assets/b4603ff1-28b0-483f-9644-6ad28e9e5faf" />

#### 📦 Tabla Pedido
<img width="846" height="614" alt="image" src="https://github.com/user-attachments/assets/3c859614-e596-4260-9ae9-6ef0d614f5d1" />

#### 🍽️ Tabla Plato
<img width="699" height="616" alt="image" src="https://github.com/user-attachments/assets/b9c3116a-f343-431a-b75c-d6406cded00a" />


#### 📂 Tabla Categoria
<img width="689" height="612" alt="image" src="https://github.com/user-attachments/assets/db307655-4268-4de5-9302-591865a66e54" />


### ⚙️ Código SQL
```sql
-- Tabla Cliente
CREATE TABLE Cliente (
    id_cliente VARCHAR(20) PRIMARY KEY,
    nombre_cliente VARCHAR(50) NOT NULL
);

-- Tabla Mesero
CREATE TABLE Mesero (
    id_mesero VARCHAR(20) PRIMARY KEY,
    nombre_mesero VARCHAR(50) NOT NULL
);

-- Tabla Pedido (con claves foráneas hacia Cliente y Mesero)
CREATE TABLE Pedido (
    id_pedido VARCHAR(20) PRIMARY KEY,
    precio DECIMAL(10,2),
    cantidad INT,
    id_cliente VARCHAR(20),
    id_mesero VARCHAR(20),
    CONSTRAINT fk_pedido_cliente FOREIGN KEY (id_cliente) REFERENCES Cliente(id_cliente),
    CONSTRAINT fk_pedido_mesero FOREIGN KEY (id_mesero) REFERENCES Mesero(id_mesero)
);

-- Tabla Plato (con clave foránea hacia Pedido)
CREATE TABLE Plato (
    id_plate VARCHAR(20) PRIMARY KEY,
    nombre_plato VARCHAR(50) NOT NULL,
    precio_actual DECIMAL(10,2),
    id_pedido VARCHAR(20),
    CONSTRAINT fk_plato_pedido FOREIGN KEY (id_pedido) REFERENCES Pedido(id_pedido)
);
```
---

## 🗄️ Ejemplo 3: Clínica Médica

### 📋 Tablas Creadas
* `Paciente`: Almacena la información personal de los pacientes registrados en la clínica.
* `Especialidad`: Define las distintas especialidades médicas disponibles.
* `Medico`: Contiene los datos de los médicos y su vinculación con sus respectivas especialidades.
* `Receta`: Registra las recetas médicas emitidas con sus dosis y duración.
* `Cita`: Controla la programación de las citas médicas, relacionando al paciente, el médico y la receta.
* `Medicamento`: Almacena los medicamentos asociados a cada receta.

### 🖼️ Captura de las Tablas

#### 🧑‍⚕️ Tabla Paciente
<img width="1074" height="629" alt="image" src="https://github.com/user-attachments/assets/3a78e54f-cbf3-4305-86dc-4256045ff0b8" />



#### 🩺 Tabla Especialidad
<img width="1073" height="654" alt="image" src="https://github.com/user-attachments/assets/e5d5fe3f-c097-46b6-95c0-f2887064a2b9" />


#### 👨‍⚕️ Tabla Medico
<img width="1076" height="656" alt="image" src="https://github.com/user-attachments/assets/6b24eded-ae14-489e-a69d-7953b7d74fa0" />


#### 💊 Tabla Receta
<img width="1068" height="657" alt="image" src="https://github.com/user-attachments/assets/9dde830f-e6fc-44a2-aecf-ae3fd76a56e5" />


#### 📅 Tabla Cita
<img width="1172" height="658" alt="image" src="https://github.com/user-attachments/assets/ddd063da-8e11-4aa9-924a-a3e5b2e3141f" />


#### 🧪 Tabla Medicamento
<img width="1073" height="655" alt="image" src="https://github.com/user-attachments/assets/348aab7c-9b56-4b2c-899a-7e90ad4f375b" />

### ⚙️ Código SQL
```sql
-- Tabla Paciente
CREATE TABLE Paciente (
    id_paciente VARCHAR(20) PRIMARY KEY,
    nombre_paciente VARCHAR(50) NOT NULL
);

-- Tabla Especialidad
CREATE TABLE Especialidad (
    id_especialidad VARCHAR(20) PRIMARY KEY,
    nombre_especialidad VARCHAR(50) NOT NULL
);

-- Tabla Medico (con claves foráneas hacia Especialidad)
CREATE TABLE Medico (
    id_medico VARCHAR(20) PRIMARY KEY,
    nombre_medico VARCHAR(50) NOT NULL,
    id_especialidad VARCHAR(20),
    CONSTRAINT fk_medico_especialidad FOREIGN KEY (id_especialidad) REFERENCES Especialidad(id_especialidad)
);

-- Tabla Receta
CREATE TABLE Receta (
    id_receta VARCHAR(20) PRIMARY KEY,
    dosis VARCHAR(100),
    duracion VARCHAR(50)
);

-- Tabla Cita (con claves foráneas hacia Paciente, Medico, Receta)
CREATE TABLE Cita (
    id_cita VARCHAR(20) PRIMARY KEY,
    fecha DATE,
    hora TIME,
    id_paciente VARCHAR(20),
    id_medico VARCHAR(20),
    id_receta VARCHAR(20),
    CONSTRAINT fk_cita_paciente FOREIGN KEY (id_paciente) REFERENCES Paciente(id_paciente),
    CONSTRAINT fk_cita_medico FOREIGN KEY (id_medico) REFERENCES Medico(id_medico),
    CONSTRAINT fk_cita_receta FOREIGN KEY (id_receta) REFERENCES Receta(id_receta)
);

-- Tabla Medicamento (con claves foráneas hacia, Receta)
CREATE TABLE Medicamento (
    id_medicamento VARCHAR(20) PRIMARY KEY,
    nombre_medicamento VARCHAR(50) NOT NULL,
    id_receta VARCHAR(20),
    CONSTRAINT fk_medicamento_receta FOREIGN KEY (id_receta) REFERENCES Receta(id_receta)
);

```

## 🗄️ Ejemplo 4: Sistema de Aerolínea

### 📋 Tablas Creadas
* `Pasajeros`: Almacena la información de los pasajeros, su número, asiento y tarifa.
* `Vuelos`: Registra los vuelos con su número, fecha, origen, destino y la identificación del avión.
* `Avion`: Contiene la identificación única de cada avión.

### 🖼️ Captura de las Tablas

#### 🎫 Tabla Pasajeros
<img width="1055" height="657" alt="image" src="https://github.com/user-attachments/assets/789c30b9-e0ba-4ae6-b476-52c0858caf38" />


#### ✈️ Tabla Vuelos
<img width="951" height="651" alt="image" src="https://github.com/user-attachments/assets/d99f8167-a1e5-45cd-808d-ef114208d422" />


#### 🛩️ Tabla Avion
<img width="744" height="654" alt="image" src="https://github.com/user-attachments/assets/73f69b57-582d-4f99-95a1-6c600e0a64de" />


### ⚙️ Código SQL
```sql
-- Tabla Avion
CREATE TABLE Avion (
    id_avion VARCHAR(20) PRIMARY KEY,
    modelo_avion VARCHAR(50) NOT NULL
);

-- Tabla Vuelos (con claves foráneas hacia Avion)
CREATE TABLE Vuelos (
    numero VARCHAR(20) PRIMARY KEY,
    fecha DATE,
    origen VARCHAR(100),
    destino VARCHAR(100),
    id_avion VARCHAR(20),
    CONSTRAINT fk_vuelos_avion FOREIGN KEY (id_avion) REFERENCES Avion(id_avion)
);

-- Tabla Pasajeros (con claves foráneas hacia Vuelos)
CREATE TABLE Pasajeros (
    id_pasajero VARCHAR(20) PRIMARY KEY,
    nombre_pasajero VARCHAR(50) NOT NULL,
    numero VARCHAR(20),
    asiento VARCHAR(10),
    tarifa DECIMAL(10,2),
    CONSTRAINT fk_pasajeros_vuelos FOREIGN KEY (numero) REFERENCES Vuelos(numero)
);
```
---

## 🗄️ Ejemplo 5: Empresa Discográfica

### 📋 Tablas Creadas
* `Manager`: Almacena la información de los managers de los artistas (Id y nombre).
* `Artista`: Contiene los datos de los artistas (NIF, nombre e id del manager).
* `Participa`: Tabla intermedia que relaciona al artista con los eventos (NIF, id).
* `Evento`: Registra los eventos musicales (id, fecha, asistencia).

### 🖼️ Captura de las Tablas

#### 👔 Tabla Manager
<img width="678" height="656" alt="image" src="https://github.com/user-attachments/assets/271d5415-7095-40e2-a3fb-aeb519c521ce" />


#### 🎤 Tabla Artista
<img width="674" height="657" alt="image" src="https://github.com/user-attachments/assets/fb485dae-5ab6-4dc5-9838-ba008a885da4" />


#### 🤝 Tabla Participa
<img width="681" height="654" alt="image" src="https://github.com/user-attachments/assets/0769cf24-414c-4635-912c-fbc5c6f34cd5" />


#### 📅 Tabla Evento
<img width="672" height="654" alt="image" src="https://github.com/user-attachments/assets/b5318212-5a71-4309-b910-5e3329acb5e9" />


### ⚙️ Código SQL
```sql
-- Tabla Manager
CREATE TABLE Manager (
    Id VARCHAR(20) PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL
);

-- Tabla Artista (con claves foráneas hacia Manager)
CREATE TABLE Artista (
    NIF VARCHAR(20) PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL,
    Id VARCHAR(20),
    CONSTRAINT fk_artista_manager FOREIGN KEY (Id) REFERENCES Manager(Id)
);
-- Tabla Evento
CREATE TABLE Evento (
    id VARCHAR(20) PRIMARY KEY,
    fecha DATE,
    asis INT
);

-- Tabla Participa (con claves foráneas hacia Artista, Evento)
CREATE TABLE Participa (
    NIF VARCHAR(20),
    id VARCHAR(20),
    CONSTRAINT pk_participa PRIMARY KEY (NIF, id),
    CONSTRAINT fk_participa_artista FOREIGN KEY (NIF) REFERENCES Artista(NIF),
    CONSTRAINT fk_participa_evento FOREIGN KEY (id) REFERENCES Evento(id)
);
```
---

## 🗄️ Ejemplo 6: Tienda Informática

### 📋 Tablas Creadas
* `Cliente`: Almacena la información de los clientes (id_cliente, nombre, apellidos, dirección).
* `Telefono_celular`: Registra los números de teléfono asociados a cada cliente.
* `Producto`: Contiene los detalles del inventario (código, descripción, precio, número de existencias).
* `Compra`: Registra las transacciones de compra realizadas por los clientes (fecha, id_cliente, código).
* `Proveedor`: Almacena los datos de los proveedores (identificador, nombres, apellidos, dirección, provincia).
* `Num_telefono_celular`: Registra los teléfonos de contacto de los proveedores.
* `Suministra`: Tabla intermedia que relaciona los productos suministrados por cada proveedor.

### 🖼️ Captura de las Tablas

#### 👤 Tabla Cliente
<img width="837" height="657" alt="image" src="https://github.com/user-attachments/assets/d93fe9f5-9496-4e7a-bfc7-6adb38d96f38" />


#### 📱 Tabla Telefono_celular
<img width="486" height="657" alt="image" src="https://github.com/user-attachments/assets/47b6a20e-3192-4be7-81a1-abb9029ab51b" />


#### 📦 Tabla Producto
<img width="923" height="656" alt="image" src="https://github.com/user-attachments/assets/28407c34-7d53-4931-9f6b-fcc53d4fc59e" />


#### 🛒 Tabla Compra
<img width="629" height="657" alt="image" src="https://github.com/user-attachments/assets/b0093759-c309-4c5b-91ea-01d673af7176" />


#### 🚚 Tabla Proveedor
<img width="1059" height="665" alt="image" src="https://github.com/user-attachments/assets/96d1d53e-eb35-4cc7-abff-4810ca704f5a" />


#### 📞 Tabla Num_telefono_celular
<img width="1043" height="658" alt="image" src="https://github.com/user-attachments/assets/001996c4-8a06-442e-a2c3-d8b54a190015" />

#### 🤝 Tabla Suministra
<img width="700" height="640" alt="image" src="https://github.com/user-attachments/assets/e7a4e5ff-3ce8-4c08-ad08-0e31cf828d81" />


### ⚙️ Código SQL
```sql
-- Tabla Cliente
CREATE TABLE Cliente (
    id_cliente VARCHAR(20) PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL,
    apellidos VARCHAR(100) NOT NULL,
    direccion VARCHAR(255)
);

-- Tabla Telefono (con claves foráneas hacia Cliente)
CREATE TABLE Telefono_celular (
    telefono VARCHAR(20) PRIMARY KEY,
    id_cliente VARCHAR(20),
    CONSTRAINT fk_telefono_cliente FOREIGN KEY (id_cliente) REFERENCES Cliente(id_cliente)
);

-- Tabla Producto
CREATE TABLE Producto (
    codigo VARCHAR(20) PRIMARY KEY,
    descripcion VARCHAR(255) NOT NULL,
    precio DECIMAL(10,2),
    numero_existencias INT
);

-- Tabla Proveedor
CREATE TABLE Proveedor (
    identificador VARCHAR(20) PRIMARY KEY,
    nombres VARCHAR(100) NOT NULL,
    apellidos VARCHAR(100) NOT NULL,
    direccion VARCHAR(255),
    provincial VARCHAR(100)
);

-- Tabla Numero Celular (con claves foráneas hacia Proveedor)
CREATE TABLE Num_telefono_celular (
    telefono VARCHAR(20) PRIMARY KEY,
    identificador VARCHAR(20),
    CONSTRAINT fk_num_tel_proveedor FOREIGN KEY (identificador) REFERENCES Proveedor(identificador)
);

-- Tabla Compra (con claves foráneas hacia Cliente, Producto)
CREATE TABLE Compra (
    fecha DATE,
    id_cliente VARCHAR(20),
    codigo VARCHAR(20),
    CONSTRAINT fk_compra_cliente FOREIGN KEY (id_cliente) REFERENCES Cliente(id_cliente),
    CONSTRAINT fk_compra_producto FOREIGN KEY (codigo) REFERENCES Producto(codigo)
);

-- Tabla Suministra (con claves foráneas hacia Producto, Proveedor)
CREATE TABLE Suministra (
    codigo VARCHAR(20),
    suministro VARCHAR(100),
    identificador VARCHAR(20),
    CONSTRAINT fk_suministra_producto FOREIGN KEY (codigo) REFERENCES Producto(codigo),
    CONSTRAINT fk_suministra_proveedor FOREIGN KEY (identificador) REFERENCES Proveedor(identificador)
);

```
---

## 🗄️ Ejemplo 7: Discos Musicales

### 📋 Tablas Creadas
* `Disco`: Almacena la información de los discos musicales (id_disco, título, precio, id_genero, identificador).
* `Genero_Musical`: Define los géneros musicales disponibles (id_genero)[cite: 8].
* `Cantante`: Contiene los datos de los cantantes (Nombre, país, identificador)[cite: 8].
* `Canción`: Registra las canciones (Identificador, título)[cite: 8].
* `Tiene`: Tabla que relaciona los discos y las canciones (id, identificador, posición)[cite: 8].

### 🖼️ Captura de las Tablas

#### 💿 Tabla Disco
<img width="1023" height="657" alt="image" src="https://github.com/user-attachments/assets/88b93fb3-1b5e-4aba-b5b9-8f81628eadc9" />


#### 🎵 Tabla Genero_Musical
<img width="882" height="644" alt="image" src="https://github.com/user-attachments/assets/f7ed5ef1-dfa3-49a6-8e17-9ae174af4478" />


#### 🎤 Tabla Cantante
<img width="887" height="655" alt="image" src="https://github.com/user-attachments/assets/a3704499-3d34-4c23-87b8-e5d30e4330f3" />

#### 🎶 Tabla Canción
<img width="888" height="646" alt="image" src="https://github.com/user-attachments/assets/0d6825a5-29db-4dce-be2f-c4863483b9c5" />


#### 🔗 Tabla Tiene
<img width="884" height="676" alt="image" src="https://github.com/user-attachments/assets/30b0c14f-3a5a-46c8-b199-b94d67a90c74" />

### ⚙️ Código SQL
```sql
-- Tabla Cliente Genero_Musical
CREATE TABLE Genero_Musical (
    id_genero VARCHAR(20) PRIMARY KEY,
    nombre_genero VARCHAR(50) NOT NULL
);

-- Tabla Cantante
CREATE TABLE Cantante (
    identificador VARCHAR(20) PRIMARY KEY,
    Nombre VARCHAR(100) NOT NULL,
    pais VARCHAR(50)
);

-- Tabla Disco (con claves foráneas hacia Musical, Cantante)
CREATE TABLE Disco (
    id_disco VARCHAR(20) PRIMARY KEY,
    titulo VARCHAR(100) NOT NULL,
    precio DECIMAL(10,2),
    id_genero VARCHAR(20),
    identificador VARCHAR(20),
    CONSTRAINT fk_disco_genero FOREIGN KEY (id_genero) REFERENCES Genero_Musical(id_genero),
    CONSTRAINT fk_disco_cantante FOREIGN KEY (identificador) REFERENCES Cantante(identificador)
);

-- Tabla Cancion
CREATE TABLE Cancion (
    Identificador VARCHAR(20) PRIMARY KEY,
    titulo VARCHAR(100) NOT NULL
);

-- Tabla Tiene (con claves foráneas hacia Disco, CanCION)

CREATE TABLE Tiene (
    id VARCHAR(20),
    identificador VARCHAR(20),
    posicion INT,
    CONSTRAINT pk_tiene PRIMARY KEY (id, identificador),
    CONSTRAINT fk_tiene_disco FOREIGN KEY (id) REFERENCES Disco(id_disco),
    CONSTRAINT fk_tiene_cancion FOREIGN KEY (identificador) REFERENCES Cancion(Identificador)
);
```
---

## 🗄️ Ejemplo 8: Camiones

### 📋 Tablas Creadas
* `Provincia`: Almacena la información de las provincias (código y nombre).
* `Destino`: Registra los destinos de los paquetes (id_destinatario, nombre y dirección).
* `Camionero`: Contiene los datos de los conductores (cédula, nombre, teléfono y dirección).
* `Paquete`: Almacena la información de los paquetes a enviar y sus relaciones con provincia, destino y camionero.
* `Camion`: Registra los vehículos de transporte, sus características y el camionero asignado.

### 🖼️ Captura de las Tablas

#### 🗺️ Tabla Provincia
<img width="884" height="653" alt="image" src="https://github.com/user-attachments/assets/22bdfb25-7736-442c-adea-b25a44b95bc6" />


#### 📍 Tabla Destino
<img width="891" height="653" alt="image" src="https://github.com/user-attachments/assets/33d3843e-de28-498e-b1df-68f59e6dce63" />


#### 👤 Tabla Camionero
<img width="885" height="656" alt="image" src="https://github.com/user-attachments/assets/6afe5c1e-ecf0-4ac5-b021-13607f414187" />


#### 📦 Tabla Paquete
<img width="1244" height="656" alt="image" src="https://github.com/user-attachments/assets/1035b73d-ac5e-47d6-a8e5-33b333c16e1d" />


#### 🚚 Tabla Camion
<img width="959" height="656" alt="image" src="https://github.com/user-attachments/assets/eb55a639-8b62-4a27-9594-b9dfbde44179" />

### ⚙️ Código SQL
```sql
CREATE TABLE Provincia (
    codigo VARCHAR(20) PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL
);

-- Tabla Destino
CREATE TABLE Destino (
    id_destinatario VARCHAR(20) PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL,
    direccion VARCHAR(255)
);

-- Tabla Camionero
CREATE TABLE Camionero (
    cedula VARCHAR(20) PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL,
    telefono VARCHAR(20),
    direccion VARCHAR(255)
);

-- Tabla Paquete (con claves foráneas hacia destino, Camionero)
CREATE TABLE Paquete (
    código VARCHAR(20) PRIMARY KEY,
    descripcion VARCHAR(255) NOT NULL,
    direccion VARCHAR(255),
    id_destinatario VARCHAR(20),
    cedula VARCHAR(20),
    CONSTRAINT fk_paquete_destino FOREIGN KEY (id_destinatario) REFERENCES Destino(id_destinatario),
    CONSTRAINT fk_paquete_camionero FOREIGN KEY (cedula) REFERENCES Camionero(cedula)
);

-- Tabla Camion(con claves foráneas hacia Camionero)
CREATE TABLE Camion (
    matricula VARCHAR(20) PRIMARY KEY,
    modelo VARCHAR(100) NOT NULL,
    potencia INT,
    tipo VARCHAR(50),
    cedula VARCHAR(20),
    CONSTRAINT fk_camion_camionero FOREIGN KEY (cedula) REFERENCES Camionero(cedula)
);
```
## 🗄️ Ejemplo 9: Veterinaria

### 📋 Tablas Creadas
* `Propietario`: Almacena la información de los dueños de las mascotas (cédula, nombres, dirección).
* `Telefonos`: Registra los números telefónicos adicionales de los propietarios.
* `Familiar`: Contiene los datos de los familiares vinculados al propietario.
* `Telf_familiar`: Almacena los teléfonos de contacto de los familiares.
* `Mascota`: Registra los datos de las mascotas (id, fecha de nacimiento, nombre, tipo) y su dueño.
* `Persona`: Contiene la información del personal clínico y veterinarios (cédula, nombre, código, fecha de alta, especialidad).
* `Auxiliar`: Registra los datos del personal auxiliar de la clínica (cédula, nombre, código, base de cotización).
* `Consulta`: Controla el registro de las consultas médicas realizadas a las mascotas por el personal.

### 🖼️ Captura de las Tablas

#### 👤 Tabla Propietario
<img width="1720" height="648" alt="image" src="https://github.com/user-attachments/assets/c93c0cb4-5a97-4ead-a9cd-023487b0c895" />


#### 📞 Tabla Telefonos
<img width="1712" height="655" alt="image" src="https://github.com/user-attachments/assets/4e56fcc0-6ea7-46f1-b445-d2fa17f121b6" />


#### 👥 Tabla Familiar
<img width="1697" height="656" alt="image" src="https://github.com/user-attachments/assets/c164e45d-64a0-4961-bd40-cdf3a5d48c04" />


#### 📱 Tabla Telf_familiar
<img width="1717" height="656" alt="image" src="https://github.com/user-attachments/assets/60bcb670-a9f8-46cb-9851-11e8b657fedb" />


#### 🐾 Tabla Mascota
<img width="1711" height="654" alt="image" src="https://github.com/user-attachments/assets/c6843a3a-fda6-4eee-baa1-4c021633908b" />


#### 👨‍⚕️ Tabla Persona
<img width="1696" height="656" alt="image" src="https://github.com/user-attachments/assets/a294990e-8db9-42e8-8c10-2fae0ba22ba0" />


#### 🧑‍💼 Tabla Auxiliar
<img width="1714" height="669" alt="image" src="https://github.com/user-attachments/assets/813fe711-c0a0-4d0f-ae69-baa17ab349e4" />


#### 🩺 Tabla Consulta
<img width="1703" height="651" alt="image" src="https://github.com/user-attachments/assets/51e045dd-a0a7-4068-a0c6-d9383c4cc322" />


### ⚙️ Código SQL
```sql
-- Tabla Propietario
CREATE TABLE vet_propietario (
    cédula VARCHAR(20) PRIMARY KEY,
    nombres VARCHAR(100) NOT NULL,
    dirección VARCHAR(255)
);

-- Tabla Telefonos
CREATE TABLE vet_telefonos (
    telefono VARCHAR(20) PRIMARY KEY,
    cédula VARCHAR(20),
    CONSTRAINT fk_vet_telefonos_propietario FOREIGN KEY (cédula) REFERENCES vet_propietario(cédula)
);

-- Tabla Familiar
CREATE TABLE vet_familiar (
    cédula VARCHAR(20) PRIMARY KEY,
    nombres VARCHAR(100) NOT NULL,
    CONSTRAINT fk_vet_familiar_propietario FOREIGN KEY (cédula) REFERENCES vet_propietario(cédula)
);

-- Tabla Telefonos Familiar
CREATE TABLE vet_telf_familiar (
    telefono VARCHAR(20) PRIMARY KEY,
    cédula VARCHAR(20),
    CONSTRAINT fk_vet_telf_familiar FOREIGN KEY (cédula) REFERENCES vet_familiar(cédula)
);

-- Tabla Mascota
CREATE TABLE vet_mascota (
    id VARCHAR(20) PRIMARY KEY,
    fecha_nacimiento DATE,
    nombre VARCHAR(100) NOT NULL,
    tipo VARCHAR(50),
    cédula VARCHAR(20),
    CONSTRAINT fk_vet_mascota_propietario FOREIGN KEY (cédula) REFERENCES vet_propietario(cédula)
);

-- Tabla Persona
CREATE TABLE vet_persona (
    cédula VARCHAR(20) PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL,
    código VARCHAR(20),
    fecha_alta DATE,
    especialidad VARCHAR(100)
);

-- Tabla Auxiliar
CREATE TABLE vet_auxiliar (
    cédula VARCHAR(20) PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL,
    código VARCHAR(20),
    base_cotizacion DECIMAL(10,2)
);

-- Tabla Consulta
CREATE TABLE vet_consulta (
    id VARCHAR(20) PRIMARY KEY,
    fecha_atencion DATE,
    diagnostico VARCHAR(255),
    id_mascota VARCHAR(20),
    cédula VARCHAR(20),
    CONSTRAINT fk_vet_consulta_mascota FOREIGN KEY (id_mascota) REFERENCES vet_mascota(id),
    CONSTRAINT fk_vet_consulta_persona FOREIGN KEY (cédula) REFERENCES vet_persona(cédula)
);

```
<!-- Botón para regresar a la unidad principal -->
<div align="center">
  <a href="UNIDAD1.md">
    <img src="https://img.shields.io/badge/⬅_Volver_a_la_Unidad_1-555555?style=for-the-badge" alt="Volver a Unidad 1" />
  </a>
</div>
