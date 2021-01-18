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
---

### Herramientas varias para trabajar con archivos de imágenes

**[ExifTool by Phil Harvey](https://exiftool.org/)**
ExifTool es una biblioteca de Perl independiente de la plataforma más una aplicación de línea de comandos para leer, escribir y editar metainformación en una amplia variedad de archivos.

_Ejemplo para extraer todos los metadatos de una imagen:_ <code>exiftool -a MA-sample-id-556343.tif</code>

**[ImageMagick](https://imagemagick.org/)**
ImageMagick es un conjunto de utilidades de código abierto1​ para mostrar, manipular y convertir imágenes, capaz de leer y escribir más de 200 formatos.2

_Ejemplo para reducir al 50% una imagen:_ <code>magick mogrify -resize 50% rose.jpg</code>
_Ejemplo para crear copias reducidas de todos los jpg en otra carpeta:_ <code>magick mogrify -resize 200x200 -path ch *.jpg</code>

!!! **Porque usar aplicaciones de línea de comandos?**
!!! Principalmente porque, a diferencia de las aplicaciones gráficas, la línea de comandos consume muy pocos recursos y ejecuta las tareas mucho (mucho) más rápido. Eso se traduce en productividad a la hora de crear y ejecutar comandos en nuestra máquina o en un servidor remoto.

### Extraer metadatos de un archivo que contiene metadatos ISAD-G 

1. Descarga un archivo a elección: 
*     TIFF: [https://docs.museosabiertos.org/editor-de-metadatos/MA-sample-id-556343.tif](https://docs.museosabiertos.org/editor-de-metadatos/MA-sample-id-556343.tif)
*     JPG: [https://docs.museosabiertos.org/editor-de-metadatos/MA-sample-id-2498680.jpg](https://docs.museosabiertos.org/editor-de-metadatos/MA-sample-id-2498680.jpg)
3. Abre una ventana de terminal en su carpeta y ejecuta:
*   TIFF: <code>exiftool -xmp-isadg:all MA-sample-id-556343.tif</code>
*   JPG: <code>exiftool -xmp-isadg:all MA-sample-id-2498680.jpg</code>
