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

| Título                                                                  | URL                                                              |
| -------------------------------------------------------------------- | ---------------------------------------------------------------- |
| ExifTool Command-Line Examples                                       | https://exiftool.org/examples.html                               |
| Metadata Sidecar Files                                               | https://exiftool.org/metafiles.html                              |
| ExifTool FAQ                                                         | https://exiftool.org/faq.html                                    |
| ExifTool-Batch-Processor                                             | https://github.com/CarletonArchives/ExifTool-Batch-Processor     |
| Here is a complete list of metadata TAGS (depending on file format): | http://www.sno.phy.queensu.ca/~phil/exiftool/TagNames/index.html |
|                                                                      |                                                                  |

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
|                                                                               |                                                                         |

# Buscar

| what to do                         | Command                                                                                            |
| ---------------------------------- | -------------------------------------------------------------------------------------------------- |
| Buscar imágenes sin metadatos EXIF | `exiftool -p '$filename' -r -if '(not $datetimeoriginal) and $filetype eq "JPEG"' . > nodates.txt` |
| verificar                          | `cat nodates.txt \| wc -l`                                                                         |


# Debugging

When a command is not working you can launch it in verbose mode, there are 5 different levels of verbosity, level 0 means no verbosity

## For more: <https://exiftool.org/Shift.html>
|                                           |                                                                                         |
| ----------------------------------------- | --------------------------------------------------------------------------------------- |
| 🔥 Ver dónde se almacena los metadatos   | `exiftool -a -G1 -s img.tif`                                                            |
| Extraer todos los metadatos de un archivo | `exiftool -ee3 -U -G3:1 -api requestall=3 -api largefilesupport ARCHIVO`                |
| 🔥 Validar -reparar- imagenes            | `exiftool -validate -warning -error -a test.jpg`                                        |
| 🔥 Validar / repair imagenes recursivo   | `exiftool -validate -warning -error -a  -ext jpg /Users/mrtn/Desktop/csv2exif/images/*` |
|                                           |                                                                                         |

# Metadata Export

|                                                                              |                                                     |
| ---------------------------------------------------------------------------- | --------------------------------------------------- |
| Export all metadata of specified file into a csv file (headers are included) | `exiftool -csv photo.jpg > photo.csv`               |
| Export all VRAE tag of specified file into a csv file (headers are included) | `exiftool -csv -xmp-vrae:all photo.jpg > photo.csv` |
|                                                                              |                                                     |
|                                                                              |                                                     |
|                                                                              |                                                     |






### Export all metadata of all jpg file into a csv file (headers are included)

```s
exiftool -csv -ext jpg /home/ebah/photo/
```

### Export selected metadata of all jpg file into a csv file (headers are included)

```s
exiftool -Make -Model -DateTimeOriginal -csv -ext jpg /home/ebah/photo/
```



# File renaming

### Rename using fixed string and same file extension as original

```s
exiftool "-FileName<HELLOWORLD.%e" photo.JPG
```

### Rename using fixed string and same *lowercase* file extension as original

```s
exiftool "-FileName<HELLOWORLD.%le" photo.jpg
```

### Rename based on date (for the format see: )

```s
exiftool "-FileName<DateTimeOriginal" -d "%Y%m%dT%H%M%S.%%le" photo.jpg
```

### Prevent illegal characters to be written in filename (unpredictable results)

```s
exiftool '-filename<${make;}.%le' -d "%Y%m%dT%H%M%S" photo.jpg
```

### Replace spaces in tag string

```s
exiftool -Make photo.jpg
```

```s
exiftool '-filename<${make;tr/ /_/;s/__+/_/g}.%le' photo.jpg
```

### Composite rename: DateTimeOriginal + Make tags
```s
exiftool '-filename<${DateTimeOriginal}_${make;tr/ /_/;s/__+/_/g}.%le' -d "%Y%m%dT%H%M%S" photo.jpg
```

### Add a counter for duplicate images
```s
exiftool '-FileName<${DateTimeOriginal}_${Model;tr/ /_/;s/__+/_/g}.%e' -d "%Y%m%dT%H%M%S%%-.c" 20130914T074335_Canon.jpg
```

### Contitional expression

If condition matches then the file is processed otherwise skipped exiftool -shutterspeed -if '$make eq "Canon"'

### Rename files only from Canon Camera
```s
exiftool '-filename<CANON.%le' -if '$make eq "Canon"' photo.jpg
```

### Time shift

Time shift is very handy when camera's clock is misaligned from real time (say because you are abroad on holiday and forgot to adjust camera's clock)

For more: <http://www.sno.phy.queensu.ca/~phil/exiftool/Shift.html>

### Add 1 hour to the DateTimeOriginal's value
```s
exiftool "-DateTimeOriginal+=0:0:0 1:0:0" photo.jpg
```

# VARIOS

### Extraer XMP
```s
exiftool -xmp -b FILE.tif > FILE.xmp
```

### Write XMP > JPG en un folder
```s
exiftool -tagsfromfile %d%f.xmp -all:all DIR
```

### Create XMP sidecar files for all files with extension EXT in a directory tree
```s
exiftool -ext TIF -o %d%f.xmp -r /User/xxx/workflow
```

### Write multiple tags in TIF
```s
exiftool -creator=BIZIOLI\ HOS. -title=AR-CIFHA-CDV-PAN-001 -description=PAREJA\ TOMADA\ DE\ LA\ MANO\ -copyright = "2020 CIFHA" 1.tif
```

### Escribir XMP en TIF
```s
exiftool -tagsfromfile CCA-LAN-02-028.xmp -xmp CCA-LAN-02-028.tif
```
### Crear los XMP de todos los files
```s
exiftool -ext TIF -o %d%f.xmp -r /Volumes/GoogleDrive/Mi\ unidad/_Clientes/CIFHA/workflow
```

### Escribir XMP:ISADG en CSV
```s
exiftool -csv -xmp-isadg:all *.tif > log.csv
```

### Listar grupo XMP:ISADG - XMP:VRAE
```s
exiftool -xmp-isadg:all
```

```s
exiftool -xmp-vrae:all
```

### Ver etiquetas específicas de un archivo
```s
exiftool -creator -title -description -copyright -Photoshop:CopyrightFlag -CaptionWriter AR-CIFHA-CDV-AS-1-001.tif
```

## Etiquetas a CSV
```s
exiftool -csv -creator -title -description -copyright -Photoshop:CopyrightFlag -CaptionWriter AR-CIFHA-CDV-AS-1-001.tif > log.csv
```

## Ver etiquetas de *TIF a CSV
```s
exiftool -csv -creator -title -description -copyright -Photoshop:CopyrightFlag -CaptionWriter*.tif > log.csv
```

## Copiar FILENAME a EXIF
```s
exiftool "-iptc:caption-abstract<filename" *.jpg
```
