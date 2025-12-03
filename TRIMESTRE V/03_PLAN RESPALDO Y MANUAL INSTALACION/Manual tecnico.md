
# Manual Técnico — MotionParts

**Versión:** 1.0 • **Autores:** Santiago Riola, Juan Peraza, Camilo Pinzón

## 1. Portada y datos generales

- **Proyecto:** MotionParts
- **Versión:** 1.0
- **Autores:** Santiago Riola, Juan Peraza, Camilo Pinzón
- **Programa académico:** Análisis y Desarrollo de software
- **Institución:** SENA SEET

Descripción: este manual documenta la arquitectura, el diseño y la implementación del sistema Ecommerce para Car Eléctricos La 64. Contiene instrucciones de instalación, configuración, ejecución y referencia a la integración con MaiaERP, así como detalles de backend, frontend y la base de datos.

---

## Tabla de contenidos

- [Introducción](#2-introducción)
- [Descripción general del sistema](#3-descripción-general-del-sistema)
- [Arquitectura del software](#4-arquitectura-del-software)
- [Diseño del sistema (UML)](#5-diseño-del-sistema-uml)
- [Modelo de datos](#6-modelo-de-datos)
- [Detalles técnicos de implementación](#7-detalles-técnicos-de-implementación)
- [Requerimientos del sistema](#8-requerimientos-del-sistema)
- [Requerimientos de software](#9-requerimientos-de-software)
- [Instalación del sistema (mejorada)](#10-instalación-del-sistema-mejorada)

---

## 2. Introducción

La finalidad de este manual técnico es documentar la estructura, funcionamiento e implementación del sistema de Ecommerce desarrollado para Car Eléctricos La 64, una empresa mayorista de autopartes. El documento abarca la arquitectura del software, los módulos del sistema, el diseño de datos, la integración con MaiaERP para facturación electrónica, así como los procesos de inventario, ventas y envíos implementados. Su alcance incluye la descripción técnica del backend, frontend y base de datos, además de los lineamientos para instalación, configuración y mantenimiento del sistema. Está dirigido principalmente a desarrolladores, administradores del sistema y personal técnico encargado de dar soporte, garantizar la operatividad y realizar futuras mejoras o adaptaciones a la plataforma.

---

## 3. Descripción General del Sistema

Este proyecto tiene como objetivo desarrollar un sistema de Ecommerce para Car Eléctricos La 64, una empresa mayorista de autopartes. La plataforma permitirá a los clientes consultar fácilmente el catálogo de productos, realizar compras en línea y automatizar la facturación, integrándose con el sistema MaiaERP para asegurar el cumplimiento fiscal. Además, optimizará la gestión de inventarios, el proceso de ventas y el seguimiento de envíos, mejorando la eficiencia operativa y la experiencia del cliente, tanto a nivel nacional como internacional.

### Objetivo General

Desarrollar una plataforma de comercio electrónico para Car Eléctricos La 64 que permita gestionar el catálogo de productos, realizar compras en línea, generar facturación electrónica sincronizada con MaiaERP y proporcionar información sobre el estado de pedidos y envíos, asegurando la integración entre la tienda física y digital.

### Objetivos Específicos

1. Gestionar usuarios de la empresa Car Eléctricos La 64.
2. Gestionar los productos de la empresa Car Eléctricos La 64.
3. Gestionar las ventas, pagos y envíos de productos de la empresa Car Eléctricos La 64.
4. Gestionar la facturación electrónica de las ventas que se hagan por medio del comercio electrónico de la empresa Car Eléctricos La 64, con apoyo del software MaiaERP.
5. Gestionar reportes gráficos e impresos de las ventas, pagos y envíos de productos de la empresa Car Eléctricos la 64.

### Usuarios principales

- Administrador
- Empleado
- Usuario 
- Invitado

El sistema de Ecommerce desarrollado para Car Eléctricos La 64 permite a los clientes consultar en línea el catálogo completo de autopartes, visualizar precios, disponibilidad y detalles técnicos, y realizar compras de forma sencilla desde cualquier dispositivo. El software gestiona todo el proceso de venta, desde la selección de productos hasta el pago y la generación automática de la factura, la cual se integra con el sistema MaiaERP para garantizar el cumplimiento fiscal y la actualización en tiempo real del inventario. Paralelamente, la plataforma administra el estado de las órdenes, permitiendo el seguimiento de envíos y el control de pedidos pendientes, entregados o no exitosos. En conjunto, el sistema centraliza y automatiza la operación comercial de la empresa, mejorando la eficiencia interna y proporcionando una experiencia de compra fluida tanto para clientes nacionales como internacionales.

---

## 4. Arquitectura del Software

### Arquitectura del Proyecto MotionParts

#### Lenguajes

- **Java:** Utilizado en el backend para la lógica de negocio y servicios.
- **TypeScript:** Utilizado en el frontend con Angular para el desarrollo de la interfaz de usuario.
- **JavaScript:** Scripts auxiliares y de inicialización en la carpeta `db`.
- **Shell/Bash y Batch:** Scripts para automatización y manejo de base de datos (`.sh`, `.bat`).

#### Frameworks

- **Spring Boot:** Framework principal del backend, facilita la creación de aplicaciones Java empresariales y APIs REST.
- **Angular 19:** Framework principal del frontend para construir SPA (Single Page Applications) modernas y responsivas.

#### Librerías

- **Backend:**
  - Spring Security: Seguridad y autenticación (incluyendo JWT).
  - Spring Data MongoDB: Acceso a base de datos MongoDB.
  - Spring WebSocket: Comunicación en tiempo real.
  - Hibernate/JPA: ORM para persistencia de datos.
  - Jacoco: Cobertura de pruebas.
  - SonarQube: Análisis de calidad de código.

- **Frontend:**
  - TailwindCSS: Framework de estilos CSS utilitario

#### Base de datos

- **MongoDB:** Base de datos principal.

---

## 5. Diseño del Sistema (UML)

### Diagrama de Casos de Uso

#### Diagrama de Casos de Uso - Admin, Empleado y Cliente

![Casos de Uso - Admin, Empleado y Cliente 1](./imagenes/diagram1.jpg)
![Casos de Uso - Admin, Empleado y Cliente 2](./imagenes/diagram2.jpg)
![Casos de Uso - Admin, Empleado y Cliente 3](./imagenes/diagram3.jpg)
![Casos de Uso - Admin, Empleado y Cliente 4](./imagenes/diagram4.jpg)

### Diagrama de Clases

![Diagrama de Clases](./imagenes/diagrama_clases.png)

### Diagrama de Despliegue

![Diagrama de Despliegue](./imagenes/diagrama_despliegue.png)

---

## 6. Modelo de Datos

![Modelo de Datos](./imagenes/modelo_datos.png)

---

## 7. Detalles Técnicos de Implementación

### Estructura del proyecto

#### Frontend

```
Frontend/
├── .angular/           # Archivos de caché y build internos de Angular CLI
├── architecture/       # Diagramas, documentación y artefactos de arquitectura del frontend
├── coverage/           # Reportes de cobertura de pruebas unitarias
├── public/             # Archivos públicos y estáticos (usados por Vite o Angular)
├── src/                # Código fuente principal de la aplicación
│   ├── app/            # Componentes, módulos, servicios y lógica de la app Angular
│   ├── assets/         # Recursos estáticos como imágenes, íconos, etc.
│   ├── environments/   # Configuraciones de entorno (dev, prod)
│   ├── global-polyfill.ts # Polyfills globales para compatibilidad
│   ├── index.html      # HTML principal de la aplicación Angular
│   ├── main.ts         # Punto de entrada de la app Angular
│   ├── styles.css      # Estilos globales
│   └── test.ts         # Configuración de pruebas unitarias
├── .dockerignore       # Exclusiones para el contexto de Docker
├── angular.json        # Configuración del proyecto Angular
├── default.conf        # Configuración de servidor (Nginx, etc.)
├── Dockerfile          # Dockerfile para construir la imagen del frontend
├── karma.conf.js       # Configuración de Karma para pruebas unitarias
├── package.json        # Dependencias y scripts npm
├── README.md           # Documentación principal del frontend
├── sonar-project.properties # Configuración de SonarQube para análisis de calidad
├── tsconfig*.json      # Configuración de TypeScript
```

#### Backend

```
Backend/
├── .dockerignore, .gitignore      # Exclusiones para Docker y Git
├── build.gradle.kts, settings.gradle.kts # Configuración de Gradle
├── Dockerfile                     # Dockerfile para construir la imagen del backend
├── README.md                      # Documentación principal del backend
├── sonar-project.properties       # Configuración de SonarQube
├── src/
│   └── main/
│       ├── java/
│       │   └── com/
│       │       └── motionparts/
│       │           └── ecommerce/
│       │               ├── MotionPartsApplication.java   # Clase principal de arranque Spring Boot
│       │               ├── auth/                         # Controladores y lógica de autenticación (ej: Google OAuth)
│       │               ├── config/                       # Configuración de seguridad, JWT, CORS, MongoDB, WebSocket, etc.
│       │               ├── controllers/                  # Controladores REST para cada recurso (usuarios, productos, pedidos, etc.)
│       │               ├── dto/                          # Objetos de transferencia de datos (DTOs)
│       │               ├── maia/                         # Integraciones o módulos especiales (ej: MAIA)
│       │               ├── mappers/                      # Mapeadores entre entidades y DTOs
│       │               ├── models/                       # Modelos de dominio (entidades MongoDB, documentos)
│       │               ├── payment/                      # Lógica y controladores de pagos (ej: Wompi)
│       │               ├── repositories/                 # Interfaces de acceso a datos (MongoRepository)
│       │               ├── security/                     # Lógica de seguridad y utilidades
│       │               ├── seed/                         # Scripts o servicios para poblar datos iniciales
│       │               ├── services/                     # Servicios de negocio (lógica principal)
│       │               └── util/                         # Utilidades y helpers generales
│       └── resources/
│           ├── application.properties                   # Configuración principal de Spring Boot
│           ├── application-dev.properties               # Configuración para entorno de desarrollo
│           ├── application-prod.properties              # Configuración para entorno de producción
│           ├── application-test.properties              # Configuración para pruebas
│           ├── firebase-service-account.json            # Credenciales para integración con Firebase
│           ├── MD/                                     # Documentación técnica y de integración
│           ├── META-INF/                               # Metadatos de configuración de Spring
│           └── templates/
│               └── emails/                             # Plantillas HTML para correos automáticos
├── test/                                               # Pruebas unitarias y de integración
├── uploads/                                            # Archivos subidos (productos, logos, etc.)
├── products/                                           # Archivos de productos (imágenes, datos, etc.)
```

### Integraciones externas

- **Wompi:** Pasarela de pagos.
- **SMTP/servicio de correo:** Para notificaciones.
- **MAIA:** Sincronización de datos externos.

---

## 8. Requerimientos del Sistema

### Requisitos Mínimos

- **CPU:** 2 núcleos (Intel i3, AMD Ryzen 3 o equivalente)
- **RAM:** 4 GB
- **Almacenamiento:** 20 GB libres (para base de datos, imágenes, logs y builds)
- **Sistema Operativo:** Windows 10/11, Ubuntu 20.04+ o equivalente
- **Red:** Conexión a Internet para dependencias y APIs externas

### Requisitos Recomendados

- **CPU:** 4 núcleos (Intel i5/i7, AMD Ryzen 5 o superior)
- **RAM:** 8 GB o más (mejor rendimiento para backend, frontend y MongoDB simultáneos)
- **Almacenamiento:** 50 GB SSD (mejor velocidad para base de datos y archivos estáticos)
- **Sistema Operativo:** Windows 10/11 Pro, Ubuntu 22.04 LTS, macOS 12+
- **Red:** Conexión estable a Internet

---

## 9. Requerimientos de Software

1. **Sistema Operativo**
   - Windows 10/11, Ubuntu 20.04+, macOS 12+
   - (Cualquier sistema moderno compatible con Java, Node.js y MongoDB)

2. **Backend**
   - Java 21 o superior (JDK)
   - Gradle 9.x (o usar los scripts gradlew incluidos)
   - Docker (opcional, para despliegue en contenedores)
   - Correo SMTP (para envío de correos, configurable en application.properties)

3. **Base de Datos**
   - MongoDB 8.x o superior
   - (Instalado localmente o acceso a un servidor remoto)

4. **Frontend**
   - Node.js 22.x o superior
   - npm 22.x o superior (incluido con Node.js)
   - Angular CLI (opcional, para desarrollo: `npm install -g @angular/cli`)
   - Vite (si usas Vite para build: `npm install -g vite`)
  
5. **Otros**
   - Git (para control de versiones)
   - Docker Compose (opcional, para levantar todos los servicios juntos)

---
### 10. Instalación del Sistema (mejorada)

Esta sección amplía los pasos mínimos ya descritos: añade enlaces a la documentación oficial de cada herramienta y detalla comandos de instalación y verificación para Windows (PowerShell) y Linux/macOS (bash). No se eliminó ni modificó el resto del documento.


Documentación oficial (enlaces útiles):

- Java (JDK 21+): https://adoptium.net/  | Documentación Oracle Java: https://docs.oracle.com/en/java/
- Node.js & npm: https://nodejs.org/ (descargas: https://nodejs.org/en/download/)
- Angular CLI: https://angular.io/cli
- Gradle & Gradle Wrapper: https://gradle.org/install/  | Wrapper: https://docs.gradle.org/current/userguide/gradle_wrapper.html
- MongoDB: https://www.mongodb.com/docs/
- Docker (opcional): https://docs.docker.com/get-started/

Recomendación: utiliza las guías oficiales anteriores para seguir pasos más detallados o para descargar instaladores específicos según tu sistema operativo.

A continuación se presentan instrucciones prácticas y verificables para preparar el entorno y ejecutar el proyecto localmente.

1) Preparar el entorno (instalar las herramientas principales)

- Java (JDK 21+)

   - Windows (PowerShell): instalar desde Adoptium/Oracle y configurar `JAVA_HOME`:

      ```powershell
      # Ajusta la ruta según la instalación
      setx JAVA_HOME "C:\Program Files\Eclipse Adoptium\jdk-21"
      $env:JAVA_HOME = 'C:\Program Files\Eclipse Adoptium\jdk-21' # sesión actual
      java -version
      javac -version
      ```

   - Linux (Debian/Ubuntu): instalar la versión disponible más reciente desde los repositorios o el paquete por defecto:

      ```bash
      sudo apt update
      sudo apt install openjdk-21-jdk -y
      java -version
      javac -version
      ``

- Node.js & npm (Node 22+ recomendado)

   - Windows (instalación normal — instalador oficial o winget):

      - Descarga el instalador MSI desde la página oficial: `https://nodejs.org/en/download/` y ejecuta el instalador, o usa `winget` si lo tienes instalado:

      ```powershell
      nvm install 22.x
      nvm use 22.x
      node -v
      npm -v
      ```

      - Si prefieres el instalador manual, abre `https://nodejs.org/en/download/` y descarga "Windows Installer" (x64) y ejecútalo.

   - Linux/macOS (instalación normal vía repositorios oficiales / NodeSource):

      ```bash
      # Script de NodeSource para instalar la versión "current" (última disponible)
      curl -fsSL https://deb.nodesource.com/setup_current.x | sudo -E bash -
      sudo apt-get install -y nodejs
      node -v
      npm -v
      ```

- Angular CLI (opcional para `ng serve` durante desarrollo)

   ```bash
   npm install -g @angular/cli
   ng --version
   ```

   Nota: si prefieres no instalar globalmente, puedes usar `npx ng serve` desde la carpeta `Frontend`.

- Gradle

   - debes instalar Gradle globalmente, sigue: https://gradle.org/install/

- MongoDB (local) o Docker

   - Instalación local: sigue la guía oficial https://www.mongodb.com/docs/manual/installation/ para tu SO.
   - Verifica la instalación:

      ```powershell
      mongod --version
      mongo --version
      ```

2) Configuración del proyecto y variables

- Edita `Backend/src/main/resources/application.properties` o `application-dev.properties` para apuntar a tu MongoDB. Ejemplo:

   ```properties
   spring.data.mongodb.uri=mongodb://localhost:27017/motionparts
   ```

- Mantén claves y credenciales fuera del repositorio; usa variables de entorno o un archivo `.env` (no commiteado).

3) Restaurar base de datos de ejemplo (si aplica)

- Windows (PowerShell):

   ```powershell
   .\db\restoreLocal.bat
   ```

- Linux/macOS:

   ```bash
   bash db/restoreLocal.sh
   ```

4) Ejecutar backend y frontend (resumen de comandos)

- Clonar repositorio y posicionarse:

   ```bash
   git clone https://tu-repo.git
   cd MotionParts
   ```

- Backend (usar Gradle r):

   ```powershell
   cd Backend
   .\gradlew bootRun    # Windows (PowerShell)
   ```
   o
   ```bash
   cd Backend
   ./gradlew bootRun         # Linux/macOS
   ```

- Frontend:

   ```bash
   cd ../Frontend
   npm install
   npm run start
   # o usar Angular CLI: npx ng serve --open
   ```

5) Verificación

Ejecuta estos comandos para comprobar que las herramientas están accesibles:

```powershell
java -version
javac -version
node -v
npm -v
mongod --version
docker --version    # si usas Docker
```

6) Notas finales y recomendaciones

- Usa el *Gradle Wrapper* incluido para garantizar la versión de Gradle del proyecto.
- Para Windows, si quieres instalar automáticamente paquetes desde la línea de comandos, puedes usar `winget` o `choco` (requieren instalación previa). Puedo añadir ejemplos si lo deseas.
- Mantén credenciales (SMTP, Wompi, Firebase) en variables de entorno o `.env` fuera del control de versión.