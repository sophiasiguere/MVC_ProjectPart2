<h1> Documentación </h1> 
<br>
DIAGRAMA DE ENTIDAD RELACIÓN
 <img width="1000" alt="diagrama" src="https://user-images.githubusercontent.com/59983672/228640861-5736a79b-d7b6-487e-b746-60b7d80425fd.PNG">
<br>
<br>
Query utilizado: 
<br>

```
CREATE TABLE Rol (
  id INT AUTO_INCREMENT PRIMARY KEY,
  nombre VARCHAR(50) NOT NULL
);

CREATE TABLE Usuarios (
  id INT AUTO_INCREMENT PRIMARY KEY,
  nombre VARCHAR(50) NOT NULL,
  usuario VARCHAR(50) NOT NULL,
  correo VARCHAR(50) NOT NULL,
  telefono VARCHAR(50) NOT NULL,
  contrasena VARCHAR(50) NOT NULL,
  id_rol INT NOT NULL,
  FOREIGN KEY (id_rol) REFERENCES Rol(id)
);

INSERT INTO Rol (nombre) VALUES ('administrador'), ('vendedor');

CREATE TABLE Cotizacion (
  id INT AUTO_INCREMENT NOT NULL PRIMARY KEY,
  correoCliente VARCHAR(50) NOT NULL,
  telefonoCliente VARCHAR(50) NOT NULL,
  fechaCotizacion DATE NOT NULL
);

CREATE TABLE Pedido (
  id INT AUTO_INCREMENT PRIMARY KEY,
  NoPedido INT NOT NULL,
  tamañoAltura INT NOT NULL,
  tamañoHorizonte INT NOT NULL,
  tamañoExtension INT NOT NULL,
  colorPantone VARCHAR(50) NOT NULL,
  Material VARCHAR(50) NOT NULL,
  calibre VARCHAR(50) NOT NULL,
  logo VARCHAR(50) NOT NULL,
  FOREIGN KEY (NoPedido) REFERENCES Cotizacion(id)
);

```
