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

### Ejemplo de archivo con ISAD-G incrustado en XMP

1. Descarga el archivo: [https://docs.museosabiertos.org/editor-de-metadatos/DemoImage_ISADG-XMP-Metadata.png](https://docs.museosabiertos.org/editor-de-metadatos/DemoImage_ISADG-XMP-Metadata.png)
2. Abre una ventana de terminal en su carpeta y ejecuta:
<code>exiftool -xmp-isadg:all DemoImage_ISADG-XMP-Metadata.png</code>