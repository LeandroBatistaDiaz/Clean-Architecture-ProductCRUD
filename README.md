# Clean Architecture - Product CRUD 📦🏗️

Este repositorio contiene una API RESTful desarrollada en **.NET (C#)** enfocada en la gestión de productos (operaciones CRUD). El proyecto sirve como una plantilla o ejemplo práctico de la implementación de **Clean Architecture** (Arquitectura Limpia), separando claramente las responsabilidades y manteniendo el dominio de la aplicación independiente de los frameworks y la interfaz de usuario.

## 🏗️ Estructura de la Solución (`LatinoNet`)

La solución está dividida en múltiples proyectos para respetar la regla de dependencia, donde las capas externas dependen de las internas, pero nunca al revés:

### 1. Capa de Dominio (Core)
* **`LatinoNet.Entities`**: Contiene las entidades principales del negocio (ej. `Product`) y las reglas empresariales críticas. No tiene dependencias externas.

### 2. Capa de Aplicación (Casos de Uso)
* **`LatinoNet.UseCasesPorts`**: Define los contratos (Interfaces) de entrada y salida para los casos de uso (Patrón Ports and Adapters).
* **`LatinoNet.UseCases`**: Contiene la lógica de negocio y la implementación de las operaciones del CRUD de productos.
* **`LatinoNet.DTOs`**: Objetos de Transferencia de Datos utilizados para mover información entre las capas de manera segura.

### 3. Capa de Infraestructura
* **`LatinoNet.RepositoryEFCore`**: Implementación del acceso a datos utilizando **Entity Framework Core**. Maneja el contexto de la base de datos y la persistencia de los productos.
* **`LatinoNet.IoC` (Inversion of Control)**: Proyecto encargado de centralizar la inyección de dependencias (`Dependency Injection`), conectando las interfaces con sus implementaciones concretas.

### 4. Capa de Presentación
* **`LatinoNet.Api`**: El proyecto principal (Host). Configura el entorno, los middlewares y expone la API.
* **`LatinoNet.Controllers`**: Controladores que reciben las peticiones HTTP y las dirigen a los puertos de entrada (`Input Ports`) de los casos de uso.
* **`LatinoNet.Presenters`**: Formatean la salida de los casos de uso mediante los puertos de salida (`Output Ports`) para entregar las respuestas HTTP al cliente.

## 🚀 Tecnologías Utilizadas

* **.NET** (C#)
* **Entity Framework Core**
* **Patrones de Diseño:** Arquitectura Limpia, Puertos y Adaptadores (Hexagonal), Inyección de Dependencias, Patrón Repositorio.

## 💻 Instalación y Ejecución

1. **Clonar el repositorio:**
   ```bash
   git clone [https://github.com/LeandroBatistaDiaz/Clean-Architecture-ProductCRUD.git](https://github.com/LeandroBatistaDiaz/Clean-Architecture-ProductCRUD.git)
   cd Clean-Architecture-ProductCRUD
