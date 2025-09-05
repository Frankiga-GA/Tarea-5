# Sistema de Gestión de Recursos Educativos

**Este proyecto es un sistema web para gestionar recursos educativos**, como libros, artículos o cualquier otro material de aprendizaje. Permite a los usuarios registrar nuevos recursos, visualizarlos y editar los existentes. El sistema está construido con **CodeIgniter 4** y usa **MySQL** para la base de datos.

---

## **Características del Proyecto**

### **1. Gestión de Recursos Educativos**
- Registro, listado, edición y búsqueda de recursos educativos de manera eficiente.

### **2. Base de Datos Estructurada**
- Utiliza una base de datos relacional con tablas para **categorías**, **subcategorías**, **editoriales** y **recursos**, asegurando una correcta organización de la información.

### **3. Búsqueda Eficiente**
- Los usuarios pueden buscar recursos utilizando filtros como **título**, **editorial**, **subcategoría** o **estado**.

### **4. Formulario Interactivo**
- Formulario de registro y edición fácil de usar, con validaciones integradas para garantizar la consistencia de los datos.

---

## **Tecnologías Usadas**

- **Backend**: PHP con **CodeIgniter 4**.
- **Base de Datos**: **MySQL**.
- **Frontend**: HTML, CSS (utilizando **Bootstrap** para el diseño responsivo).
- **Servidor Web**: **Apache** (usando **Laragon** o cualquier servidor compatible).

---

## **Configuración de la Base de Datos**

### **1. Crear la Base de Datos**

```sql
CREATE DATABASE IF NOT EXISTS cursos_db;
USE cursos_db;
2. Crear Tablas
Tabla de Categorías
sql
Copiar código
CREATE TABLE categorias (
    idcategoria INT AUTO_INCREMENT PRIMARY KEY,
    categoria VARCHAR(255) NOT NULL
);

INSERT INTO categorias (categoria) VALUES 
('Matemáticas'), 
('Comunicación'), 
('Computación');
Tabla de Subcategorías
sql
Copiar código
CREATE TABLE subcategorias (
    idsubcategoria INT AUTO_INCREMENT PRIMARY KEY,
    subcategoria VARCHAR(255) NOT NULL,
    idcategoria INT,
    FOREIGN KEY (idcategoria) REFERENCES categorias(idcategoria)
);

INSERT INTO subcategorias (subcategoria, idcategoria) VALUES
('Razonamiento Lógico Matemático', 1),
('Álgebra', 1),
('Trigonometría', 1),
('Razonamiento verbal', 2),
('Composición', 2),
('Redacción', 2),
('Base de datos', 3),
('Sistemas operativos', 3),
('Lenguajes de programación', 3);
Tabla de Editoriales
sql
Copiar código
CREATE TABLE editoriales (
    ideditorial INT AUTO_INCREMENT PRIMARY KEY,
    editorial VARCHAR(255) NOT NULL,
    nacionalidad VARCHAR(255) NOT NULL
);

INSERT INTO editoriales (editorial, nacionalidad) VALUES
('Editorial XYZ', 'México'),
('Editorial ABC', 'España'),
('Editorial 123', 'Estados Unidos');
Tabla de Recursos
sql
Copiar código
CREATE TABLE recursos (
    idrecurso INT AUTO_INCREMENT PRIMARY KEY,
    idsubcategoria INT,
    ideditorial INT,
    tipo VARCHAR(50),
    titulo VARCHAR(255),
    apublicacion INT,
    isbn VARCHAR(50),
    numpaginas INT,
    rutaportada VARCHAR(255),
    rutarecurso VARCHAR(255),
    estado VARCHAR(50),
    creado TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    modificado TIMESTAMP NULL DEFAULT NULL,
    FOREIGN KEY (idsubcategoria) REFERENCES subcategorias(idsubcategoria),
    FOREIGN KEY (ideditorial) REFERENCES editoriales(ideditorial)
);
Uso del Proyecto
1. Registrar Recursos
Formulario de Registro:

Visita http://localhost:8080/recursos/create para registrar un nuevo recurso educativo, eligiendo la subcategoría, editorial, tipo y estado.

2. Ver Recursos Registrados
Lista de Recursos:

Visita http://localhost:8080/recursos para ver todos los recursos registrados. Desde aquí también puedes editar un recurso, haciendo clic en el botón "Editar" junto a cada recurso.

3. Buscar Recursos
Búsqueda:

En la página de lista de recursos, utiliza el formulario de búsqueda para encontrar recursos por título, editorial, subcategoría o estado.

Estructura de la Base de Datos
La base de datos cursos_db contiene las siguientes tablas:

categorias: Almacena las categorías principales de los recursos (como Matemáticas, Comunicación, Computación).

subcategorias: Contiene las subcategorías relacionadas con las categorías (por ejemplo, Trigonometría, Álgebra).

editoriales: Guarda información sobre las editoriales y sus respectivas nacionalidades.

recursos: La tabla principal que guarda los recursos (libros, artículos, etc.), incluyendo información como título, tipo, subcategoría, editorial, estado y más.

Contribuciones
Si deseas contribuir al proyecto, ¡serás bienvenido! Si encuentras algún error o tienes una idea para mejorar el proyecto, puedes seguir estos pasos:

Haz un fork del repositorio.

Crea una nueva rama para tu función o corrección de error.

Realiza tus cambios y haz un commit con un mensaje claro.

Push y abre un pull request con una descripción detallada de los cambios.

