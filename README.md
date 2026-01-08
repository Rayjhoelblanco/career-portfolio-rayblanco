# QA Automation Framework – Cypress (E2E) | SauceDemo
## Automation Frameworks
Cypress E2E Framework ([link al repo](https://github.com/Rayjhoelblanco/cypress-e2e-framework))

Framework de automatización E2E desarrollado con **Cypress**, aplicando buenas prácticas reales de QA Automation utilizadas en proyectos **SaaS / e-commerce**.

El objetivo del proyecto es demostrar **criterio técnico**, **estructura escalable** y **decisiones conscientes** según el contexto del sistema bajo prueba.

---

## Stack Tecnológico
- Cypress (E2E Testing)
- JavaScript
- Page Object Model (POM)
- Custom Commands (Cypress.Commands)
- Fixtures para datos de prueba

---

## Estructura del Proyecto

```text
cypress/
 ├── e2e/
 │   ├── login.cy.js        # Tests de login por UI
 │   ├── cart.cy.js         # Tests de carrito
 │   └── checkout.cy.js     # Flujo E2E completo
 ├── pages/
 │   ├── LoginPage.js
 │   ├── ProductsPage.js
 │   ├── CartPage.js
 │   └── CheckoutPage.js
 ├── fixtures/
 │   ├── users.json
 │   └── checkout.json
 └── support/
     ├── commands.js        # Custom commands
     └── e2e.js             # Import global


---

## Estrategia de Login

### Login por UI (`cy.login`)
Utilizado para:
- Tests funcionales de login
- Validaciones de errores
- Sistemas sin API de autenticación

Implementado mediante **Page Object Model**.

```js
cy.login("standard");

Login por API (cy.loginByApi) – Patrón Profesional

Incluido para demostrar el patrón utilizado en SaaS reales, donde:

El backend expone un endpoint de autenticación

Se obtiene token o cookie de sesión

Se evita el login por UI en regresión

Nota: SauceDemo no posee una API real de autenticación, por lo que este comando se incluye a nivel demostrativo del patrón, pero no se utiliza en ejecución real del flujo para evitar inestabilidad.

Este enfoque demuestra conocimiento de optimización de suites de regresión en entornos productivos reales.

 Tipos de Tests Implementados
 Smoke Tests

Login exitoso

Agregar producto al carrito

Eliminar producto del carrito

Validan que el core del negocio esté operativo antes de liberar una versión.


End-to-End (E2E)

Login

Agregar producto

Checkout completo

Confirmación de compra

Validan el flujo crítico de compra de punta a punta simulando el comportamiento real del usuario.

Ejecución del Proyecto
Instalación
npm install

Abrir Cypress
npx cypress open

Buenas Prácticas Aplicadas

Separación de responsabilidades (POM)

Datos desacoplados mediante fixtures

Custom commands para reutilización

No uso de cy.wait() hardcodeado

Assertions funcionales (no visuales)

Decisiones técnicas basadas en contexto real

Objetivo del Framework

Este proyecto no busca cubrir todos los casos posibles, sino demostrar:

Capacidad de análisis

Criterio técnico

Diseño mantenible

Enfoque profesional orientado a negocio

👤 Ray Blanco
QA Analyst / QA Automation
Enfoque en pruebas funcionales, automatización y calidad en entornos SaaS.
