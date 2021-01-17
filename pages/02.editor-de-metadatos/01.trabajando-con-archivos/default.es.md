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

1. Descarga un archivo a elección: 
*     TIFF: [https://docs.museosabiertos.org/editor-de-metadatos/MA-sample-id-556343.tif](https://docs.museosabiertos.org/editor-de-metadatos/MA-sample-id-556343.tif)
*     JPG: [https://docs.museosabiertos.org/editor-de-metadatos/MA-sample-id-2498680.jpg](https://docs.museosabiertos.org/editor-de-metadatos/MA-sample-id-2498680.jpg)
3. Abre una ventana de terminal en su carpeta y ejecuta:
*   TIFF: <code>exiftool -xmp-isadg:all MA-sample-id-556343.tif</code>
*   JPG: <code>exiftool -xmp-isadg:all MA-sample-id-2498680.jpg</code>
