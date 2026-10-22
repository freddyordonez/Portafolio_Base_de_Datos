<div align="center">

# 📐 Diagramas MER: Ejemplos y Prácticas

*Repositorio de las evidencias y diagramas correspondientes a los ejercicios de modelado conceptual.*

</div>

---

## 📌 Parte 1: Ejemplos Guiados

### 📚 Ejemplo 1: Sistema de Biblioteca
> **Contexto:** Una biblioteca registra libros y autores. 
* Un libro puede tener varios autores y un autor varios libros. 
* Los socios toman libros prestados; de cada préstamo interesan la *fecha de retiro* y la *fecha de devolución*.

<div align="center">
  <!-- Reemplaza "URL_DE_LA_IMAGEN" con el enlace o ruta de tu foto -->

  <img width="1600" height="567" alt="image" src="https://github.com/user-attachments/assets/5b1a311f-f908-40e0-9ba7-05c303747422" />

  <br><em>Diagrama MER: Sistema de Biblioteca</em>
</div>

<br><hr width="30%"><br>

### 🍽️ Ejemplo 2: Pedidos de Restaurante
> **Contexto:** Los clientes realizan pedidos que contienen varios platos con distinta cantidad. 
* Los platos se agrupan en categorías. 
* Cada pedido lo atiende un único mesero. 
* El precio del plato debe registrarse tal como estaba al momento del pedido, aunque luego cambie.

<div align="center">

  <img width="1600" height="1194" alt="image" src="https://github.com/user-attachments/assets/4f03ee0b-9ba1-49b4-a541-c7b1369ec125" />

 
  <br><em>Diagrama MER: Pedidos de Restaurante</em>
</div>

<br><hr width="30%"><br>

### 🏥 Ejemplo 3: Clínica Médica
> **Contexto:** Los pacientes solicitan atención médica en la clínica. 
* Cada turno lo atiende un médico a un paciente especificando fecha, hora y consultorio. 
* De algunas de estas atenciones se genera una receta que incluye medicamentos con dosis y duración. 
* Cada médico pertenece a una especialidad.

<div align="center">

  <img width="1600" height="1194" alt="image" src="https://github.com/user-attachments/assets/72d2e91d-d0ff-4d23-868b-fdcc2155e9c1" />

  
  <br><em>Diagrama MER: Clínica Médica</em>
</div>

<br><hr width="30%"><br>

### ✈️ Ejemplo 4: Sistema de Aerolínea
> **Contexto:** Una aerolínea opera vuelos (cada uno con número, fecha, origen y destino).
* Cada vuelo lo realiza un avión. 
* Los pasajeros realizan reservas para un vuelo específico, indicando asiento y tarifa pagada en el momento de la reserva.

<div align="center">

  <img width="1600" height="1194" alt="image" src="https://github.com/user-attachments/assets/d47d4ddd-0ef1-4b48-9c24-de289ff2dadd" />

  
  <br><em>Diagrama MER: Sistema de Aerolínea</em>
</div>

<br><br>

---

## 🚀 Parte 2: Ejercicios Propuestos

### 🎵 Ejercicio 5: Empresa Discográfica
> **Contexto:** Una empresa discográfica necesita modelar los datos sobre sus diferentes recursos:
* 🧑‍💼 **Manager:** Se almacena su identificador y nombre. Un manager representa a una serie de artistas.
* 🎤 **Artista:** Es representado por un manager. Se almacena su nombre completo (atributo único) y su NIF.
* 🎉 **Evento de promoción:** Los artistas participan en eventos para dar a conocer sus trabajos. Pueden participar varios artistas. Se almacena un identificador único, la fecha de celebración y el número de asistentes.

<div align="center">

<img width="1600" height="1194" alt="image" src="https://github.com/user-attachments/assets/bc27c05a-ad24-4b50-93ef-9e5ca4a7f825" />
  
</div>

<br><hr width="30%"><br>

### 💻 Ejercicio 6: Tienda Informática
> **Contexto:** Aplicación para la gestión de ventas e inventario de una tienda informática.
* 📦 **Productos:** Se venden a los clientes. Se guarda el código, descripción, precio y número de existencias. 
* 👥 **Clientes:** Se guarda el código, nombre, apellidos, dirección y teléfono. Un cliente puede comprar varios productos y un producto ser comprado por varios clientes. 
* 🛒 **Compras:** Cada vez que se compre un artículo quedará registrada la compra junto con la fecha. 
* 🏢 **Proveedores:** Suministran los productos. Un producto puede ser suministrado por varios proveedores. Se guarda el código, nombres, apellidos, dirección, provincia y teléfono.

<div align="center">

<img width="1600" height="1044" alt="image" src="https://github.com/user-attachments/assets/48d3a006-3051-4cf8-92d2-6320655d8ec4" />

</div>

<br><hr width="30%"><br>

### 💿 Ejercicio 7: Discos Musicales
> **Contexto:** Gestión de ventas de discos de diferentes géneros musicales y cantantes.
* 🎼 **Géneros y Cantantes:** Cada género tiene un identificador. De un cantante se registra el nombre y su país.
* 💽 **Discos:** Todo disco pertenece a un cantante (quien puede tener muchos discos). Cada disco tiene título, género musical, precio y cantante. 
* 🎧 **Canciones:** Un disco tiene un conjunto de canciones (identificador y título). Una canción puede estar en varios discos. Interesa conocer la posición de una canción en un determinado disco.

<div align="center">
  
<img width="1024" height="482" alt="image" src="https://github.com/user-attachments/assets/8eb288d0-a7d3-42af-b7c8-2d7c2442daea" />

</div>

<br><hr width="30%"><br>

### 🚚 Ejercicio 8: Camiones
> **Contexto:** Gestión de una empresa de transporte que reparte paquetes por toda España.
* 🚛 **Camioneros:** Encargados de llevar los paquetes. Se guarda la cédula, nombre, teléfono, dirección, salario y población en que vive. 
* 📦 **Paquetes:** Interesa el código, descripción, destinatario y su dirección. Un camionero distribuye muchos paquetes, y un paquete sólo es distribuido por un camionero. 
* 🗺️ **Provincias:** Se guarda el código de provincia y nombre. Un paquete sólo llega a una provincia, pero a una provincia pueden llegar varios paquetes.
* 🚚 **Camiones:** Interesa la matrícula, modelo, tipo y potencia. Un camionero puede conducir diferentes camiones en fechas diferentes, y un camión ser conducido por varios camioneros.

<div align="center">

<img width="1024" height="668" alt="image" src="https://github.com/user-attachments/assets/e0306dfd-dff4-4fb5-8fcb-bd8e58e34007" />

</div>

<br><hr width="30%"><br>

### 🐾 Ejercicio 9: Veterinaria
> **Contexto:** Modelado del sistema de gestión para una clínica veterinaria.
1. 👤 **Propietario:** Interesa conocer su cédula, apellidos, nombres, dirección y teléfonos.
2. 🐕 **Mascota:** Interesa su identificador, nombre, fecha de nacimiento y tipo. Un propietario puede llevar una o varias mascotas (una mascota pertenece a un solo propietario).
3. 🩺 **Personal Clínico:** Interesa código, cédula y nombre. Se distingue entre veterinarios (se guarda fecha de alta y especialidad) y auxiliares (interesa su base de cotización).
4. 📋 **Consultas Médicas:** Las mascotas pasan consulta con los veterinarios. Un veterinario atiende a varias mascotas, y una mascota puede ser atendida varias veces en fechas diferentes por distintos veterinarios. Al pasar consulta se realiza un diagnóstico.
5. 🚨 **Familiar de Contacto:** Para casos de emergencia. Interesa cédula, nombre y teléfono. Si el propietario se da de alta en la clínica, el familiar ya no interesa. Es contacto de un solo propietario.

<div align="center">
  
<img width="1427" height="782" alt="image" src="https://github.com/user-attachments/assets/830f350a-ce99-4c67-8ae2-27f4f0a8fd12" />

</div>

<br><br>

---

<!-- Botón para regresar a la unidad principal -->
<div align="center">
  <a href="UNIDAD1.md">
    <img src="https://img.shields.io/badge/⬅_Volver_a_la_Unidad_1-555555?style=for-the-badge" alt="Volver a Unidad 1" />
  </a>
</div>
