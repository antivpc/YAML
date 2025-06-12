[:point_up_2: Volver al Índice](README.md) | [:point_left: Capítulo 1](capitulo-1.md) | [:point_right: Capítulo 3](capitulo-3.md)

---

# Capítulo 2 - Sintaxis Básica de YAML

## 1. Estructura Fundamental

La simplicidad y legibilidad de YAML se basan en tres estructuras fundamentales: los `pares clave-valor` (conocidos como *mappings* u objetos), las **listas** (también llamadas *sequences* o arrays) y los **escalares** (los valores atómicos como cadenas de texto, números, booleanos, etc.). La **indentación** con espacios es la piedra angular que define la jerarquía y la anidación de estas estructuras.

##
### Clave-Valor (Mappings / Objetos)

Los pares clave-valor son la forma más básica de representar datos estructurados en YAML, similar a los objetos en JSON o los diccionarios en Python. Cada par consta de una **clave** seguida de dos puntos (`:`) y luego su **valor**. Es crucial que haya al menos un espacio después de los dos puntos.

* `Sintaxis:` `clave: valor`

**Características clave:**

* `Orden:` En YAML, el orden de las claves dentro de un *mapping* no está garantizado, aunque muchos procesadores lo mantengan. No dependas del orden.
* `Unicidad:` Las claves dentro de un mismo nivel de un *mapping* deben ser únicas.
* `Valores:` Los valores pueden ser escalares, otras *mappings* (objetos anidados) o listas.

**Ejemplos:**

```yaml
nombre: Juan
edad: 30
es_estudiante: true
saldo: 1500.75
direccion:
  calle: Calle Falsa 123
  ciudad: Springfield
  codigo_postal: "12345" # Una cadena, aunque parezca un número
```

En este ejemplo:
* `nombre`, `edad`, `es_estudiante`, `saldo`, y `direccion` son **claves**.
* `Juan`, `30`, `true`, `1500.75` y el *mapping* de `direccion` son sus respectivos **valores**.
* `direccion` contiene un *mapping* anidado con sus propias claves (`calle`, `ciudad`, `codigo_postal`) y valores.

##
### Listas (Sequences / Arrays)

Las listas en YAML representan una colección ordenada de elementos, similar a los arrays en JavaScript o las listas en Python. Cada elemento de una lista se indica con un guion (`-`) seguido de un espacio.

* **Sintaxis:**
    ```yaml
    - elemento1
    - elemento2
    - elemento3
    ```

**Características clave:**

* **Orden:** Los elementos de una lista mantienen el orden en que fueron definidos.
* **Valores:** Los elementos de una lista pueden ser escalares, *mappings* (objetos) o incluso otras listas (listas anidadas).

**Ejemplos:**

```yaml
frutas_favoritas:
  - Manzana
  - Plátano
  - Cereza

habilidades:
  - nombre: Programación
    nivel: Avanzado
  - nombre: Diseño
    nivel: Intermedio
  - nombre: Idiomas
    detalles:
      - Español
      - Inglés
      - Alemán
```

En estos ejemplos:
* `frutas_favoritas` es una **lista** de cadenas de texto.
* `habilidades` es una **lista de *mappings***. Cada elemento de la lista es un "objeto" que describe una habilidad.
* Dentro del *mapping* de "Idiomas", `detalles` es una **lista anidada** de cadenas de texto.

**Formato en línea (Flow Style):**

YAML también permite definir listas y *mappings* en una sola línea, usando la sintaxis de JSON, lo cual es útil para estructuras pequeñas o para hacer los archivos más compactos:

* **Listas en línea:** Se usan corchetes `[]` y comas `,` para separar elementos.
    ```yaml
    numeros: [1, 2, 3, 4]
    colores: ["rojo", "verde", "azul"]
    ```
* **Mappings en línea:** Se usan llaves `{}` y comas `,` para separar pares clave-valor.
    ```yaml
    usuario: { id: 101, nombre: "Ana", activo: true }
    ```
Aunque este estilo es válido, a menudo se prefiere el estilo de bloque (usando indentación y guiones) para una mayor legibilidad, especialmente en archivos de configuración.

##
### Escalares (Strings, Números, Booleanos, Nulos)

Los escalares son los valores atómicos en YAML, es decir, no pueden dividirse en componentes más pequeños dentro de la estructura de YAML. YAML es inteligente y a menudo puede inferir el tipo de dato de un escalar sin necesidad de comillas.

**Tipos comunes de escalares:**

* **Cadenas de Texto (Strings):**
    * No necesitan comillas si no contienen caracteres especiales (`:` , `-`, `#`, etc.) ni inician con caracteres que puedan ser interpretados como otros tipos.
    * `nombre: "Maria"` (con comillas)
    * `mensaje: Hola mundo` (sin comillas)
    * `version: 1.0.0` (una cadena, no un número, por la presencia de puntos como parte de una versión)
* **Números:**
    * **Enteros:** `edad: 25`, `cantidad: -10`
    * **Flotantes:** `precio: 19.99`, `gravedad: 9.81`
* **Booleanos:**
    * Representan valores de verdad. YAML acepta varias representaciones para `true` y `false`.
    * `activo: true`, `estado: True`, `aprobado: yes`
    * `desactivado: false`, `terminado: False`, `cancelado: no`
* **Nulos (Null):**
    * Representa la ausencia de valor. Se puede usar `null` o `~`.
    * `descripcion: null`
    * `valor_nulo: ~`

**Ejemplos combinados de escalares:**

```yaml
configuracion_general:
  aplicacion: MiApp
  version: 2.3.1
  debug: true
  limite_usuarios: 500
  precio_unitario: 24.99
  fecha_inicio: 2024-06-12
  token_api: null
```

Es crucial recordar que la **indentación correcta** es lo que le dice a YAML cómo se relacionan estos pares clave-valor, listas y escalares entre sí. Cada nivel de anidamiento debe tener una indentación consistente (generalmente 2 o 4 espacios).

---

## 2. Indentación y Espacios

La **indentación** es el pilar fundamental de la sintaxis de YAML. A diferencia de otros formatos como XML o JSON que usan llaves (`{}`), corchetes (`[]`) o etiquetas para definir la estructura, YAML utiliza **espacios en blanco** al inicio de cada línea para indicar la jerarquía y el anidamiento de los datos. Esto es lo que le otorga su extrema legibilidad, pero también lo que requiere precisión.

##
### La Importancia de los Espacios

En YAML:

* **Los espacios son significativos:** La cantidad de espacios al comienzo de una línea determina si un elemento es hijo de otro o si está al mismo nivel.
* **No se permiten tabulaciones:** Es vital usar **solo espacios** para la indentación. Los analizadores de YAML suelen rechazar archivos que contengan tabulaciones, o pueden interpretarlos de manera inesperada. La mayoría de los editores de código están configurados para convertir las tabulaciones en espacios automáticamente, pero es algo a tener en cuenta.
* **Indentación consistente:** Dentro de un mismo nivel de anidamiento, todos los elementos deben tener la misma cantidad de espacios de indentación. El estándar recomienda usar **dos espacios** o **cuatro espacios** para cada nivel de indentación, pero lo más importante es ser **consistente** en todo el documento. Si decides usar dos espacios por nivel, úsalos siempre; si decides usar cuatro, haz lo mismo.

Veamos cómo funciona la indentación con un ejemplo:

```yaml
# Nivel 0
persona:
  # Nivel 1 (2 espacios de indentación)
  nombre: Ana
  edad: 28
  ciudad: Barcelona
  # Nivel 1, contiene un mapping anidado
  contacto:
    # Nivel 2 (4 espacios de indentación, 2 más que el nivel 1)
    email: ana@ejemplo.com
    telefono: "123-456-7890"
  # Nivel 1, contiene una lista
  hobbies:
    # Nivel 2 (4 espacios de indentación)
    - leer
    - cocinar
    - viajar
```

En este ejemplo:
* `persona` está en el nivel superior (sin indentación).
* `nombre`, `edad`, `ciudad`, `contacto`, y `hobbies` están indentados con **dos espacios**, lo que los convierte en propiedades del objeto `persona`.
* `email` y `telefono` están indentados con **cuatro espacios** (dos más que `contacto`), lo que los convierte en propiedades del objeto `contacto`.
* `leer`, `cocinar`, y `viajar` (elementos de la lista `hobbies`) también están indentados con **cuatro espacios** y precedidos por el guion (`-`).

##
### Errores Comunes de Indentación

La sensibilidad a la indentación es una de las principales fuentes de errores al escribir YAML. Presta especial atención a los siguientes problemas comunes:

1.  **Uso de Tabulaciones en lugar de Espacios:**
    * **Incorrecto (con tabulaciones):**
        ```yaml
        config:
        	puerto: 8080 # Aquí hay una tabulación
        ```
    * **Correcto (con espacios):**
        ```yaml
        config:
          puerto: 8080 # Aquí hay 2 espacios
        ```
    **Consejo:** Configura tu editor de código para reemplazar las tabulaciones con espacios automáticamente (generalmente es la configuración por defecto para YAML).

2.  **Indentación Inconsistente:**
    * **Incorrecto (mezclando niveles de indentación o números de espacios):**
        ```yaml
        servicios:
          web:
            puerto: 80 # 2 espacios
           version: 1.0 # 3 espacios, inconsistente con 'puerto'
          db: # 2 espacios
            usuario: admin # 4 espacios
           password: secure # 3 espacios
        ```
    * **Correcto:**
        ```yaml
        servicios:
          web:
            puerto: 80
            version: 1.0
          db:
            usuario: admin
            password: secure
        ```
    **Consejo:** Elige una cantidad de espacios (2 o 4 son los más comunes) y sé estricto con ella.

3.  **Espacios Faltantes Después de los Dos Puntos (`:`):**
    El separador clave-valor (`:`) debe ir siempre seguido de al menos un espacio.
    * **Incorrecto:**
        ```yaml
        nombre:Juan
        edad :30
        ```
    * **Correcto:**
        ```yaml
        nombre: Juan
        edad: 30
        ```

4.  **Guiones de Lista Mal Indentados o sin Espacio:**
    El guion (`-`) de un elemento de lista debe estar correctamente indentado al mismo nivel de la lista y seguido de un espacio.
    * **Incorrecto:**
        ```yaml
        tareas:
        -Comprar pan # Sin espacio después del guion
         -Estudiar     # Mala indentación
        ```
    * **Correcto:**
        ```yaml
        tareas:
          - Comprar pan
          - Estudiar
        ```

**Herramientas para Evitar Errores:**

* **Editores de Código:** Utiliza editores como VS Code, Sublime Text, Atom, o IDEs como IntelliJ IDEA, que tienen excelente soporte para YAML. Estos resaltan errores de sintaxis, gestionan la indentación automáticamente y te alertan sobre problemas de espacios/tabulaciones.
* **Validadores YAML:** Herramientas online (como [YAML Lint](https://www.yamllint.com/)) o de línea de comandos (`yamllint`) son invaluables para verificar la sintaxis de tus archivos y encontrar errores de indentación antes de que causen problemas en tu aplicación.

Dominar la indentación es el paso más importante para escribir YAML efectivo y sin errores. Una vez que te acostumbres a ella, apreciarás la limpieza y legibilidad que ofrece este formato.

---

## 3. Comentarios

Los **comentarios** son líneas de texto que los procesadores de YAML ignoran completamente. Su propósito es hacer que tu código o archivo de configuración sea más fácil de entender para los humanos. Añadir comentarios es una **muy buena práctica** para documentar la intención, explicar decisiones de diseño, o incluso para deshabilitar temporalmente ciertas partes de la configuración.

##
### Comentarios de una Línea

En YAML, un comentario comienza con el símbolo de almohadilla o numeral (`#`). Todo lo que sigue al `#` en esa línea se considera parte del comentario y no será interpretado como parte de los datos YAML.

Puedes colocar comentarios:

1.  **En una línea separada:** Esto es ideal para explicar secciones enteras o para añadir notas generales.
    ```yaml
    # Este es un comentario que explica la configuración de la aplicación
    aplicacion: MiServicio
    ```

2.  **Al final de una línea de código:** Útil para explicar el propósito de una clave-valor específica.
    ```yaml
    puerto: 8080 # El puerto en el que la aplicación escuchará
    debug: true  # Habilitar el modo de depuración para desarrollo
    ```
    Es importante que haya al menos un espacio entre el valor y el `#` si el comentario va en la misma línea.

**Ejemplos:**

```yaml
# Configuración de la base de datos
database:
  type: postgres
  host: localhost
  port: 5432 # Puerto estándar para PostgreSQL
  username: admin
  password: supersecret # ¡En un entorno real, esto debería ser una variable de entorno!

# Lista de usuarios permitidos
usuarios_permitidos:
  - nombre: Alice
    rol: admin
  - nombre: Bob # Bob es un usuario regular
    rol: viewer
```

##
### Buenas Prácticas para Comentar

Aunque los comentarios son excelentes, es bueno seguir algunas pautas para mantener tus archivos YAML limpios y efectivos:

* **Sé claro y conciso:** El objetivo del comentario es añadir claridad, no confusión. Evita comentarios demasiado largos o redundantes.
* **Comenta el "por qué", no solo el "qué":** Es más útil explicar la razón detrás de una configuración (`# Habilitar CORS para permitir solicitudes desde el frontend`) que simplemente repetir lo que ya dice el código (`# Esto habilita CORS`).
* **Mantén los comentarios actualizados:** Un comentario desactualizado puede ser peor que no tener ninguno, ya que puede inducir a error. Si cambias el código, asegúrate de que el comentario siga siendo relevante.
* **Usa el espacio adecuadamente:** Para comentarios al final de la línea, un espacio antes del `#` mejora la legibilidad. Si el comentario es muy largo, considera ponerlo en una línea separada encima del elemento que comenta.
* **Evita comentar lo obvio:** Si una clave como `nombre_usuario: "admin"` es autoexplicativa, un comentario que diga `# Nombre de usuario` es innecesario.

**Ejemplo de buenas prácticas:**

```yaml
# Configuración del entorno de despliegue
# Esta sección define los parámetros específicos para el despliegue en producción
entorno:
  nombre: produccion
  # Deshabilitar las notificaciones por correo electrónico para evitar spam durante pruebas.
  # Se activarán una vez que el sistema esté completamente en vivo.
  notificaciones_email: false
  # El nivel de log debe ser 'info' o superior en producción para evitar sobrecarga de logs.
  log_level: info
```

Al incorporar comentarios de manera reflexiva, transformarás tus archivos YAML de simples contenedores de datos en documentos autodocumentados que son fáciles de entender y mantener para cualquiera que trabore con ellos, incluido tu yo futuro.

---

[:point_up_2: Volver al Índice](README.md) | [:point_left: Capítulo 1](capitulo-1.md) | [:point_right: Capítulo 3](capitulo-3.md)
