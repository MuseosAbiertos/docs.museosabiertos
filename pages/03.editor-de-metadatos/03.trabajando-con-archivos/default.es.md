---
title: 'Trabajando con archivos'
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
hide_hypothesis: false
---

### Herramientas para trabajar con archivos de imágenes

**[ExifTool](exiftool)**
ExifTool (de Phil Harvey) es una biblioteca de Perl independiente de la plataforma más una aplicación de línea de comandos para leer, escribir y editar metainformación en una amplia variedad de archivos.

* _Ejemplo para extraer todos los metadatos de una imagen:_ <code>exiftool -a imagen.jpg</code>

**[ImageMagick](https://imagemagick.org/)**
ImageMagick es un conjunto de utilidades de código abierto, para mostrar, manipular y convertir imágenes, capaz de leer y escribir más de 200 formatos y ofrece un amplio conjunto de opciones para manipular imágenes.

* _Ejemplo para reducir una imagen al 50%:_ <code>magick mogrify -resize 50% imagen.jpg</code>

!!! **Porque usar aplicaciones de línea de comandos?**<br>
!!! Principalmente porque, a diferencia de las aplicaciones gráficas, la línea de comandos consume muy pocos recursos y ejecuta las tareas mucho más rápido. Eso se traduce en productividad a la hora de crear y ejecutar comandos en nuestra máquina o en un servidor remoto.

