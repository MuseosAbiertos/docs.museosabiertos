---
title: 'Editor de metadatos para la descripción archivística'
menu: 'Editor de metadatos GLAM'
media_order: '1.png,2.png,3.png,logo-mecenazgo.jpg,logo-editor.png,MA-sample-id-2498680.jpg,logo-mecenazgo-web.jpg,emm-button-large.jpg'
sitemap:
    ignore: false
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
hide_hypothesis: false
taxonomy:
    category:
        - docs
    tag:
        - metadata
page-toc:
    active: true
external_links:
    no_follow: false
---

![Editor de metadatos para la descripción archivística](logo-editor.png?resize=400,200) 

Este editor multiplataforma es una interfaz gráfica para la edición de metadatos de registros de colecciones con las normas [EXIF](https://docs.fileformat.com/image/exif/), [IPTC](https://iptc.org/standards/photo-metadata/), [XMP](https://www.adobe.com/products/xmp.html), GPS y extendido a [Dublin Core](https://dublincore.org/specifications/dublin-core/) y [ISAD(G) 2000](https://www.ica.org/sites/default/files/CBPS_2000_Guidelines_ISAD%28G%29_Second-edition_EN.pdf).


!!!  Web de Proyecto:  [https://museosabiertos.org/proyectos/editor-metadatos-glam](https://museosabiertos.org/proyectos/editor-metadatos-glam)


## Objetivo
Esta herramienta de edición de metadatos -de unidades documentales- ayuda a implementar los normas internacionales -dentro del modelo conceptual OAIS [http://www.oais.info].- en una única interfase, donde los metadatos se 'embeben' en los documentos, evitando así la dispersión de soluciones y colaborando con la estandarización y aceleración de los procesos de registro de colecciones.

Es especialmente útil para pequeñas organizaciones sin sistemas de administración de activos digitales y organizaciones grandes con muchos contribuyentes individuales. Los metadatos pueden luego transferirse al sistema de gestión de activos digitales.

También ayuda a incorporar a más personas en los flujos de trabajo, como los fotógrafos independientes, que de otro modo no tendrían acceso al sistema de gestión de activos digitales de una organización.

Este proyecto -libre y abierto- está orientado a todas las personas e instituciones que resguardan documentos y archivos patrimoniales, que procuren implementar las normas internacionales.

En este video, Greg Reser explica con más detalles este concepto: [Greg Reser (VRA) About Cultural Heritage Metadata](https://youtu.be/qoIilcir88Q) 


## Características
* Software de código abierto con licencia GNU
* Software multiplataforma (puede ser ejecutado en Windows XP, 7, 10, MacOS, Linux y Raspberry pi)
* Edita los metadatos y los 'guarda' dentro del archivo sin modificar la imagen (ej.: JPG, TIF, PDF) conservando su contexto al 'viajar' a través de aplicaciones, dispositivos y bases de datos.
* Edita metadatos según las normas internacionales EXIF, IPTC, Dublin Core, ISAD(G), VRA Core y muchos otros
* No es destructivo (no altera las imágenes)
* Reduce significativamente las tareas de registro
* Aunque lo permite, hace obsoleto el uso de hojas de cálculo independientes para el registros de colecciones
* Diseñado para adaptarse a un flujo de trabajo para auditoría de datos con [Open Refine](https://openrefine.org/)
* Exporta los metadatos a un archivo tabulado CSV para facilitar la ingestión en aplicaciones, como [AtoM](https://accesstomemory.org/), [Archivematica](https://www.archivematica.org/), [DSpace](https://duraspace.org/dspace/), [Fedora Commons](https://duraspace.org/fedora/) o [RODA](https://roda-community.org/).

## Tags
Embedded Metadata, Access to Digital Image Files, Metadata editor, Heritage


## Software
Aplicación Java/Swing que funciona como frontend gráfico (GUI) para ExifTool. La UI está diseñada con GUI Designer from IntelliJ IDEA. Licencia abierta, GNU General Public License.

Este desarrollo se apoya en estándares y software de código abierto de terceras partes

* [EXIF](https://docs.fileformat.com/image/exif/) es un estándar creado en el año 1995 para las especificaciones de formatos de imagen y sonido utilizados principalmente por cámaras digitales y escáneres, creado por la [_Asociación de la industria de cámaras de Japón_](https://en.wikipedia.org/wiki/Japan_Electronic_Industries_Development_Association) y hoy cuenta con una total aceptación y soporte.
* Viendo las limitaciones de EXIF, en el año 2001 Abobe System creó [XMP](https://es.wikipedia.org/wiki/XMP), un modelo de datos extensibles, con el fin de poder registrar metadatos, como [Dublin Core](https://es.wikipedia.org/wiki/Dublin_Core), pero con el objetivo de aplicarlo a los archivos PDF. Hoy en día puede ser utilizado en prácticamente cualquier formato gráfico y es un framework extensible a otras aplicaciones.
* [ExifTool by Phil Harvey](https://exiftool.org/) es una biblioteca de Perl multiplataforma, creada en el año 2003, más una aplicación de línea de comandos para leer y editar metainformación en una amplia variedad de archivos, que es usada por muchas aplicaciones de código abierto que deban escribir metadatos.
* [ISAD(G) XML Schema](https://gist.github.com/anarchivist/826364)* 

### Dependencias
* [JRE (Java Runtime Environment)](https://adoptopenjdk.net/releases.html)
* [ExifTool by Phil Harvey](https://exiftool.org/) 

### Documentación
* [Planilla de documentación de estándares](https://docs.google.com/spreadsheets/d/1lgJ7bgF3YWYn6RpQe6xPpc2lPtMmsKxhdoTDaipEz4M/edit#gid=1070734913)
* [Issues](https://app.asana.com/0/1199531865244213/board)

## Roadmap
* Importa un CSV o XML y guarda los metadatos en archivos (ej.: JPG, TIFF, PDF) 
* Lectura/escritura de metadatos en un archivo XML externo (sidecar)
* Soporte para [VRA Core 4](https://core.vraweb.org/)
* Integración con los vocabularios Getty [AAT en Español](https://www.aatespanol.cl/), [TGN](http://www.getty.edu/research/tools/vocabularies/tgn/index.html) y [ULAN](https://www.getty.edu/research/tools/vocabularies/ulan/) 
* Integracíon con [WikiData](https://www.wikidata.org/)
* Soporte para [EAD 2002](https://www.loc.gov/ead/index.html)
* Soporte para [EAD3 (2015)](https://www.loc.gov/ead/index.html)
* Soporte para [DACS](https://github.com/saa-ts-dacs/dacs)
* Soporte para [SPECTRUM](https://collectionstrust.org.uk/spectrum/)
Soporte para [ISAAR (CPF) 2ªed](https://www.ica.org/es/isaar-cpf-norma-internacional-sobre-los-registros-de-autoridad-de-archivos-relativos-a-instituciones)
* Guarda un histórico de ediciones

## Mockups

![](1.png)
![](2.png)
![](3.png)

## Agradecimientos
* A [Jairo Enrique Serrano Castañeda](https://scholar.google.com/citations?user=rW2nV5cAAAAJ&hl), amigo y estimado DevOps, por su oído siempre atento y dedicación en las incidencias
* A [María Laura Caliusco](https://bit.ly/3nwKVGN), por su pasión académica y por haber aceptado la propuesta de 'descripción patrimonial' y también como colaborador en el paper final "[Hacia un modelo semántico para la descripción del patrimonio](http://dx.doi.org/10.5281/zenodo.3338005)" 
* A Harry van der Wolf, desarrollador principal de [jExifToolGUI](https://github.com/hvdwolf/jExifToolGUI), por permitirme 'montarme' sobre su proyecto sin tener que crear mi propio fork y aceptar que su proyecto acepte otros espacios de nombres
* A [Greg Reser](mailto:greser@ucsd.edu), Visual Resources Association. Presidente del [subcomité de metadatos integrados de VRA](http://metadatadeluxe.pbworks.com/w/page/20792294/VRA%20Embedded%20Metadata%20Subcommittee), y desarrollador de las herramientas [VRA para Adobe Bridge](http://metadatadeluxe.pbworks.com/w/page/108523528/VRA%20Bridge%20Metadata%20Tools). 


## Proyectos similares
* [jExifToolGUI](https://github.com/hvdwolf/jExifToolGUI)
* [Custom Metadata Panel for Bridge](https://github.com/adobe-dmeservices/custom-metadata)
* [IPTC Releases Cultural Heritage Panel for Metadata Management](https://iptc.org/news/culturalheritagepanel/)
* [Tropy](https://tropy.org/)

## Proyectos relacionados
* [Metadata Extraction Tool](http://meta-extractor.sourceforge.net/)
* [JHOVE](http://jhove.openpreservation.org/)


[![emm-button-large](emm-button-large.jpg "emm-button-large")
](http://www.embeddedmetadata.org/goto?supportsemm)

---

[![](logo-mecenazgo-web.jpg)](https://www.buenosaires.gob.ar/mecenazgo)

Expediente: 19029867

## Los contribuyentes pueden ser mecenas de la cultura
Quienes tributen el impuesto sobre los Ingresos Brutos pueden destinar parte del pago de los mismos para financiar proyectos culturales.
https://www.buenosaires.gob.ar/cultura/mecenazgo/informacion-para-contribuyentes

