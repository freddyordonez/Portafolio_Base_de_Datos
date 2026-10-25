<div align="center">

# 🔗 Modelo Relacional: Ejemplos y Prácticas

*Repositorio de las evidencias y esquemas relacionales correspondientes al diseño lógico de bases de datos.*

</div>

---

## 📌 Parte 1: Ejemplos Guiados

### 📚 Ejemplo 1: Sistema de Biblioteca
> **Contexto:** Una biblioteca registra libros y autores, socios y los préstamos con fecha de retiro y devolución, adaptado estrictamente al esquema relacional de tus apuntes.

```text
Socio (id_socio, ...)
Libro (fecha_retiro, fecha_devolucion, id_socio, id_libro)
Autor (id_autor, id_libro)
```
<img width="1320" height="561" alt="image" src="https://github.com/user-attachments/assets/a959b37a-f95b-4ed3-8ed5-7e4930bec465" />


### 🍽️ Ejemplo 2: Pedidos de Restaurante
> **Contexto:** Los clientes realizan pedidos que contienen varios platos con distinta cantidad. Los platos se agrupan en categorías, cada pedido lo atiende un único mesero, y se registra el precio actual del plato.

```text
Pedido (precio, cantidad, id_pedido, id_cliente, id_mesero)
Cliente (id_cliente)
Mesero (id_mesero)
Plato (id_plate, precio_actual, id_pedido)
Categoria (id_categoria, id_plato)
```
<img width="1151" height="899" alt="image" src="https://github.com/user-attachments/assets/1eb969a3-e613-426d-a0f4-2c1780950d80" />


### 🏥 Ejemplo 3: Clínica Médica
> **Contexto:** Los pacientes solicitan atención médica en la clínica. Cada turno lo atiende un médico a un paciente especificando fecha, hora y consultorio. De algunas atenciones se genera una receta que incluye medicamentos con dosis y duración, y cada médico pertenece a una especialidad.

```text
Paciente (id_paciente)
Cita (id_cita, fecha, hora, id_paciente, id_medico, id_receta)
Medico (id_medico, id_especialidad)
Especialidad (id_especialidad)
Receta (id_receta, dosis, duracion)
Medicamento (id_medicamento, id_receta)
```
<img width="1319" height="1191" alt="image" src="https://github.com/user-attachments/assets/3c0527ab-dffb-44fd-b67d-dfaceae894d4" />


### ✈️ Ejemplo 4: Sistema de Aerolínea
> **Contexto:** Una aerolínea opera vuelos (cada uno con número, fecha, origen y destino) realizados por un avión. Los pasajeros realizan reservas indicando asiento y tarifa.

```text
Pasajeros (id_pasajero, número, asiento, tarifa)
Vuelos (numero, fecha, origen, destino, id_avion)
Avión (id_avion)
```
<img width="1148" height="689" alt="image" src="https://github.com/user-attachments/assets/c6ede584-2634-4d65-a773-642a13984f2c" />

## 🚀 Parte 2: Ejercicios Propuestos
### 🎵 Ejercicio 5: Empresa Discográfica
> **Contexto:** Una empresa discográfica necesita modelar sus recursos: un manager representa a una serie de artistas, y los artistas participan en eventos de promoción para dar a conocer sus trabajos registrando identificador, fecha y asistentes.

```text
Manager (Id, nombre)
Artista (NIF, nombre, id)
Participa (NIF, id)
Evento (id, fecha, asis)
```
<img width="1185" height="937" alt="image" src="https://github.com/user-attachments/assets/4d91f582-f69c-4b1f-94f6-7dfdd5b1e11c" />


### 💻 Ejercicio 6: Tienda Informática
> **Contexto:** Aplicación para la gestión de ventas e inventario de una tienda informática. Se gestionan productos, clientes, compras, proveedores y suministros, registrando sus respectivos códigos, direcciones y teléfonos.

```text
Cliente (id_cliente, nombre, apellidos, direccion)
Telefono_celular (telefono, id_cliente)
Producto (codigo, descripción, precio, número_existencias)
Compra (fecha, id_cliente, código)
Proveedor (identificador, nombres, apellidos, direccion, provincial)
Num_telefono_celular (telefono, identificador)
Suministra (codigo, suministro, identificador)
```
<img width="918" height="1001" alt="image" src="https://github.com/user-attachments/assets/9f89186f-181c-4241-9a70-75e872bcc4cd" />

### 💿 Ejercicio 7: Discos Musicales
> **Contexto:** Gestión de ventas de discos de diferentes géneros musicales y cantantes. Todo disco pertenece a un cantante y tiene un género, precio y un conjunto de canciones donde interesa conocer la posición.

```text
Disco (id_disco, título, precio, id_genero, identificador)
Genero_Musical (id_genero)
Cantante (Nombre, país, identificador)
Canción (Identificador, título)
Tiene (id, identificador, posición)
```
<img width="833" height="1008" alt="image" src="https://github.com/user-attachments/assets/c351bbe0-3931-4d23-9962-9425f6a955f8" />

### 🚚 Ejercicio 8: Camiones
> **Contexto:** Gestión de una empresa de transporte que reparte paquetes por toda España. Se registran camioneros, paquetes, provincias de destino y camiones conducidos por los empleados.

```text
Paquete (código, descripción, dirección, código, id_destinatario, cedula)
Provincia (código, nombre)
Destino (id_destinatario, nombre, direccion)
Camionero (cedula, nombre, telefono, direccion)
Camion (matricula, modelo, potencia, tipo, cedula)
```
<img width="820" height="908" alt="image" src="https://github.com/user-attachments/assets/8c7b2b59-e509-4ea1-b159-a9ee533da8c7" />

### 🐾 Ejercicio 9: Veterinaria
> **Contexto:** Modelado del sistema de gestión para una clínica veterinaria. Se registran propietarios, teléfonos, familiares de contacto, mascotas, consultas médicas y personal clínico (veterinarios y auxiliares).

```text
Propietario (cédula, nombres, dirección)
Telefonos (telefono, cédula)
Familiar (cédula, nombres, cédula)
Telf_familiar (telefono, cédula)
Mascota (fecha_nacimiento, nombre, id, tipo, cedula)
Consulta (fecha_atencion, diagnostico, id, cedula)
Persona (cédula, nombre, código, fecha_alta, especialidad)
Auxiliar (cédula, nombre, código, base_cotizacion)
```
<img width="796" height="1179" alt="image" src="https://github.com/user-attachments/assets/821a821e-afea-4819-9ae4-e80fca7f02ba" />
