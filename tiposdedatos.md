[:point_up_2: Volver al Indice](README.md) | [:point_left: Anterior](introduccion.md) | [:point_right: Siguiente](elementos.md)

# Tipos de Datos en YAML

YAML maneja tipos de datos que son comunes en muchos lenguajes de programación y sistemas de serialización, haciendo que los archivos sean intuitivos y fáciles de usar. Los tipos de datos principales son:

---

## 1. Escalares (Scalars)

Los escalares son los valores más simples y representan una única pieza de información. YAML infiere el tipo de dato basándose en el contenido, pero también se puede especificar explícitamente.

### a. Cadenas (Strings)

Representan texto. Son el tipo más común. No necesitan comillas la mayoría de las veces, a menos que contengan caracteres especiales o la sintaxis de YAML.

```yaml
# Cadenas sin comillas (recomendado si no hay caracteres especiales)
nombre: Juan Perez
ciudad: Nueva York

# Cadenas con comillas dobles (útil para caracteres especiales o escape)
mensaje: "Hola, ¿cómo estás?"
ruta: "C:\\usuarios\\documentos"

# Cadenas con comillas simples (útil si hay comillas dobles internas)
frase: 'Esto es un ejemplo con "comillas" internas.'

# Cadenas multilínea (mantienen saltos de línea y sangría)
descripcion_larga: |
  Este es un párrafo muy largo
  que se extiende en varias líneas.
  La sangría se mantiene.

# Cadenas multilínea (pliegan saltos de línea en un solo espacio)
parrafo_plegado: >
  Este párrafo se plegará
  en una sola línea.
  Múltiples espacios se reducirán a uno.
```

### b. Números Enteros (Integers)

Representan números sin decimales.

```yaml
edad: 30
cantidad: 100
```

### c. Números Flotantes (Floats)

Representan números con decimales.

```yaml
temperatura: 25.5
precio: 99.99
pi: 3.14159
```

### d. Booleanos (Booleans)

Representan valores de verdad: `true` (verdadero) o `false` (falso). También se pueden usar `True/False`, `TRUE/FALSE`, `on/off`, `yes/no`, `YES/NO`.

```yaml
casado: true
activo: no
permitir_acceso: YES
```

### e. Nulo (Null)

Representa la ausencia de valor. Se usa comúnmente con `null` o `~`.

```yaml
estado_civil: null
telefono_alternativo: ~
```

### f. Fecha y Hora (Date and Time)

YAML puede parsear cadenas que representan fechas y horas en formatos ISO 8601.

```yaml
fecha_nacimiento: 1990-05-15
ultima_modificacion: 2023-10-27T14:30:00Z
```

---

## 2. Colecciones (Collections)

Las colecciones son estructuras que agrupan múltiples valores.

### a. Listas (Lists/Sequences)

Representan una secuencia ordenada de elementos. Cada elemento de la lista se denota con un guion (`-`) seguido de un espacio.

```yaml
frutas_favoritas:
  - Manzana
  - Banana
  - Uva
numeros_primos: [2, 3, 5, 7, 11] # Notación de flujo (inline)
```

### b. Mapas (Maps/Dictionaries/Associative Arrays)

Representan una colección desordenada de pares clave-valor. Cada par se define como \`clave: valor\`. La clave es única dentro de un mapa.

```yaml
persona:
  nombre: Ana
  apellido: Gómez
  edad: 28
  ciudad: Medellín
configuracion_db: {host: localhost, port: 5432, user: admin} # Notación de flujo (inline)
```

---

## 3. Combinaciones de Tipos

YAML es muy flexible, permitiendo anidar colecciones dentro de otras colecciones, creando estructuras de datos complejas.

### a. Lista de Mapas

Común para representar una lista de objetos o registros.

```yaml
usuarios:
  - id: 1
    nombre: Carlos
    email: carlos@example.com
  - id: 2
    nombre: Laura
    email: laura@example.com
```

### b. Mapa de Listas

Un mapa donde algunos valores son listas.

```yaml
proyectos:
  frontend:
    - nombre: Website
      tecnologias: [HTML, CSS, JavaScript]
  backend:
    - nombre: API Rest
      tecnologias: [Python, Django, PostgreSQL]
```

---

Estos son los tipos de datos fundamentales que encontrarás al trabajar con YAML, cubriendo la mayoría de las necesidades para la serialización y configuración de datos.

[:point_up_2: Volver al Indice](README.md) | [:point_left: Anterior](introduccion.md) | [:point_right: Siguiente](elementos.md)
