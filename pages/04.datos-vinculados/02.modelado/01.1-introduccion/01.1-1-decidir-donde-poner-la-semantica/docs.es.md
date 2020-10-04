---
taxonomy:
    category:
        - docs
title: '1.1 Decidir dónde poner la semántica'
---

¿Qué tiene esto que ver con los [datos vinculados](https://es.wikipedia.org/wiki/Datos_enlazados)? 
Los ejemplos anteriores demuestran que tanto el uso de un modelo genérico estandarizado como el de un modelo específico altamente personalizado tienen un costo. El tremendo esfuerzo que la [comunidad de LIS](https://es.wikipedia.org/wiki/Bibliotecas_y_ciencia_de_la_informaci%C3%B3n) ha puesto en la estandarización de metadatos refleja cómo hemos estado tratando de encontrar un punto óptimo entre los dos enfoques. Como se demostrará a través de ejemplos prácticos, la evolución de una narrativa no estructurada a una representación altamente estructurada de metadatos requiere el desarrollo de esquemas para que los metadatos sean interoperables.

Al dividir las narrativas descriptivas no estructuradas en campos bien estructurados, necesitamos hacer explícito el significado de los diferentes campos (también llamados atributos) documentándolos en un esquema. Al estructurar y atomizar los campos de metadatos, los hacemos más interoperables con las máquinas, pero también dependemos cada vez más de los esquemas cuando necesitamos interpretar nuestros propios metadatos o los de otra persona. Es precisamente en este contexto donde es necesario comprender los datos vinculados.
Mediante la adopción de un modelo de datos radicalmente simple, se puede abstraer el [XML](https://es.wikipedia.org/wiki/Extensible_Markup_Language) tradicional y los esquemas de base de datos que teníamos que usar en el pasado para interpretar y reutilizar los datos.
