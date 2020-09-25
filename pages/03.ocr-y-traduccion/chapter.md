---
title: 'OCR + traducción'
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

#### Tips para escanear o fotografiar

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

## OCR y traducción con [Imagemagick](https://www.imagemagick.org/) + [Scan Tailor](https://scantailor.org/) + [Tesseract](https://github.com/tesseract-ocr/) + [Translate Shell](https://www.soimort.org/translate-shell/)

1. Escanea o fotografía tu documento
2. Crop?
		1. Dejar mínimamente unos @20 px por fuera del borde de la hoja escaneada/fotografiada
2. `mogrify -resize 3000x3000 -path 3000px *.tif`
		1. solo necesario si precisas achicarla
		2. previamente crear la carpeta [3000px], para no sobreescribir el original (opcional)
3. Scan Tailor
		1. Tutorial: https://youtu.be/qLUgMQkkhtA 
4. `tesseract -l eng entrada.tif salida`
		1. el parámetro [eng] se refiere al idioma de entrada (opcional)
5. `trans :es file://salida.txt -o traducido.txt`
		1. el parámetro [:es] se refiere al idioma al que debe ser traducido

## Ejemplo Bash
`# tesseract -l eng IMG_20200911.tif IMG_20200911; trans :es file://IMG_20200911.txt -o IMG_20200911_ES.txt`


===

## Otros Manuales

* [OCR with Tesseract and ScanTailor](https://programminghistorian.org/en/lessons/retired/OCR-with-Tesseract-and-ScanTailor)


