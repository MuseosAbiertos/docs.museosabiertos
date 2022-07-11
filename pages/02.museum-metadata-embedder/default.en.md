---
title: 'Museum Metadata Embedder EN'
hide_hypothesis: false
menu: 'Museum Metadata Embedder'
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
published: true
media_order: 'Logo Banco Hipotecario.jpg,Logo Techniques.jpg,Logo Mecenazgo 2021 negro ch.png,DO_Logo_Horizontal_Blue.png'
metadata:
    'metadata, exiftool, vra core, dublin core, embedder': ''
---

![mme-logo-300](mme-logo-300.jpg "mme-logo-300")

[[ver la versión en español]](https://docs.museosabiertos.org/es/museum-metadata-embedder)

Embed (write) metadata - [Dublin Core](https://dublincore.org/specifications/dublin-core/), [VRA Core](https://core.vraweb.org/), [XMP](https://www.adobe.com/products/xmp.html), [ISAD(G)](https://www.ica.org/sites/default/files/CBPS_2000_Guidelines_ISAD(G)_Second-edition_EN.pdf), [IPTC](https://iptc.org/standards/photo-metadata/), [EXIF](https://docs.fileformat.com/image/exif/) and more - into [all types of images](https://exiftool.org/#supported) and PDF files from a normalized CSV.

**MME** is a Python 3 command line application, which uses [ExifTool](https://exiftool.org/) (by Phil Harvey) and also has a graphical interface, runnable on Linux, MacOS and Windows.

## Use
<code>python mme.py CSV_PATH IMAGES_PATH</code>
Positional arguments: CSV_PATH path to the CSV file to be processed. JPGS_PATH path to the JPG files.
Example: <code> python3 mme.py csv/test.csv images/</code>

### Opciones
-h, --help mostrar este mensaje de ayuda y salir

--row-progress-notify ROW_PROGRESS_NOTIFY, -r ROW_PROGRESS_NOTIFY
el número de filas entre las notificaciones de progreso. 100 por defecto

--notify-broken-keys NOTIFY_BROKEN_KEYS, -n NOTIFY_BROKEN_KEYS
Notificar sobre claves rotas/faltantes en el CSV. Falso por defecto.

--max-depth MAX_DEPTH, -m MAX_DEPTH
Profundidad máxima de las subcarpetas para buscar JPGS. 3 por defecto

### GMME (Interfaz gráfica)
'gmme' es la versión gráfica de mme.py. Es un script de python3 (solamente). No acepta argumentos.

Uso:
<code>python3 gmme.py & </code>

### Archivos del repositorio
| Path                              | Descripción                                                       |
| :-------------------------------- | :---------------------------------------------------------------- |
| csv/                               | Carpeta sugerida para alojar los archivos CSV                     |
| csv/test.csv                      | Archivo CSV de prueba para la primera ejecución y test            |
| exiftool/                          | Ejecutable exiftool                                               |
| data/exiftool_configs/             | Archivos de configuración para ExifTool                           |
| data/notion_maps_txts/             | Carpeta interna de trabajo -no es obligatoria-                    |
| data/maps.json                    | Mapa de relacion entre cabeceras del CSV y las etiquetas ExifTool |
| images/                            | Archivos de prueba para la primera ejecución y test               |
| images/vrae_exiftool_example.tiff | Archivo de ejemplo VRA Core                                       |
|                                   |                                                                   |

### Configuración personalizada
**MME** utiliza un mapa JSON para mapear el _"Nombre de pantalla" (Encabezado de la columna CSV) <-> "Nombre de etiqueta"_, para cada uno de los estándares. El archivo debe encontrarse dentro del directorio 'data', en un archivo JSON llamado 'maps.json'.
Este archivo se puede editar para agregar nuevas etiquetas.

Sólo es necesario editar las cabeceras (primera fila de la hoja de cálculo) para que se ajusten al esquema. Esto puede implicar la división de algunas columnas para ajustarse al esquema, la adición de columnas y otras ediciones. Todo esto es probablemente más fácil, más rápido y más preciso de hacer en una hoja de cálculo.

### Requerimientos del sistema
|          |                                             |
| -------- | ------------------------------------------- |
| Perl     | https://www.activestate.com/products/perl/  |
| Python 3 | https://www.python.org/downloads/ |

## Descarga
https://github.com/MuseosAbiertos/Museum-Metadata-Embedder

## Agradecimientos
* **Harry van der Wolf**, por su inestimable colaboración y la creación de la interfaz gráfica (GUI) y sus ejecutables multiplataforma
* **Greg Reser**, por todo su apoyo y colaboración en esta implementación de VRA Core
* **Phil Harvey**, por su maravilloso ExifTool, que pronto cumplirá 30 años!
* **Jairo Serrano**, amigo y estimado SysOp que logra que todo funcione sin romperse y lo repara cuando se rompe
* **Sebastián Gersbach**, por el diseño del logo y el paquete de iconos
* **Centro de Documentación de Bienes Patrimoniales de Chile** [https://www.aatespanol.cl/]

## Sponsors/Mecenas
Esta aplicación ha sido posible gracias al programa de Mecenazgo Cultural de la Ciudad Autónoma de Buenos Aires, Argentina

![Logo%20Mecenazgo%202021%20negro%20ch](Logo%20Mecenazgo%202021%20negro%20ch.png "Logo%20Mecenazgo%202021%20negro%20ch")

y especialmente a nuestros mecenas

Banco Hipotecario https://www.hipotecario.com.ar
Techniques & Supplies https://www.techniques.com.ar
Digital Ocean https://www.digitalocean.com

![Logo%20Banco%20Hipotecario](Logo%20Banco%20Hipotecario.jpg "Logo%20Banco%20Hipotecario")
![Logo%20Techniques](Logo%20Techniques.jpg "Logo%20Techniques")
![DO_Logo_Horizontal_Blue](DO_Logo_Horizontal_Blue.png "DO_Logo_Horizontal_Blue")