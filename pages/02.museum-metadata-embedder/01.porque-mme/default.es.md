---
title: 'Porqué MME [DRAFT]'
hide_hypothesis: false
twitterenable: true
twittercardoptions: summary
articleenabled: false
musiceventenabled: false
orgaenabled: false
orga:
    ratingValue: 2.5
orgaratingenabled: false
eventenabled: false
personenabled: false
musicalbumenabled: false
productenabled: false
product:
    ratingValue: 2.5
restaurantenabled: false
restaurant:
    acceptsReservations: 'yes'
    priceRange: $
facebookenable: true
menu: 'Porqué MME'
media_order: 'EXIF Data Configuration.png,xmpquote.gif'
---

Mayormente, las colecciones de objetos de arte se encuentran registradas en dos archivos, en hojas de cálculo que listan el contenido de sus colecciones y en imágenes, que los representan. 
Es decir, que para 'ver' los metadatos de una imagen, se debe contar con una aplicación de hojas de cálculo; si quieres enviarla por email, debes enviar ambos archivos, donde el archivo CSV contiene, normalmente, la totalidad de la colección.

## Dónde guardar los metadatos ?
En el universo GLAM, tradicionalmente, se considera que **una imagen de archivo nunca debe alterarse**, por lo que los metadatos se escriben 'fuera de la imagen', así sea en una base de datos o en un archivo externo (XMP, CSV...). Esta filosofía es la que hoy tienen la mayoría de las aplicaciones, por ejemplo, [Tropy](https://tropy.org/).

Sin embargo, esta presunción es errónea, dado que EXIF o XMP, si bien graban los datos dentro del archivo de imagen, no alteran la imagen, pues los graba dentro de un área de cabecera. Más aún, las aplicaciones apra escribir metadatos no tienen la capacidad para alterar las imágenes.

**MME** sigue una filosofía opuesta e incrusta los metadatos en un área reservada a ellos, de modo que ellos siempre se encuentren 'dentro' de la imagen, facilitando la ingestión y simplificando los procesos de registro y difusión, aunque no desaconseja 'también' guardarlos en un archivo CSV. De hecho, **MME** incrusta los metadatos a partir de un archivo CSV.

## Porqué escribir los metadatos en las imágenes ?

### EXIF (Exchangeable Image File Format)
La característica principal de Exif es su capacidad para grabar información de la cámara en un archivo de imagen en el punto de captura. Algunos campos de datos comunes incluyen la marca y el modelo de la cámara, su número de serie, la fecha y hora de la captura de la imagen, la velocidad de obturación, la apertura, la lente utilizada y la configuración de la velocidad ISO. Los metadatos Exif a menudo incluyen otros detalles técnicos, como el balance de blancos y la distancia al sujeto.

![EXIF%20Data%20Configuration](EXIF%20Data%20Configuration.png "EXIF%20Data%20Configuration")

El estándar Exif fue establecido en 1985 por la JCIA (Japan Camera Industry Association), el predecesor de CIPA (Camera & Imaging Products Association). Hoy en día, [JEITA](https://www.jeita.or.jp/english/) (Japan Electronics and Information Technology Industries Association) gestiona el estándar, mientras que CIPA discute la nueva tecnología y promueve el estándar.

_Leer más:_
* [EXIF](https://es.wikipedia.org/wiki/Exchangeable_image_file_format)
* [EXIF Data Explained](https://photographylife.com/what-is-exif-data)

### XMP (Extensible Metadata Plataform)

Adobe's Extensible Metadata Platform (XMP) es una tecnología de etiquetado creada por 'Adobe Systems Incorporated' en el año 2001. XMP registra o graba metadatos en una sintaxis formada por un subconjunto de la [W3C](https://www.w3.org/), la cual es escrita en [XML](https://www.w3.org/XML/).
Fue creado para extender el concepto, creado por EXIF a su gama de productos, ampliándolo a otros tipos de archivo con nuevos y más tipos de datos.

![xmpquote](xmpquote.gif "xmpquote")




 
