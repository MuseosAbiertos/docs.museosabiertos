---
title: 'Editor de metadatos para la descripción archivística'
menu: 'Editor de metadatos GLAM'
media_order: '1.png,2.png,3.png,DemoImage_ISADG-XMP-Metadata.png'
---

Este editor multiplataforma es una herramienta gráfica para la edición de metadatos de registros de colecciones con las normas [Dublin Core](https://dublincore.org/specifications/dublin-core/), [ISAD(G) 2000](https://www.ica.org/sites/default/files/CBPS_2000_Guidelines_ISAD%28G%29_Second-edition_EN.pdf), [EAD 2002](https://www.loc.gov/ead/index.html)

## Contexto en Argentina
La Secretaría de Cultura de la Nación (Argentina), en su resolución 1070, [https://senip.cultura.gob.ar/wp-content/uploads/2016/09/Res-1070.pdf](https://senip.cultura.gob.ar/wp-content/uploads/2016/09/Res-1070.pdf) instruye a los organismos dependientes adoptar una ficha de registro de inventario de unidades documentales de acuerdo a la norma ISAD(G); pero no documenta su adaptación local de la norma, como tampoco regula ni sugiere como implementarla. Muchas otras instituciones o archivos utilizan estas normas y carecen de herramientas apropiadas para el registro de documentos.

## Objetivos
Esta herramienta busca ayudar, tanto al archivista iniciado como al experimentado, a implementar las normas en una única interfase, evitando la dispersión de soluciones y colaborando con la estandarización de los procesos y la aplicación de las normas.

* Gran parte de los archivos y museos usan planillas de cálculo para guardar los metadatos (ISAD-G, EAD, DC, METS...) de los documentos digitales

## Características
* Software multiplataforma (puede ser ejecutado en Windows, OS X y Linux)
* Edita los metadatos y los 'guarda' dentro de un archivo (ej.: JPG, TIF, PDF) conservando su contexto al viajar a través de software, dispositivos y bases de datos.
* Edita metadatos según las normas internacionales Dublin Core, ISAD(G) 2000, EAD 2002
* No es destructivo (no altera las imágenes)
* Reduce significativamente las tareas de registro
* Hace obsoleto el uso de hojas de cálculo independientes para el registros de colecciones
* Adaptado a un flujo de trabajo para auditoría de datos con [Open Refine](https://openrefine.org/)
* Exporta los metadatos a un archivo tabulado CSV
* Exporta los metadatos a un archivo XML para la ingestión en plataformas, como [AtoM](https://accesstomemory.org/), [Archivematica](https://www.archivematica.org/), [DSpace](https://duraspace.org/dspace/), [Fedora Commons](https://duraspace.org/fedora/) o [RODA](https://roda-community.org/).

## Roadmap
* Importa un CSV o XML y guarda los metadatos en archivos (ej.: JPG, TIF, PDF) 
* Lectura/escritura de metadatos en un archivo XML externo (sidecar)
* Guarda un histórico de ediciones
* Soporte para EAD3 (2015)

## Software
Aplicación Java/Swing que funciona como frontend gráfico (GUI) para ExifTool. La UI está diseñada con GUI Designer from IntelliJ IDEA. Licencia abierta, GNU General Public License.

Este desarrollo se apoya en estándares y software de código abierto de terceras partes

* [EXIF](https://docs.fileformat.com/image/exif/) es un estándar creado en el año 1995 para las especificaciones de formatos de imagen y sonido utilizados principalmente por cámaras digitales y escáneres, creado por la [_Asociación de la industria de cámaras de Japón_](https://en.wikipedia.org/wiki/Japan_Electronic_Industries_Development_Association) y hoy cuenta con una total aceptación y soporte.
* Viendo las limitaciones de EXIF, en el año 2001 Abobe System creó [XMP](https://es.wikipedia.org/wiki/XMP), un modelo de datos extensibles, con el fin de poder registrar metadatos, como [Dublin Core](https://es.wikipedia.org/wiki/Dublin_Core), pero con el objetivo de aplicarlo a loas archivos PDF. Hoy en día puede ser utilizado en prácticamente cualquier formato gráfico y es un framework extensible a otras aplicaciones.
* [ExifTool by Phil Harvey](https://exiftool.org/) es una biblioteca de Perl (independiente de la plataforma) más una aplicación de línea de comandos para leer, escribir y editar metainformación en una amplia variedad de archivos, que es usada por muchas aplicaciones de código abierto que deban escribir metadatos.
* [ISAD(G) XML Schema](https://gist.github.com/anarchivist/826364)
* 

### Dependencias
* [JRE (Java Runtime Environment)](https://adoptopenjdk.net/releases.html)
* [ExifTool by Phil Harvey](https://exiftool.org/) 

### Ejemplo de archivo con ISAD-G incrustado en XMP

1. Descarga el archivo: [https://docs.museosabiertos.org/editor-de-metadatos/DemoImage_ISADG-XMP-Metadata.png](https://docs.museosabiertos.org/editor-de-metadatos/DemoImage_ISADG-XMP-Metadata.png)
2. Abre una ventana de terminal en su carpeta y ejecuta:
<code>exiftool -xmp-isadg:all DemoImage_ISADG-XMP-Metadata.png</code>

## Mockups

![](1.png)
![](2.png)
![](3.png)

<note>
## Integración del workflow con Drupal

* [https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3964704/](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3964704/)
* [https://www.drupal.org/project/exif](https://www.drupal.org/project/exif)

</note>