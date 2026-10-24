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


<img width="1524" height="1131" alt="image" src="https://github.com/user-attachments/assets/0b222f4e-5b88-43f0-bb22-d37c36af17a6" />


  <br><em>Diagrama MER: Sistema de Biblioteca</em>
</div>

<br><hr width="30%"><br>

### 🍽️ Ejemplo 2: Pedidos de Restaurante
> **Contexto:** Los clientes realizan pedidos que contienen varios platos con distinta cantidad. 
* Los platos se agrupan en categorías. 
* Cada pedido lo atiende un único mesero. 
* El precio del plato debe registrarse tal como estaba al momento del pedido, aunque luego cambie.

<div align="center">

  <img width="1703" height="1089" alt="image" src="https://github.com/user-attachments/assets/8bc8e4ba-4fa8-48a4-b3dc-4b4a767b4a66" />

 
  <br><em>Diagrama MER: Pedidos de Restaurante</em>
</div>

<br><hr width="30%"><br>

### 🏥 Ejemplo 3: Clínica Médica
> **Contexto:** Los pacientes solicitan atención médica en la clínica. 
* Cada turno lo atiende un médico a un paciente especificando fecha, hora y consultorio. 
* De algunas de estas atenciones se genera una receta que incluye medicamentos con dosis y duración. 
* Cada médico pertenece a una especialidad.

<div align="center">

  <img width="1448" height="801" alt="image" src="https://github.com/user-attachments/assets/67230c07-5653-41cb-a74a-948575f96383" />


  
  <br><em>Diagrama MER: Clínica Médica</em>
</div>

<br><hr width="30%"><br>

### ✈️ Ejemplo 4: Sistema de Aerolínea
> **Contexto:** Una aerolínea opera vuelos (cada uno con número, fecha, origen y destino).
* Cada vuelo lo realiza un avión. 
* Los pasajeros realizan reservas para un vuelo específico, indicando asiento y tarifa pagada en el momento de la reserva.

<div align="center">

<img width="1507" height="1080" alt="image" src="https://github.com/user-attachments/assets/2430ba14-56f2-4d62-9f4e-3d73a0e251b7" />

  
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

<img width="1742" height="427" alt="image" src="https://github.com/user-attachments/assets/25a5158a-f961-4e0b-938b-ecf3fca84798" />

</div>

<br><hr width="30%"><br>

### 💻 Ejercicio 6: Tienda Informática
> **Contexto:** Aplicación para la gestión de ventas e inventario de una tienda informática.
* 📦 **Productos:** Se venden a los clientes. Se guarda el código, descripción, precio y número de existencias. 
* 👥 **Clientes:** Se guarda el código, nombre, apellidos, dirección y teléfono. Un cliente puede comprar varios productos y un producto ser comprado por varios clientes. 
* 🛒 **Compras:** Cada vez que se compre un artículo quedará registrada la compra junto con la fecha. 
* 🏢 **Proveedores:** Suministran los productos. Un producto puede ser suministrado por varios proveedores. Se guarda el código, nombres, apellidos, dirección, provincia y teléfono.

<div align="center">

<img width="1656" height="975" alt="image" src="https://github.com/user-attachments/assets/5920512c-994e-4e4e-bcef-de5de28b8d05" />


</div>

<br><hr width="30%"><br>

### 💿 Ejercicio 7: Discos Musicales
> **Contexto:** Gestión de ventas de discos de diferentes géneros musicales y cantantes.
* 🎼 **Géneros y Cantantes:** Cada género tiene un identificador. De un cantante se registra el nombre y su país.
* 💽 **Discos:** Todo disco pertenece a un cantante (quien puede tener muchos discos). Cada disco tiene título, género musical, precio y cantante. 
* 🎧 **Canciones:** Un disco tiene un conjunto de canciones (identificador y título). Una canción puede estar en varios discos. Interesa conocer la posición de una canción en un determinado disco.

<div align="center">
  
<img width="1681" height="799" alt="image" src="https://github.com/user-attachments/assets/ffc932cd-3e5f-453f-9757-85b90b77fe11" />


</div>

<br><hr width="30%"><br>

### 🚚 Ejercicio 8: Camiones
> **Contexto:** Gestión de una empresa de transporte que reparte paquetes por toda España.
* 🚛 **Camioneros:** Encargados de llevar los paquetes. Se guarda la cédula, nombre, teléfono, dirección, salario y población en que vive. 
* 📦 **Paquetes:** Interesa el código, descripción, destinatario y su dirección. Un camionero distribuye muchos paquetes, y un paquete sólo es distribuido por un camionero. 
* 🗺️ **Provincias:** Se guarda el código de provincia y nombre. Un paquete sólo llega a una provincia, pero a una provincia pueden llegar varios paquetes.
* 🚚 **Camiones:** Interesa la matrícula, modelo, tipo y potencia. Un camionero puede conducir diferentes camiones en fechas diferentes, y un camión ser conducido por varios camioneros.

<div align="center">

<img width="1554" height="961" alt="image" src="https://github.com/user-attachments/assets/78ccc584-9860-476e-a896-5848bf794953" />


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
  

<img width="1694" height="1039" alt="image" src="https://github.com/user-attachments/assets/8c74287b-7b1b-4bf5-ad77-9633e9f3220e" />


</div>

<br><br>

---

<!-- Botón para regresar a la unidad principal -->
<div align="center">
  <a href="UNIDAD1.md">
    <img src="https://img.shields.io/badge/⬅_Volver_a_la_Unidad_1-555555?style=for-the-badge" alt="Volver a Unidad 1" />
  </a>
</div>
