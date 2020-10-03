---
title: Modelado
taxonomy:
    category: docs
---

## Resultados de aprendizaje de este capítulo

* Poner datos vinculados en un contexto más amplio
* Saliendo de la exagerada vista de la tecnología
* Comprender la importancia del modelado de datos.
* Dar sentido a los modelos de datos y sus formatos de serialización.

## 1. Introducción

Los administradores de metadatos y el software que utilizan a menudo parecen tener un parecido sorprendente con las parejas atrapadas en una relación infeliz. Durante las pausas para el café en conferencias y talleres sobre metadatos dentro del dominio de la ciencia de la información y la biblioteca, no tardará en detectar un círculo de personas que participan en lo que parece ser alguna forma de terapia de grupo.
No tengas miedo. Adelante, acércate un poco más. Probablemente escuche frases típicas como "¡Hemos estado luchando para crear nuevos campos de metadatos durante años!" O "¡Mi exportación XML es terrible!". Al enfrentarse a estos lamentos, los miembros del grupo asentirán con comprensión y expresarán su simpatía.
Quejarse del software de uno es un punto de discusión popular en todo el mundo cuando los propietarios de colecciones se reúnen para discutir los metadatos. Irónicamente, al igual que las parejas de ancianos que piensan dos veces antes del divorcio debido a las importantes consecuencias emocionales y económicas, los administradores de metadatos a menudo persisten durante años en la relación abusiva con su software.
Por lo general, prefieren no cambiar a otra solución de software.
¡Qué diferente es el ambiente en las humanidades digitales! En lugar de quejarse de las dificultades encontradas con su base de datos, las personas activas en las humanidades digitales a menudo se sienten muy orgullosas del sistema de información que construyeron para administrar un tipo específico de recurso o colección.
Susan Hockey incluso acuñó la expresión "documentos de mi base de datos y yo". Cualquiera que ya haya asistido a una conferencia de DH está familiarizado con el fenómeno: un investigador que presenta, con tedioso detalle, cómo se desarrolló una base de datos para acomodar cada característica peculiar de una colección. Estos oradores tienden a estar muy orgullosos de la bolsa de datos, la construyeron e irradian amor y pasión por ella.

¿Por qué estas dos comunidades tienen un enfoque tan diferente del software que utilizan para gestionar los recursos del patrimonio cultural y sus metadatos? ¿Por qué los poseedores de colecciones se quejan constantemente de su base de datos, mientras que los humanistas digitales expresan su satisfacción e incluso se jactan de la felicidad que encontraron con su base de datos?

Estas diferencias se relacionan con la medida en que el modelo utilizado para representar un objeto y sus metadatos se considera adecuado o no. Cuando queremos que los recursos y sus metadatos estén disponibles de manera estructurada en la web, primero debemos decidir qué características de los suyos son las más importantes para ser representadas. Al hacerlo, hacemos una abstracción de la realidad a través del desarrollo de un modelo.

En el contexto del patrimonio cultural que mencionamos, las instituciones se ven obligadas a trabajar con software estándar, ya que el desarrollo de un sistema de gestión de colecciones personalizado simplemente no es económicamente viable. El inconveniente de trabajar con software existente es que las instituciones a menudo se encuentran limitadas en cómo pueden describir sus objetos. Los proveedores tienen un incentivo comercial para desarrollar software genérico que se pueda vender a tantas instituciones como sea posible.

Esto implica que el software de gestión de colecciones ya prescribe una determinada cosmovisión explícita, mediante el uso de un modelo preestablecido. Por lo tanto, no siempre es posible adaptarse a los requisitos específicos de una institución y sus colecciones, lo que genera frustración entre los poseedores de colecciones.

Por el contrario, la comunidad DH utiliza bases de datos para proyectos de investigación limitados y específicos, ya que tienden a centrarse en la documentación y publicación de un tipo específico de recurso o colección. Dentro de estos proyectos de investigación limitados con un alcance preciso, los requisitos tienden a ser tan específicos que no es posible utilizar software estándar.

En este tipo de contexto, el software de gestión de bases de datos relacionales (RDMS) se utiliza a menudo para implementar un modelo personalizado. El inconveniente de cumplir con todos los requisitos precisos de tal proyecto son los costos de desarrollo relativamente altos y la dificultad de mantener la aplicación a lo largo del tiempo. Las inversiones se realizan en proyectos que muy a menudo no se pueden reutilizar.
