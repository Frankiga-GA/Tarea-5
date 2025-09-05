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
