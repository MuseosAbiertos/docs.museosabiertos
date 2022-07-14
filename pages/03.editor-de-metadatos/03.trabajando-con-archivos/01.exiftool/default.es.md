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

**[ExifTool by Phil Harvey](https://exiftool.org/)**
ExifTool es una biblioteca de Perl independiente de la plataforma más una aplicación de línea de comandos para leer, escribir y editar metainformación en una amplia variedad de archivos.

# Referencias

| What to do                                                           | Command                                                          |
| -------------------------------------------------------------------- | ---------------------------------------------------------------- |
| ExifTool Command-Line Examples                                       | https://exiftool.org/examples.html                               |
| Metadata Sidecar Files                                               | https://exiftool.org/metafiles.html                              |
| ExifTool FAQ                                                         | https://exiftool.org/faq.html                                    |
| ExifTool-Batch-Processor                                             | https://github.com/CarletonArchives/ExifTool-Batch-Processor     |
| Here is a complete list of metadata TAGS (depending on file format): | http://www.sno.phy.queensu.ca/~phil/exiftool/TagNames/index.html |

# Basic Commands

| What to do                                                                    | Command                                                                 |
| ----------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Show exiftool version                                                         | `exiftool -ver`                                                         |
| Shows all the EXIF metadata of image                                          | `exiftool photo.jpg`                                                    |
| Shows only selected EXIF metadata                                             | `exiftool -Model -ImageSize photo.jpg`                                  |
| Remove EXIF tags/metadata recursivo                                           | `exiftool -all= -overwrite_original –r <PATH>`                          |
| Remover todos y preservar algunos tags                                        | `exiftool -All= -TagsFromFile @ -ColorSpaceTags -OverWrite_Original –r` |
| Process all files of specified file type (case insensitive extension)         | `exiftool -Model -ImageSize -ext jpg <PATH>`                            |
| Recursively process all jpg files under specified directory and sub-directory | `exiftool -r -Model -ImageSize -ext jpg <PATH>`                         |

# Buscar

| What to do                         | Command                                                                                            |
| ---------------------------------- | -------------------------------------------------------------------------------------------------- |
| Buscar imágenes sin metadatos EXIF | `exiftool -p '$filename' -r -if '(not $datetimeoriginal) and $filetype eq "JPEG"' . > nodates.txt` |
| verificar                          | `cat nodates.txt \| wc -l`                                                                         |


# Debugging

When a command is not working you can launch it in verbose mode, there are 5 different levels of verbosity, level 0 means no verbosity

| What to do                                              | Command                                                                                 |
| ------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| 🔥 Extraer toda la información del archivo             | `exiftool -a -G1 -s img.tif`                                                            |
| Extraer absolutamente todos los metadatos de un archivo | `exiftool -ee3 -U -G3:1 -api requestall=3 -api largefilesupport ARCHIVO`                |
| 🔥 Validar -reparar- imagenes                          | `exiftool -validate -warning -error -a test.jpg`                                        |
| 🔥 Validar / repair imagenes recursivo                 | `exiftool -validate -warning -error -a  -ext jpg /Users/mrtn/Desktop/csv2exif/images/*` |

# Metadata Export

| What to do                                                                      | Command                                                                   |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| Export all metadata of specified file into a csv file (headers are included)    | `exiftool -csv photo.jpg > photo.csv`                                     |
| Export all VRAE tag of specified file into a csv file (headers are included)    | `exiftool -csv -xmp-vrae:all photo.jpg > photo.csv`                       |
| Export all metadata of all jpg file into a csv file (headers are included)      | `exiftool -csv -ext jpg /home/ebah/photo/`                                |
| Export selected metadata of all jpg file into a csv file (headers are included) | `exiftool -Make -Model -DateTimeOriginal -csv -ext jpg /home/ebah/photo/` |


# File renaming

| What to do                                                                   | Command                                                                   |
| ---------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| Rename using fixed string and same file extension as original                | `exiftool "-FileName<HELLOWORLD.%e" photo.jpg`                            |
| Rename using fixed string and same *lowercase* file extension as original    | `exiftool "-FileName<HELLOWORLD.%le" photo.jpg`                           |
| Rename based on date                                                         | `exiftool "-FileName<DateTimeOriginal" -d "%Y%m%dT%H%M%S.%%le" photo.jpg` |
| Prevent illegal characters to be written in filename (unpredictable results) | `exiftool '-filename<${make;}.%le' -d "%Y%m%dT%H%M%S" photo.jpg`          |
| Rename files only from Canon Camera                                          | `exiftool '-filename<CANON.%le' -if '$make eq "Canon"' photo.jpg`         |
| Add 1 hour to the DateTimeOriginal's value                                   | `exiftool "-DateTimeOriginal+=0:0:0 1:0:0" photo.jpg`                     |

# Varios
| What to do                                                                    | Command                                                                                                        |
| ----------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Escribir XMP en TIF                                                           | `exiftool -tagsfromfile CCA-LAN-02-028.xmp -xmp CCA-LAN-02-028.tif`                                            |
| Extraer XMP                                                                   | `exiftool -xmp -b FILE.tif > FILE.xmp`                                                                         |
| Crear los XMP de todos los files                                              | `exiftool -ext TIF -o %d%f.xmp -r /Users/user/workflow`                                                        |
| Write XMP > JPG en un folder                                                  | `exiftool -tagsfromfile %d%f.xmp -all:all DIR`                                                                 |
| Create XMP sidecar files for all files with extension EXT in a directory tree | `exiftool -ext TIF -o %d%f.xmp -r /User/xxx/workflow`                                                          |
| Write multiple tags in TIF                                                    | `exiftool -creator=Creator -title=This title -description=This description -copyright = "Copy" 1.tif`          |
| Escribir XMP:ISADG en CSV                                                     | `exiftool -csv -xmp-isadg:all *.tif > log.csv`                                                                 |
| Etiquetas a CSV                                                               | `exiftool -csv -creator -title -copyright -Photoshop:CopyrightFlag -CaptionWriter file.tif > log.csv`          |
| Listar grupo XMP:ISADG                                                        | `exiftool -xmp-isadg:all`                                                                                      |
| Listar grupo XMP:VRAE                                                         | `exiftool -xmp-vrae:all`                                                                                       |
| Ver etiquetas específicas de un archivo                                       | `exiftool -creator -title -description -copyright -Photoshop:CopyrightFlag -CaptionWriter file.tif`            |
| Exportar etiquetas de TIF a CSV                                               | `exiftool -csv -creator -title -description -copyright -Photoshop:CopyrightFlag -CaptionWriter*.tif > log.csv` |
| Copiar FILENAME a EXIF                                                        | `exiftool "-iptc:caption-abstract<filename" *.jpg`                                                             |


## ExifTool FAQ
https://exiftool.org/faq.html
