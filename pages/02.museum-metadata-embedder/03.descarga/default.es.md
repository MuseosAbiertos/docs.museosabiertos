---
title: Descarga
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
---

## GitHub
https://github.com/MuseosAbiertos/Museum-Metadata-Embedder

### Instrucciones 
* Clona el repositorio o descarga el .zip en la carpeta en la que desees trabajar; es correcto nombrarla 'mme' 
  * en MacOS, puedes usar esta ruta: <code>/Users/<user\>/mme</code> 
  * en Windows, puedes usar esta ruta: <code>C:\Users\<user\>\mme</code> 
* Debes conservar la estructura de archivos dentro del archivo .zip que descargues 
* Los archivos de imágenes a tratar debes ubicarlos dentro de la carpetas 'images', dentro de 'mme' 
  

### Requerimientos del sistema
    
|          |                                             |
| -------- | ------------------------------------------- |
| Perl     | https://www.activestate.com/products/perl/  |
| Python 3 | https://www.python.org/downloads/ |

    
### Configuración personalizada
**MME** utiliza un mapa JSON para mapear el _"Nombre de pantalla" (Encabezado de la columna CSV) <-> "Nombre de etiqueta"_, para cada uno de los estándares. El archivo debe encontrarse dentro del directorio 'data', en un archivo JSON llamado 'maps.json'.
Este archivo se puede editar para agregar nuevas etiquetas.

Sólo es necesario editar las cabeceras (primera fila de la hoja de cálculo) para que se ajusten al esquema. Esto puede implicar la división de algunas columnas para ajustarse al esquema, la adición de columnas y otras ediciones. Todo esto es probablemente más fácil, más rápido y más preciso de hacer en una hoja de cálculo.

### Archivos del repositorio
| Path                              | Descripción                                                       |
| :-------------------------------- | :---------------------------------------------------------------- |
| csv/                               | Carpeta sugerida para alojar los archivos CSV                     |
| csv/test.csv                      | Archivo CSV de prueba para la primera ejecución y test            |
| exiftool/                          | Ejecutable ExifTool                                               |
| data/exiftool_configs/             | Archivos de configuración para ExifTool                           |
| data/notion_maps_txts/             | Carpeta interna de trabajo -no es obligatoria-                    |
| data/maps.json                    | Mapa de relación entre cabeceras del CSV y las etiquetas ExifTool |
| images/                            | Archivos de prueba para la primera ejecución y test               |
| images/vrae_exiftool_example.tiff | Archivo de ejemplo VRA Core                                       |
|                                   |                                                                   |

