---
title: 'OCR + Traducción'
taxonomy:
    category:
        - docs
textsize:
    scale: ''
    modifier: '1'
style:
    header-font-family: ''
    header-color: ''
    block-font-family: ''
    block-color: ''
    background-color: ''
    background-image: ''
    background-size: ''
    background-repeat: ''
    justify-content: ''
    align-items: ''
class: ''
footer: ''
presentation:
    content: ''
    parser: ''
    styles: ''
---

## OCR y traducción con [Scan Tailor](https://scantailor.org/) + [Tesseract](https://github.com/tesseract-ocr/) + [Translate Shell](https://www.soimort.org/translate-shell/)


#### Cómo recuperar textos de imágenes y traducirlos a tu idioma en 3 pasos

> Este breve 'manual' está creado con la intención de poder ejecutar las tareas en Linux, OS X o Windows y con la línea de commandos, a fin de reducir significativamente el tiempo que requieren estas tareas.

! Requisitos: Debes tener instaladas, previamente, las cuatro aplicaciones

0. Escanea o fotografía tu documento (asegúrate de obtener un mínimo de 300 dpi)
1. Importa la imagen con Scan Tailor
		1. [tutorial](https://youtu.be/qLUgMQkkhtA)
2. `tesseract -l eng entrada.tif salida.txt`
		1. el parámetro [eng] se refiere al idioma de entrada (opcional)
3. `trans :es file://salida.txt -o traducido.txt` _(el sufijo '.txt' es opcional)_
		1. el parámetro [:es] se refiere al idioma al que debe ser traducido


#### Opcional
Puedes reducir el tamaño de tus imágenes al mínimo requerido y así para optimizar espacio en disco y procesamiento
		1. Crea una carpeta [3000px], para no sobreescribir el original (opcional)
		2. En la línea de commandos, dentro de la carpeta de la imágen, ejecuta la suguiente línea
		3. `mogrify -resize 3000x3000 -path 3000px *.tif`

! Debes tener instalado [Imagemagick](https://www.imagemagick.org/)

! Tip: OS X puedes usar [sips](https://bhrigu.me/blog/2020/04/12/mac-os-x-command-line-tools-to-edit-media/). Ejemplo: `sips -z [height] [width] file.png`

#### Ejemplo Bash
Esta línea obtiene el texto de la imagen, la graba en un archivo y luego la traduce

`tesseract -l eng IMG_20200911.tif IMG_20200911; trans :es file://IMG_20200911.txt -o IMG_20200911_ES.txt`


### Tips para escanear o fotografiar

Para obtener un buen resultado con Scan Tailor y minimizar los errores en el procesamiento automático, siga estas reglas al escanear:

* Escanea o fotografía todas las páginas [incluida la tapa y contratapa] con buena luz y con las mínimas deformaciones del plano.
* No escanees en modo blanco y negro; utiliza la escala de grises o, si es necesario, color.
* No escanees a una resolución inferior a 300 DPI, normalmente escanea en 300 o 600 DPI.
* No escanees a JPEG: el formato tiene pérdidas y la conversión a otros formatos no dará como resultado una mejor calidad. (Los usuarios de cámaras probablemente necesitarán usar el modo JPG, pero usarán la mejor resolución y la mejor configuración de calidad JPEG posible).
* Cuando escanees, use normalmente el formato TIFF, pero ten cuidado, ya que TIFF se puede usar para algoritmos de compresión JPEG.
* Si necesitas comprimir la imagen, elija LZW, un formato sin pérdidas
* Si no puedes usar TIFF, escanea a PNG; se garantiza el uso de algoritmos de compresión sin pérdida o, en casos extremos, a BMP (el tamaño del archivo no estará comprimido y, por lo tanto, será enorme, y preferiblemente debe convertirse a un formato que use compresión sin pérdida).
* Evita el modo de escaneo "Documento" y, en general, intenta desactivar todas las opciones para mejorar los escaneos.
* Siempre haz una prueba con un grupo de imágenes, de modo de poder optimizar el flujo al resultado final. Por ejemplo, Escanea/fotografía con diferentes calidades y busca aquella que sea la mínima calidad aceptable para Scan Tailor, de modo de no tener que procesar imágenes muy grandes, innecesariamente.

===

## Otros Manuales

* [OCR with Tesseract and ScanTailor](https://programminghistorian.org/en/lessons/retired/OCR-with-Tesseract-and-ScanTailor)


