# GUIA DE YAML - ESPAÑOL

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

### [Capítulo 4: Estructuras Avanzadas](capitulo-4.md)
<details>
   <summary>Contenido</summary>

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
</details>

### [Capítulo 5: Validación y Herramientas](capitulo-5.md)
<details>
   <summary>Contenido</summary>

1. Herramientas de Validación YAML
   - Validadores online
   - Herramientas de línea de comandos (Ej: yamllint)
2. Esquemas YAML (ej. JSON Schema para YAML)
   - ¿Qué son y para qué sirven?
   - Cómo definir y usar esquemas
</details>

### [Capítulo 6: Integración y Uso Práctico](capitulo-6.md)
<details>
   <summary>Contenido</summary>

1. YAML en Lenguajes de Programación
   - Python (PyYAML)
   - JavaScript (js-yaml)
   - Go (gopkg.in/yaml.v2)
   - Otros lenguajes (mencionar librerías populares)
2. Ejemplos de Uso Real
   - Archivos de configuración (Docker Compose, Kubernetes)
   - Automatización (Ansible)
   - CI/CD (GitHub Actions, GitLab CI)
</details>

### [Capítulo 7: Buenas Prácticas y Consejos](capitulo-7.md)
<details>
   <summary>Contenido</summary>

1. Legibilidad y Mantenibilidad
   - Consistencia en la indentación
   - Uso apropiado de comentarios
2. Evitar Errores Comunes
   - Problemas con espacios al final de línea
   - Orden de las claves (aunque YAML no garantiza el orden)
3. Seguridad en YAML
   - Deserialización de datos no confiables
</details>

### [Apéndice A: Referencia Rápida de Sintaxis](apendice-a.md)
### [Apéndice B: Preguntas Frecuentes (FAQ)](apendice-b.md)
### [Apéndice C: Recursos Adicionales](apendice-c.md)
