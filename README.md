# GUIA DE YAML - ESPAÑOL

¡Bienvenido a la Guía Completa de YAML en Español! En el mundo del desarrollo de software y la administración de sistemas, la configuración y el intercambio de datos son tareas cotidianas. Necesitamos formatos que sean a la vez potentes para las máquinas y crucialmente, legibles para los humanos. Aquí es donde YAML (YAML Ain't Markup Language) brilla con luz propia.

Si alguna vez te has preguntado cómo funcionan los archivos de configuración de herramientas populares como Docker, Kubernetes, Ansible o incluso GitHub Actions, la respuesta a menudo reside en YAML. Es un formato de serialización de datos diseñado para ser amigable, intuitivo y, sobre todo, fácil de entender y escribir.

Esta guía ha sido creada pensando en ti, ya seas un desarrollador, un administrador de sistemas, un DevOps o simplemente alguien curioso que busca entender cómo se estructuran los datos de configuración hoy en día. Desde sus conceptos más básicos hasta sus características más avanzadas, te acompañaremos paso a paso para que domines YAML y lo apliques eficazmente en tus proyectos.

A lo largo de los siguientes capítulos, exploraremos la sintaxis fundamental, los tipos de datos, las estructuras avanzadas y las mejores prácticas. También veremos cómo se integra YAML con distintos lenguajes de programación y herramientas del día a día. Nuestro objetivo es proporcionarte una referencia clara y práctica que te permita no solo leer, sino también escribir y validar tus propios archivos YAML con confianza.

## Índice

### [Capítulo 1 - Introducción a YAML](capitulo-1.md)
<details>
   <summary>Contenido</summary>
   
1. ¿Qué es YAML?
   - Origen y propósito
   - ¿Por qué usar YAML? Ventajas y desventajas
   - Casos de uso comunes (configuración, orquestación, etc.)
2. Diferencias entre YAML, JSON y XML
   - Comparativa de sintaxis
   - Cuándo elegir YAML sobre otros formatos
</details>
   
### [Capítulo 2 - Sintaxis Básica de YAML](capitulo-2.md)
<details>
   <summary>Contenido</summary>

1. Estructura fundamental
   - Clave-Valor (Mappings/Objetos)
   - Listas (Sequences/Arrays)
   - Escalares (Strings, Números, Booleanos, Nulos)
2. Indentación y Espacios
   - La importancia de los espacios
   - Errores comunes de indentación
3. Comentarios
   - Comentarios de una línea
   - Buenas prácticas para comentar
</details>

### [Capítulo 3: Tipos de Datos y Representación](capitulo-3.md)
<details>
   <summary>Contenido</summary>

1. Cadenas de Texto (Strings)
   - Cadenas sin comillas
   - Cadenas con comillas simples y dobles
   - Cadenas multilínea (literales y plegadas)
2. Números
   - Enteros
   - Flotantes
   - Notación exponencial
3. Booleanos
   - Valores verdaderos y falsos
4. Nulos
   - Representación de valores nulos
5. Fechas y Horas
   - Formatos estándar de fecha y hora
6. Binario (opcional, para casos específicos)
</details>

### Capítulo 4: Estructuras Avanzadas

1. Anidamiento de Clave-Valor y Listas
   - Creación de estructuras complejas
2. Bloques de Estilo
   - Bloques escalares (literal y plegado)
3. Anclas y Alias (Reutilización de datos)
   - Definición de anclas (&)
   - Uso de alias (*)
   - Casos de uso y beneficios
4. Directivas YAML
   - Directivas de versión (%YAML)
   - Directivas de etiquetas (%TAG)

### Capítulo 5: Validación y Herramientas

1. Herramientas de Validación YAML
   - Validadores online
   - Herramientas de línea de comandos (Ej: yamllint)
2. Esquemas YAML (ej. JSON Schema para YAML)
   - ¿Qué son y para qué sirven?
   - Cómo definir y usar esquemas

### Capítulo 6: Integración y Uso Práctico

1. YAML en Lenguajes de Programación
   - Python (PyYAML)
   - JavaScript (js-yaml)
   - Go (gopkg.in/yaml.v2)
   - Otros lenguajes (mencionar librerías populares)
2. Ejemplos de Uso Real
   - Archivos de configuración (Docker Compose, Kubernetes)
   - Automatización (Ansible)
   - CI/CD (GitHub Actions, GitLab CI)

### Capítulo 7: Buenas Prácticas y Consejos

1. Legibilidad y Mantenibilidad
   - Consistencia en la indentación
   - Uso apropiado de comentarios
2. Evitar Errores Comunes
   - Problemas con espacios al final de línea
   - Orden de las claves (aunque YAML no garantiza el orden)
3. Seguridad en YAML
   - Deserialización de datos no confiables

### Apéndice A: Referencia Rápida de Sintaxis
### Apéndice B: Preguntas Frecuentes (FAQ)
### Apéndice C: Recursos Adicionales



- [Introducción de YAML](introduccion.md)
- [Tipos de datos en YAML](tiposdedatos.md)
- [Elementos de GitHub Actions](elementos.md)











