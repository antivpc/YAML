[:point_up_2: Volver al Indice](README.md) | [:point_left: Anterior](tiposdedatos.md)

# Introducción a elementos de GitHub Actions

En el contexto de la automatización de CI/CD (Integración Continua/Entrega Continua) y específicamente en plataformas como GitHub Actions, estos términos son fundamentales para definir y ejecutar tareas automatizadas en tu repositorio de código. Comprenderlos te permitirá construir flujos de trabajo eficientes para probar, construir y desplegar tu software.

---

## 1. Workflows (Flujos de Trabajo)

Un `Workflow` es un proceso automatizado y configurable que consta de uno o más `Jobs`. Esencialmente, es el plan completo o la receta que define una serie de pasos a ejecutar. Los workflows se definen en archivos YAML y residen en el directorio `.github/workflows/` de tu repositorio.

* **Propósito**: Automatizar tareas repetitivas como la compilación de código, la ejecución de pruebas, el análisis de código, el despliegue de aplicaciones, o cualquier otra lógica de negocio que necesite ejecutarse automáticamente.
* **Ejemplo de uso**: Un workflow podría ser "Integración Continua", que se encarga de compilar el código y ejecutar las pruebas unitarias cada vez que se sube un cambio. Otro podría ser "Despliegue a Producción", que se activa manualmente o después de que se apruebe una pull request.

```yaml
# .github/workflows/ci.yml
name: Integración Continua

on: [push, pull_request] # Eventos que activan el workflow

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Configurar Node.js
        uses: actions/setup-node@v4
        with:
          node-version: '20'
      - name: Instalar dependencias
        run: npm install
      - name: Ejecutar pruebas
        run: npm test
```

---

## 2. Eventos / Triggers (Disparadores)

Un `Evento` o `Trigger` es una actividad específica que inicia la ejecución de un `Workflow`. Un workflow puede ser configurado para reaccionar a uno o varios eventos.

* **Propósito**: Especificar cuándo debe ejecutarse un workflow. Esto asegura que la automatización se dispare en el momento adecuado.
* **Tipos comunes de eventos**:
    * `push`: Cuando se sube código a una rama específica.
    * `pull_request`: Cuando se abre, actualiza o cierra una pull request.
    * `schedule`: En un horario programado (similar a un cron job).
    * `workflow_dispatch`: Permite ejecutar el workflow manualmente desde la interfaz de usuario.
    * `release`: Cuando se publica o actualiza una versión (release) del software.
* **Ejemplo en YAML**: La sección `on:` de un workflow define los eventos.

```yaml
on:
  push:
    branches:
      - main
  pull_request:
    branches: [main, develop]
  schedule:
    - cron: '0 0 * * *' # Ejecutar todos los días a medianoche UTC
  workflow_dispatch: # Permite ejecución manual
```

---

## 3. Jobs (Trabajos)

Un `Job` es un conjunto de `Steps` que se ejecutan en el mismo `Runner` (máquina virtual o contenedor). Un workflow puede contener uno o varios jobs, que pueden ejecutarse en paralelo o en secuencia, dependiendo de las dependencias que se definan entre ellos.

* **Propósito**: Dividir un workflow en unidades de trabajo lógicas y ejecutables. Cada job es independiente y se ejecuta en un entorno limpio.
* **Ejemplo de uso**: En un workflow de CI/CD, podría haber un job `build` (para compilar), un job `test` (para ejecutar pruebas) y un job `deploy` (para desplegar). El job `test` podría depender del job `build` para asegurar que solo se pruebe el código que compiló exitosamente.
* **Ejemplo en YAML**:

```yaml
jobs:
  build: # Nombre del job
    runs-on: ubuntu-latest # Dónde se ejecutará el job
    steps:
      # ... pasos para compilar
  test: # Otro job
    runs-on: ubuntu-latest
    needs: build # Este job depende del job 'build'
    steps:
      # ... pasos para ejecutar pruebas
```

---

## 4. Actions (Acciones)

Una **Action** es la unidad más pequeña y reutilizable de un `Workflow`. Son scripts o programas empaquetados que realizan una tarea específica. Las acciones pueden ser creadas por la comunidad, por GitHub, o ser acciones personalizadas que tú mismo desarrolles.

* **Propósito**: Simplificar y modularizar los pasos en un job. Permiten reutilizar lógica común sin tener que escribir el código desde cero cada vez.
* **Ejemplo de uso**:
    * `actions/checkout@v4`: Descarga el código de tu repositorio.
    * `actions/setup-node@v4`: Configura un entorno Node.js.
    * Una acción personalizada para desplegar en un servicio específico.
* **Ejemplo en YAML**: Se usan dentro de la sección `steps` de un job, utilizando la palabra clave `uses:`.

```yaml
steps:
  - uses: actions/checkout@v4 # Usa una acción de GitHub para descargar el código
  - name: Instalar dependencias # Un paso personalizado con un nombre
    run: npm install # Ejecuta un comando en el runner
  - name: Subir artefactos
    uses: actions/upload-artifact@v4 # Otra acción para subir archivos
    with:
      name: my-app
      path: dist/
```

---

## 5. Runners

Un **Runner** es un servidor o máquina virtual que tiene instalado el software del agente de GitHub Actions. Es el entorno donde se ejecutan tus `Jobs` y, por lo tanto, tus `Actions`.

* **Propósito**: Proporcionar el entorno de ejecución para los jobs de un workflow. Se encargan de descargar el código, ejecutar los comandos y acciones, y reportar el estado de vuelta a GitHub.
* **Tipos de Runners**:
    * **GitHub-hosted runners**: Máquinas virtuales provisionadas por GitHub. Son la opción más común y ofrecen diferentes sistemas operativos (Ubuntu Linux, Windows, macOS). Se destruyen después de cada ejecución de job.
    * **Self-hosted runners**: Máquinas o servidores que tú mismo configuras y mantienes. Son útiles si necesitas un entorno específico (hardware especial, sistema operativo no estándar, acceso a recursos de red privados) o si tienes requisitos estrictos de seguridad y rendimiento.
* **Ejemplo en YAML**: Se especifican en la sección `runs-on:` de un job.

```yaml
jobs:
  build:
    runs-on: ubuntu-latest # Usando un runner alojado en GitHub (Linux)
    steps:
      # ...

  deploy_on_premise:
    runs-on: self-hosted # Usando un runner que tú mismo has configurado
    steps:
      # ...
```

---

Estos componentes trabajan en conjunto para formar un sistema robusto y flexible para la automatización de tus procesos de desarrollo de software.

[:point_up_2: Volver al Indice](README.md) | [:point_left: Anterior](tiposdedatos.md)
