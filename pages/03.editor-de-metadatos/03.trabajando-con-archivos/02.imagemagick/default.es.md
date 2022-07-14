---
title: ImageMagick
hide_hypothesis: false
menu: ImageMagick
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

**[ImageMagick](https://imagemagick.org/)**
ImageMagick es un conjunto de utilidades de código abierto, para mostrar, manipular y convertir imágenes, capaz de leer y escribir más de 200 formatos y ofrece un amplio conjunto de opciones para manipular imágenes y las más comunes a los fines GLAM se pueden resumir en:

### Convert
https://imagemagick.org/script/convert.php
Utiliza 'magick' para convertir entre formatos de imagen, así como para cambiar el tamaño de una imagen, desenfocar, recortar, quitar manchas, tramar, dibujar, voltear, unir, volver a muestrear y mucho más.

**Algunos ejemplos:**
Para reducir el tamaño de la imagen antes de escribirla en formato PNG:
<code>magick imagen.jpg -resize 50% imagen.png</code>


### Mogrify
https://imagemagick.org/script/mogrify.php
Utiliza 'magick mogrify' para cambiar el tamaño de una imagen, desenfocar, recortar, quitar manchas, difuminar, dibujar, voltear, unir, volver a muestrear y mucho más
Esta herramienta es similar a la magia , excepto que el archivo de imagen original se sobrescribe (a menos que cambie el sufijo del archivo con la opción de formato ) con cualquier cambio que solicite.

**Algunos ejemplos:**
Para reducir una imagen al 50%:
<code>magick mogrify -resize 50% imagen.jpg</code>

Para crear una copia reducida en otra carpeta:
<code>magick mogrify -resize 200x200 -path ch imagen.jpg</code>


## Ejemplos de uso de ImageMagick
https://imagemagick.org/Usage/

## Annotated List of Command-line Options
https://imagemagick.org/script/command-line-options.php