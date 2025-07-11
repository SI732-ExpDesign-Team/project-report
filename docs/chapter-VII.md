# Capítulo VII: DevOps Practices

## 7.1. Continuous Integration

### 7.1.1. Tools and Practices
**Sistema de Control de Versiones**
- GitHub: Utilizamos GitHub como nuestro sistema centralizado de control de versiones para gestionar todos los repositorios de código de los componentes de nuestro proyecto.
    - URL de la Organización: https://github.com/SI732-ExpDesign-Team
    - Repositorios: Mantenemos repositorios separados para Backend, Frontend, aplicación Móvil y Landing Page para mantener una clara separación de responsabilidades y permitir ciclos de desarrollo independientes.

**Estrategia de Ramificación**

Implementamos un modelo de ramificación basado en características inspirado en GitFlow:

- Rama `main`:
    - Contiene únicamente código listo para producción
    - Protegida contra commits directos
    - Requiere aprobaciones de pull requests antes de fusionar
    - Siempre desplegable en entornos de producción

- Rama `develop`:
    - Rama de integración para desarrollo continuo
    - Utilizada para probar características en conjunto
    - Periódicamente fusionada en main cuando está estable

- Ramas `feature/*`:
    - Creadas para cada nueva funcionalidad o historia de usuario
    - Ramificadas desde develop
    - Utilizadas para desarrollo aislado de funcionalidades
    - Fusionadas de vuelta a develop mediante pull request al completarse
    - Se eliminan luego de un pull request exitoso

**Estándares de Revisión de Código**

- Todos los PRs deben ser revisados por al menos un miembro del equipo
- Flujos de trabajo automáticos que se activan con push a ramas main o develop
- La pipeline de CI incluye la compilación/construcción del código, ejecución de pruebas unitarias y escaneo de seguridad

**Reglas de Protección de Ramas**

Implementamos reglas de protección estrictas para las ramas críticas:

- Protecciones de la rama main:
    - Requerir revisiones de pull request antes de hacer un merge
    - Requerir que las comprobaciones de estado pasen antes de hacer un merge
    - Prohibir los pushes forzados
    - No se permite la eliminación de la rama

- Protecciones de la rama develop:
    - Requerir que las comprobaciones de estado pasen antes de hacer un merge
    - No se permiten commits directos

A continuación se muestra una captura de la estructura de ramas para nuestros repositorios y las reglas de protección:

**Repositorio de Backend**
<img src="../assets/img/chapter-VII/backend-main.png">

**Repositorio de Frontend**
<img src="../assets/img/chapter-VII/frontend-main.png">

**Repositorio de Mobile**
<img src="../assets/img/chapter-VII/mobile-main.png">

**Repositorio de Landing Page**
<img src="../assets/img/chapter-VII/landing-main.png">

**Reglas de protección para la rama main**
<img src="../assets/img/chapter-VII/backend-rule.png">
<img src="../assets/img/chapter-VII/backend-rule-1.png">

Escenario cuando se crea un pull request a la rama main:
<img src="../assets/img/chapter-VII/backend-rule2.png">
<img src="../assets/img/chapter-VII/backend-rule3.png">

### 7.1.2. Build & Test Suite Pipeline Components

**Backend:**

- Pipeline de compilación con Maven

<img src="../assets/img/chapter-VII/backend-ci.png">
<img src="../assets/img/chapter-VII/backend-ci-1.png">
<img src="../assets/img/chapter-VII/backend-workflows.png">

A continuación, se muestra el archivo de configuración .yml de GitHub Actions utilizado para compilar y ejecutar pruebas en el backend utilizando Maven:

```yaml
name: CI - Backend

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main, develop]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Set up JDK 21
        uses: actions/setup-java@v3
        with:
          java-version: '21'
          distribution: 'temurin'

      - name: Cache Maven packages
        uses: actions/cache@v3
        with:
          path: ~/.m2
          key: ${{ runner.os }}-maven-${{ hashFiles('**/pom.xml') }}
          restore-keys: |
            ${{ runner.os }}-maven-

      - name: Build and test with Maven
        run: mvn -B clean verify
```

Este workflow garantiza que en cada push o pull request a las ramas main o develop, el código se compila correctamente y se ejecutan las pruebas unitarias antes de permitir un merge.

**Frontend:**

- Pipeline de compilación con Node

Compilando archivo yaml
<img src="../assets/img/chapter-VII/frontend-ci-1.png">

Ruleset cuando requiere aprobación de un reviewer para aprobar el merge
<img src="../assets/img/chapter-VII/frontend-ci-2.png">

Compilación exitosa y permite hacer merge
<img src="../assets/img/chapter-VII/frontend-ci-3.png">

A continuación, se muestra el archivo de configuración .yml de GitHub Actions utilizado para compilar y ejecutar pruebas en el frontend utilizando Node:

```yaml
name: CI - Frontend

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main, develop]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v3

      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'

      - name: Install dependencies
        run: npm ci

      - name: Build Angular app
        run: npm run build -- --configuration=production
```

Este workflow garantiza que en cada push o pull request a las ramas main o develop, el código se compila correctamente y se ejecutan las pruebas unitarias antes de permitir un merge.

## 7.2. Continuous Delivery

### 7.2.1. Tools and Practices

**Backend**

- Herramientas:

    - Azure App Service para el despliegue continuo desde nuestro repositorio Git
    - GitHub: Configurado como repositorio de origen para el App Service.

- Prácticas:
    - Despliegue automático a Azure App Service cuando se hace un commit a la rama main o develop.
    - Generación del *.jar en cada build y sincronización con Azure.
    - Variables de entorno configuradas en Azure para conectar con la base de datos en Aiven.

Centro de Implementación de Azure App Service: 

Utilizamos como origen el repositorio de Github, rama main. Para la compilación usamos la pila de entorno de Java y versión 21. 

<img src="../assets/img/chapter-VII/backend-azure.png">

**Frontend**

- Herramientas:

    - Netlify para el despliegue continuo desde nuestro repositorio Git
    - GitHub: Configurado como repositorio de origen para el despliegue.

- Prácticas:
    - Despliegue automático a Netlify cuando se hace un pull request a la rama main o develop.

Centro de Implementación de Netlify: 

Utilizamos como origen el repositorio de Github, rama main. Para la compilación usamos Node.js y versión 18. 

<img src="../assets/img/chapter-VII/frontend-netlify.png">
<img src="../assets/img/chapter-VII/frontend-netlify-1.png">

### 7.2.2. Stages Deployment Pipeline Components

**Backend**

1. Build:
    - El Servicio de compilación de App Service (Kudu) reconoce nuestro proyecto de backend con Maven y ejecuta el comando `mvn clean package` para generar el archivo .jar.
    - Busca un archivo .jar generado y lo despliega en nuestro app service.

2. Deployment:
    - Azure App Service captura el build y despliega automáticamente.  

Diagrama de flujo del deployment del backend:
<img src="../assets/img/chapter-VII/diagram-ci.png">

**Frontend**

1. Build:
    - El Servicio de compilación de Netlify reconoce automáticamente nuestro proyecto de frontend con Angular y ejecuta el comando `npm ci` para instalar las dependencias de Node y el comando `npm run build` para compilar el código fuente.

2. Deployment:
    - Netlify captura el build y despliega automáticamente.  

Diagrama de flujo del deployment del frontend:
<img src="../assets/img/chapter-VII/diagram-ci-frontend.png">

## 7.3. Continuous deployment

### 7.3.1. Tools and Practices

**Backend**

- Herramientas utilizadas:
    - GitHub: Repositorio del código fuente del backend.
    - GitHub Actions: Ejecuta el pipeline de CI (build, test, análisis de código).
    - Azure App Service: Plataforma como servicio (PaaS) para desplegar la aplicación de Spring Boot.
    - App Service Deployment Center: Permite conectar el repositorio GitHub (modo Git externo) para sincronizar cambios y hacer el despliegue.

- Buenas prácticas aplicadas:
    - Separación entre ramas de desarrollo (develop) y producción (main).
    - Revisión de código mediante pull requests antes de hacer merge a main.
    - Generación del .jar con Maven en cada commit validado.
    - Despliegue controlado manualmente a producción desde Azure.
    - Uso de una pila compatible de versiones (Java 21, Spring Boot 3.x).

**Frontend**

- Herramientas utilizadas:
    - GitHub: Repositorio del código fuente del backend.
    - GitHub Actions: Ejecuta el pipeline de CI (build, test, análisis de código).
    - Netlify: Plataforma como servicio (PaaS) para desplegar la aplicación de Angular.

- Buenas prácticas aplicadas:
    - Separación entre ramas de desarrollo (develop) y producción (main).
    - Revisión de código mediante pull requests antes de hacer merge a main.
    - Compilación del código fuente con Angular en cada commit validado.
    - Despliegue controlado automáticamente a producción desde Netlify.

### 7.3.2. Production Deployment Pipeline Components

**Backend**

Flujo del pipeline de despliegue a producción:

- Hacemos un merge a la rama main.
- GitHub detecta el push y GitHub Actions ejecuta el CI:

    - Checkout del código
    - Setup de JDK 21
    - Build con Maven (mvn clean package)
    - Tests automáticos

- En el centro de implementación de Azure App Service:
    - Se detecta que hubo un nuevo commit en main
    - Se clona el repo y se genera nuevamente el .jar
    - Se despliega el .jar a producción en el contenedor Java de Azure App Service

Evidencia de un deployment en el app service de Azure luego de un push a main:
<img src="../assets/img/chapter-VII/backend-deploy-last.png">
<img src="../assets/img/chapter-VII/backend-deploy-1.png">
<img src="../assets/img/chapter-VII/backend-swagger-deployed.png">

Link de la REST API desplegada: https://restyle-web-services-cyf0axfvakcxaehd.brazilsouth-01.azurewebsites.net/swagger-ui/index.html#/

**Frontend**

Flujo del pipeline de despliegue a producción:

- Hacemos un merge a la rama main.
- GitHub detecta el push y GitHub Actions ejecuta el CI:

    - Checkout del código
    - Descargar dependencias con `npm ci`
    - Build con Node `npm run build`
    - Tests automáticos

- En el centro de implementación de Netlify:
    - Se detecta que hubo un nuevo commit en main
    - Se despliega el código a producción

Evidencia de un deployment en la interfaz de Netlify luego de un push a main:
<img src="../assets/img/chapter-VII/frontend-netlify.png">
<img src="../assets/img/chapter-VII/frontend-deployed.png">

Link del frontend desplegado: https://restyle-frontend.netlify.app/

## 7.4. Continuous Monitoring

La monitorización continua es fundamental para garantizar la estabilidad, el rendimiento y la seguridad de la aplicación, tanto en el entorno backend (desplegado en Azure App Service) como en el frontend (desplegado en Netlify). Esta estrategia permite detectar de forma temprana anomalías y reaccionar rápidamente ante incidencias.

### 7.4.1. Tools and Practices

**Backend:**  
- **Azure Monitor y Application Insights:**  
  Recopilan métricas de rendimiento (latencia, throughput, tasa de error) y logs de la aplicación, facilitando el diagnóstico de incidencias.  
  Fuente: [Azure Monitor Overview](https://learn.microsoft.com/es-es/azure/azure-monitor/overview)

  <img src="../assets/img/chapter-VII/sprint-2/backend-tools1.png">

- **Azure Log Analytics:**  
  Permite la agregación y análisis avanzado de logs usando el lenguaje de consultas KQL para profundizar en el comportamiento del sistema.  
  Fuente: [Azure Log Analytics](https://learn.microsoft.com/es-es/azure/azure-monitor/logs/log-analytics-overview)

   <img src="../assets/img/chapter-VII/sprint-2/backend-tools2.png">

- **Prácticas Generales:**  
  - Monitoreo 24/7 mediante dashboards personalizados en Azure.  
  - Implementación de Health Checks en endpoints críticos para asegurar la disponibilidad.  
  - Revisión periódica de logs y métricas a través de consultas automatizadas.

**Frontend:**  
- **Sentry y LogRocket:**  
  Estas herramientas registran y analizan errores de la aplicación Angular en tiempo real, proporcionando información detallada (stack trace, contexto del navegador, etc.).  
  Fuentes:  
  - [Sentry para JavaScript](https://sentry.io/for/javascript/)  

  <img src="../assets/img/chapter-VII/sprint-2/frontend-tools1.png">

  - [LogRocket](https://logrocket.com/)

  <img src="../assets/img/chapter-VII/sprint-2/frontend-tools2.png">

- **Netlify Analytics:**  
  Complementa la monitorización al ofrecer métricas de rendimiento (tiempos de carga, interacciones de usuario) directamente relacionadas con la experiencia en producción.  
  Fuente: [Netlify Analytics](https://www.netlify.com/products/analytics/)

    <img src="../assets/img/chapter-VII/sprint-2/frontend-tools3.png">

- **Prácticas Generales:**  
  - Integración de dashboards centralizados para la visualización de métricas y errores del frontend.  
  - Uso de métricas de experiencia del usuario (UX) para optimizar la interfaz.

### 7.4.2. Monitoring Pipeline Components

El pipeline de monitoreo se compone de los siguientes elementos:

1. **Agregación de Datos:**  
   - En el backend, agentes de Azure Monitor capturan métricas y logs, enviándolos a Azure Log Analytics para su análisis.  
   - En el frontend, los SDKs de Sentry y LogRocket recogen eventos y errores, integrándose en dashboards personalizados.

2. **Procesamiento y Análisis:**  
   - Uso de consultas KQL en Azure Log Analytics para filtrar y analizar logs.  
   - Los datos de Sentry/LogRocket se procesan para identificar patrones de errores y tendencias en el comportamiento de la aplicación.

3. **Visualización:**  
   - Dashboards en el portal de Azure muestran métricas clave (latencia, tasa de error, uso de recursos) en tiempo real.  
   - Paneles interactivos en Sentry y Netlify Analytics ofrecen una visión clara de la salud y el rendimiento del frontend.

    <img src="../assets/img/chapter-VII/sprint-2/monitoring1.png">

### 7.4.3. Alerting Pipeline Components

Para reaccionar de forma inmediata ante incidentes, se configura un sistema robusto de alertas:

1. **Definición de Umbrales:**  
   - Establecimiento de límites críticos, por ejemplo:  
     - Latencia superior a 1000 ms.  
     - Tasa de error HTTP (5xx) que supere un porcentaje determinado.  
     - Disponibilidad menor al 99.9%.
   - Ejemplo de consulta en Azure Log Analytics para detectar alta latencia:
     ```kql
     requests
     | where duration > 1000
     | summarize avg(duration) by bin(timestamp, 5m)
     ```

2. **Configuración de Alertas:**  
   - En Azure Monitor se configuran alertas basadas en las consultas, las cuales se activan al superar los umbrales predefinidos.  
   - Sentry y LogRocket permiten la generación de alertas en tiempo real en el frontend ante la detección de errores críticos.

3. **Integración con Acción:**  
   - Las alertas se integran con Action Groups de Azure para enviar notificaciones automáticas (correo, SMS, Slack) al equipo de soporte.

### 7.4.4. Notification Pipeline Components

El mecanismo de notificaciones asegura que toda alerta se comunique rápidamente al equipo responsable:

1. **Canales de Notificación:**  
   - **Slack/Teams:** Integraciones configuradas para enviar mensajes a canales específicos cuando se dispara una alerta.  
   - **Correo Electrónico y SMS:** Utilización de Action Groups en Azure para notificar de forma inmediata a los contactos asignados.

2. **Escalamiento y Seguimiento:**  
   - Si una alerta no es atendida en un tiempo determinado, se activa un proceso de escalamiento que involucra a niveles superiores de soporte.  
   - Se registra la recepción y resolución de alertas mediante sistemas de tickets, como Jira o ServiceNow, para garantizar un seguimiento adecuado.

3. **Confirmación de Notificaciones:**  
   - Procedimientos que confirman la recepción de notificaciones, permitiendo una trazabilidad completa de la respuesta ante incidentes.

Mediante la integración de estas herramientas y prácticas se garantiza un ecosistema de monitoreo robusto, que no solo detecta y alerta sobre posibles incidencias, sino que también facilita una respuesta rápida y eficaz, minimizando el impacto en la experiencia del usuario y manteniendo la alta disponibilidad del sistema.