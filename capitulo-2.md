[:point_up_2: Volver al Índice](README.md) | [:point_left: Capítulo 1](capitulo-1.md) | [:point_right: Capítulo 3](capitulo-3.md)

---

# Capítulo 2 - Sintaxis Básica de YAML

---

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

[:point_up_2: Volver al Índice](README.md) | [:point_left: Capítulo 1](capitulo-1.md) | [:point_right: Capítulo 3](capitulo-3.md)
