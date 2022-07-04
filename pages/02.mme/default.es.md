---
title: 'Museum Metadata Embedder'
hide_hypothesis: false
menu: 'Museum Metadata Embedder'
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
published: true
---

## [DRAFT]

**MME** (Museum Metadata Embedder) escribe (incrusta) metadatos -[Dublin Core](https://dublincore.org/specifications/dublin-core/), [VRA Core](https://core.vraweb.org/), [XMP](https://www.adobe.com/products/xmp.html), [ISAD(G)](https://www.ica.org/sites/default/files/CBPS_2000_Guidelines_ISAD(G)_Second-edition_EN.pdf), [IPTC](https://iptc.org/standards/photo-metadata/), [EXIF](https://docs.fileformat.com/image/exif/) y otros más- en [todo tipo de imágenes](https://exiftool.org/#supported) y archivos PDF a partir de un CSV normalizado.

**MME** es una aplicación de línea de comandos y tiene una interfaz gráfica, ejecutable en Linux, MacOS y Windows.

Mayormente, las colecciones de objetos se encuentran en hojas de cálculo que enumeran el contenido de sus colecciones, acompañado por las imágenes que los representan. Es decir que para ver los metadatos de una imagen, se debe contar con una planilla de cálculo; si quieres enviarla por email, debes enviar ambos archivos, donde el CSV o XLSX contiene normalmente la totalidad de la colección.

**MME** incrusta los metadatos de modo que ellos siempre se encuentren 'dentro' de la imagen, facilitando la ingestión por otras herramientas y simplificando los procesos de registro y difusión.

Para leer los metadatos detallados de una imagen o un archivo PDF solo es necesario ejecutar:
<code>exiftool -a -G1 -s <file></code>
o utilizar [Adobe Bridge Custom Metadata Panel](https://github.com/adobe-dmeservices/custom-metadata) o un servicio online, como [The Exifer](https://www.thexifer.net/)
 
    
===    
En lugar de volver a teclear todo esto en una herramienta como [Archivists' Toolkit](http://www.archiviststoolkit.org/) o en un editor XML, ¿no sería bueno generar automáticamente un documento XML de EAD a partir de la hoja de cálculo?

Con Stead puede hacerlo. Sólo hay que editar las cabeceras (primera fila de la hoja de cálculo) para que se ajusten al esquema de Stead. Esto puede implicar la división de algunas columnas para ajustarse al esquema, la adición de columnas y otras ediciones. Todo esto es probablemente más fácil, más rápido y más preciso de hacer en una hoja de cálculo que tratar de hacerlo en otro lugar volviendo a escribir todo.

Una vez que la hoja de cálculo esté lista, guárdela como CSV y utilice la herramienta de línea de comandos csv2ead para obtener un documento XML de EAD. Que lo disfrutes.
