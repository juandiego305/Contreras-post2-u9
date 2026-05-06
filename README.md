## 📊 Cobertura de Código (JaCoCo)
El pipeline automatizado genera un reporte de cobertura detallado en cada commit. La suite de pruebas garantiza una cobertura superior al **70%** en la capa de negocio.


## 🧑‍💻 Autor
* **Nombre**: Juan Diego Emmanuel Contreras Garcia
* **Institución**: Universidad Francisco de Paula Santander (UFPS)
* **Programa**: Ingeniería de Sistemas - 2026A

# Productos Service - Integración y CI/CD (UFPS)


## Descripción
Microservicio de gestión de productos implementando una suite de pruebas de integración y un pipeline de Integración Continua (CI). El sistema automatiza la verificación del código mediante GitHub Actions y genera reportes de cobertura con JaCoCo.

## 🧪 Estrategia de Pruebas Implementada
El ecosistema de pruebas utiliza la carga parcial del contexto de Spring Boot para optimizar el balance entre velocidad y fidelidad:
* **Capa de Persistencia (`@DataJpaTest`)**: Verifica los repositorios inicializando únicamente los componentes JPA y una base de datos H2 en memoria. Cada prueba se ejecuta dentro de una transacción que se revierte automáticamente al finalizar.
* **Capa Web (`@WebMvcTest`)**: Verifica los controladores REST, serialización JSON y códigos de estado HTTP (200, 201, 404), aislando la capa de negocio mediante el uso de `@MockBean`.

## 🚀 Ejecutar las Pruebas

Para ejecutar la suite de pruebas automatizadas y generar el reporte de cobertura, utiliza los siguientes comandos:

```bash
# Solo pruebas unitarias y de integración
mvn test

# Pruebas + Generación del reporte JaCoCo
mvn verify
