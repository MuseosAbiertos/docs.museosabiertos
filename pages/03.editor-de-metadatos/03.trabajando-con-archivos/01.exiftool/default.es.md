---
title: ExifTool
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
menu: ExifTool
---

# Referencias

| Qué hacer                                          | Comando                                                      |
| -------------------------------------------------- | ------------------------------------------------------------ |
| Ejemplos de líneas de comando de ExifTool          | https://exiftool.org/examples.html                           |
| Archivos Sidecar de metadatos                      | https://exiftool.org/metafiles.html                          |
| ExifTool FAQ                                       | https://exiftool.org/faq.html                                |
| Procesador de lotes ExifTool                       | https://github.com/CarletonArchives/ExifTool-Batch-Processor |
| Lista completa de TAGS (según formato de archivo): | https://exiftool.org/TagNames/index.html                     |
|                                                    |                                                              |

# Comandos Básicos

| Qué hacer                                                                            | Comando                                                                 |
| ------------------------------------------------------------------------------------ | ----------------------------------------------------------------------- |
| Mostrar la versión de ExifTool                                                       | `exiftool -ver`                                                         |
| Muestra todos los metadatos EXIF de la imagen                                        | `exiftool photo.jpg`                                                    |
| Muestra sólo los metadatos EXIF seleccionados                                        | `exiftool -Model -ImageSize photo.jpg`                                  |
| Eliminar etiquetas/metadatos EXIF recursivos                                         | `exiftool -all= -overwrite_original –r <PATH>`                          |
| Remover todos y preservar algunos tags                                               | `exiftool -All= -TagsFromFile @ -ColorSpaceTags -OverWrite_Original –r` |
| Procesar todos los archivos jpg (insensible a mayúsculas y minúsculas)               | `exiftool -Model -ImageSize -ext jpg <PATH>`                            |
| Procesar recursivamente los archivos jpg del directorio y subdirectorio especificado | `exiftool -r -Model -ImageSize -ext jpg <PATH>`                         |

# Buscar

| Qué hacer                         | Comando                                                                                            |
| ---------------------------------- | -------------------------------------------------------------------------------------------------- |
| Buscar imágenes sin metadatos EXIF | `exiftool -p '$filename' -r -if '(not $datetimeoriginal) and $filetype eq "JPEG"' . > nodates.txt` |


# Depuración

Cuando un comando no está funcionando puede lanzarlo en modo 'verbose'; hay 5 niveles diferentes de verbosidad, el nivel 0 significa que no hay verbosidad

| Qué hacer                                              | Comando                                                                                 |
| ------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| 🔥 Extraer toda la información del archivo             | `exiftool -a -G1 -s img.tif`                                                            |
| Extraer absolutamente todos los metadatos de un archivo | `exiftool -ee3 -U -G3:1 -api requestall=3 -api largefilesupport ARCHIVO`                |
| 🔥 Validar -reparar- imagenes                          | `exiftool -validate -warning -error -a test.jpg`                                        |
| 🔥 Validar / repair imagenes recursivo                 | `exiftool -validate -warning -error -a  -ext jpg /Users/mrtn/Desktop/csv2exif/images/*` |

# Exportar metadatos

| Qué hacer                                                                                               | Comando                                                   |
| ------------------------------------------------------------------------------------------------------- | --------------------------------------------------------- |
| Exportar todos los metadatos del archivo especificado a un archivo csv (se incluyen las cabeceras)      | `exiftool -csv photo.jpg > photo.csv`                     |
| Exportar todas las etiquetas VRAE de un archivo a un archivo csv (se incluyen las cabeceras) | `exiftool -csv -xmp-vrae:all photo.jpg > photo.csv`       |
| 🔥 Exportar todos los metadatos de todos los archivos jpg a un archivo csv (se incluyen las cabeceras)     | `exiftool -csv -ext jpg /home/user/photo/ > file.csv` |


# Renombrar archivos

| Qué hacer                                                                                            | Comando                                                                   |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| Renombrar utilizando una cadena fija y la misma extensión de archivo que el original                 | `exiftool "-FileName<HELLOWORLD.%e" photo.jpg`                            |
| Renombrar utilizando una cadena fija y la misma extensión de archivo en *minúsculas* que el original | `exiftool "-FileName<HELLOWORLD.%le" photo.jpg`                           |
| Cambiar el nombre en función de la fecha                                                             | `exiftool "-FileName<DateTimeOriginal" -d "%Y%m%dT%H%M%S.%%le" photo.jpg` |
| Evitar que se escriban caracteres ilegales en el nombre del archivo (resultados imprevisibles)       | `exiftool '-filename<${make;}.%le' -d "%Y%m%dT%H%M%S" photo.jpg`          |
| Cambiar el nombre de los archivos sólo desde la cámara Canon                                         | `exiftool '-filename<CANON.%le' -if '$make eq "Canon"' photo.jpg`         |
| Añade 1 hora al valor de DateTimeOriginal                                                            | `exiftool "-DateTimeOriginal+=0:0:0 1:0:0" photo.jpg`                     |

# Varios
| Qué hacer                                                                                       | Comando                                                                                                        |
| ----------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Escribir XMP en TIF                                                                             | `exiftool -tagsfromfile CCA-LAN-02-028.xmp -xmp CCA-LAN-02-028.tif`                                            |
| Extraer XMP                                                                                     | `exiftool -xmp -b FILE.tif > FILE.xmp`                                                                         |
| Crear los XMP de todos los files                                                                | `exiftool -ext TIF -o %d%f.xmp -r /Users/user/workflow`                                                        |
| Escribir XMP > JPG en una carpeta                                                               | `exiftool -tagsfromfile %d%f.xmp -all:all DIR`                                                                 |
| Crear archivos XMP sidecar para todos los archivos con extensión EXT en un árbol de directorios | `exiftool -ext TIF -o %d%f.xmp -r /User/xxx/workflow`                                                          |
| Escribir varias etiquetas en TIF                                                                      | `exiftool -creator=Creator -title=This title -description=This description -copyright = "Copy" 1.tif`          |
| Escribir XMP:ISADG en CSV                                                                       | `exiftool -csv -xmp-isadg:all *.tif > log.csv`                                                                 |
| Etiquetas a CSV                                                                                 | `exiftool -csv -creator -title -copyright -Photoshop:CopyrightFlag -CaptionWriter file.tif > log.csv`          |
| Listar grupo XMP:ISADG                                                                          | `exiftool -xmp-isadg:all`                                                                                      |
| Listar grupo XMP:VRAE                                                                           | `exiftool -xmp-vrae:all`                                                                                       |
| Ver etiquetas específicas de un archivo                                                         | `exiftool -creator -title -description -copyright -Photoshop:CopyrightFlag -CaptionWriter file.tif`            |
| Exportar etiquetas de TIF a CSV                                                                 | `exiftool -csv -creator -title -description -copyright -Photoshop:CopyrightFlag -CaptionWriter*.tif > log.csv` |
| Copiar FILENAME a EXIF                                                                          | `exiftool "-iptc:caption-abstract<filename" *.jpg`                                                             |


## ExifTool FAQ
https://exiftool.org/faq.html
