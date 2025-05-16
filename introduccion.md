# ¿Qué es YAML?

YAML (se pronuncia "yamel") es un `lenguaje de serialización de datos legible por humanos` que se utiliza a menudo para escribir archivos de configuración. El nombre YAML originalmente significaba "Yet Another Markup Language" (Otro Lenguaje de Marcado Más), pero ahora se interpreta como "`YAML Ain't Markup Language`" (YAML No es un Lenguaje de Marcado), lo que enfatiza que está diseñado para datos, no para documentos.

---

## Propósito Principal

El objetivo principal de YAML es proporcionar un `formato sencillo y fácil de leer y escribir` para representar datos estructurados. Esto lo hace ideal para situaciones donde la `legibilidad humana` es crucial, como en archivos de configuración para aplicaciones, herramientas de automatización y despliegue.

---

## Características Clave

* `Legibilidad humana`: Su sintaxis se asemeja al lenguaje natural, utilizando la **indentación** para indicar la estructura y las relaciones entre los datos.
* `Simple y conciso`: Evita el uso de muchos caracteres especiales como llaves, corchetes y comillas, lo que lo hace menos "ruidoso" visualmente que otros formatos como JSON o XML.
* `Soporte para tipos de datos`: Permite representar varios tipos de datos, incluyendo cadenas, números, booleanos, **listas** (secuencias) y **mapas** (pares clave-valor/diccionarios).
* `Comentarios`: Permite agregar comentarios en los archivos utilizando el símbolo de almohadilla (`#`), lo cual es muy útil para documentar la configuración.
* `Multilínea`: Permite escribir cadenas de texto que abarcan varias líneas, lo cual es útil para descripciones largas o bloques de texto.

---

## ¿Cómo funciona?

YAML utiliza la `indentación (espacios, no tabulaciones)` para definir la jerarquía de los datos. Los pares clave-valor se separan por dos puntos (`:`). Las listas se indican con un guion (`-`) al principio de cada elemento.

### Ejemplo Básico

```yaml
# Esto es un comentario en YAML
nombre: Juan Perez
edad: 30
casado: true
ciudades_visitadas:
  - Madrid
  - Buenos Aires
  - Nueva York
profesion: Desarrollador de Software
habilidades:
  lenguajes:
    - Python
    - JavaScript
    - Java
  herramientas:
    - Git
    - Docker
    - Kubernetes
```

---

## Usos Comunes en el Desarrollo de Software

* `Archivos de configuración`: Es muy popular para configurar aplicaciones, servicios y sistemas.
* `DevOps y Automatización`: Se utiliza ampliamente en herramientas como Docker (Docker Compose), Kubernetes, Ansible y CloudFormation para definir infraestructuras y flujos de trabajo.
* `Intercambio de datos`: Aunque JSON es más común para APIs web, YAML también se puede usar para el intercambio de datos entre sistemas.
* `Documentación`: Su legibilidad lo hace útil para la documentación de estructuras de datos.

---

En resumen, YAML es una herramienta muy útil para trabajar con datos estructurados de una manera que es fácil de leer y mantener para los humanos, lo que lo convierte en una opción popular en el mundo de la configuración y la automatización.

[Volver al Indice](README.md)
