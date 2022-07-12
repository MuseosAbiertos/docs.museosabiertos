---
title: 'Museum Metadata Embedder'
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

### Options
-h (--help)
    Show this help message and exit.

-r ROW_PROGRESS_NOTIFY (--row-progress-notify ROW_PROGRESS_NOTIFY)
    The number of rows between progress notifications. 100 by default.

-n NOTIFY_BROKEN_KEYS (--notify-broken-keys NOTIFY_BROKEN_KEYS)
    Notify about broken/missing keys in the CSV. False by default.

-m MAX_DEPTH (--max-depth MAX_DEPTH)
    Maximum depth of subfolders to search for JPGS. 3 by default.

### GMME (GUI)
gmme' is the graphical version of mme.py. It is a python3 script (only). It does not accept arguments.

Use:
<code>python3 gmme.py & </code>

### Repository files
| Path                              | Description                                                       |
| :-------------------------------- | :---------------------------------------------------------------- |
| csv/                               | Suggested folder for hosting CSV files                     |
| csv/test.csv                      | CSV test file for the first run and test            |
| exiftool/                          | Exiftool executable                                               |
| data/exiftool_configs/             | Configuration files for ExifTool                           |
| data/notion_maps_txts/             | Internal work folder -not mandatory-.                    |
| data/maps.json                    | Relationship map between CSV headers and ExifTool tags |
| images/                            | Test files for first run and test               |
| images/vrae_exiftool_example.tiff | VRA Core sample file                                       |
|                                   |                                                                   |

### Custom configuration
**MME** uses a JSON map to map the _"Display Name" (CSV Column Header) <-> "Label Name"_, for each of the standards. The file must be located inside the 'data' directory, in a JSON file named 'maps.json'.
This file can be edited to add new tags.

Only the headers (first row of the spreadsheet) needs to be edited to fit the schema. This may involve splitting some columns to fit the schema, adding columns, and other edits. All of this is probably easier, faster and more accurate to do in a spreadsheet.

### System requirements
|          |                                             |
| -------- | ------------------------------------------- |
| Perl     | https://www.activestate.com/products/perl/  |
| Python 3 | https://www.python.org/downloads/ |

## Download
https://github.com/MuseosAbiertos/Museum-Metadata-Embedder

## Acknowledgments
* Harry van der Wolf**, for his invaluable collaboration and creation of the graphical user interface (GUI) and its cross-platform executables
** **Greg Reser**, for all his support and collaboration on this VRA Core implementation
** **Phil Harvey**, for his marvelous ExifTool, soon to be 30 years old!
** **Jairo Serrano**, friend and estimated SysOp who makes everything work without breaking and fixes it when it does break
** **Sebastián Gersbach**, for the logo design and the icon package
* **Centro de Documentación de Bienes Patrimoniales de Chile** [https://www.aatespanol.cl/]

## Patrons
This application has been made possible thanks to the Cultural Patronage program of the Autonomous City of Buenos Aires, Argentina.

![Logo%20Mecenazgo%202021%20negro%20ch](Logo%20Mecenazgo%202021%20negro%20ch.png "Logo%20Mecenazgo%202021%20negro%20ch")

and especially to our sponsors

Banco Hipotecario https://www.hipotecario.com.ar
Techniques & Supplies https://www.techniques.com.ar
Digital Ocean https://www.digitalocean.com

![Logo%20Banco%20Hipotecario](Logo%20Banco%20Hipotecario.jpg "Logo%20Banco%20Hipotecario")
![Logo%20Techniques](Logo%20Techniques.jpg "Logo%20Techniques")
![DO_Logo_Horizontal_Blue](DO_Logo_Horizontal_Blue.png "DO_Logo_Horizontal_Blue")