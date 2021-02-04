---
title: 'Trabajando con archivos'
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
media_order: MuseosNacioanlesCatalogoOnline.jpg
---

### Herramientas varias para trabajar con archivos de imágenes

**[ExifTool by Phil Harvey](https://exiftool.org/)**
ExifTool es una biblioteca de Perl independiente de la plataforma más una aplicación de línea de comandos para leer, escribir y editar metainformación en una amplia variedad de archivos.

* _Ejemplo para extraer todos los metadatos de una imagen:_ <code>exiftool -a MA-sample-id-2498680.jpg</code>

**[ImageMagick](https://imagemagick.org/)**
ImageMagick es un conjunto de utilidades de código abierto, para mostrar, manipular y convertir imágenes, capaz de leer y escribir más de 200 formatos.

* _Ejemplo para reducir una imagen al 50%:_ <code>magick mogrify -resize 50% rose.jpg</code>
* _Ejemplo para crear una copia reducida en otra carpeta:_ <code>magick mogrify -resize 200x200 -path ch MA-sample-id-2498680.jpg</code>

!!! **Porque usar aplicaciones de línea de comandos?**<br>
!!! Principalmente porque, a diferencia de las aplicaciones gráficas, la línea de comandos consume muy pocos recursos y ejecuta las tareas mucho más rápido. Eso se traduce en productividad a la hora de crear y ejecutar comandos en nuestra máquina o en un servidor remoto.

### Extraer metadatos de un archivo que contiene metadatos ISAD-G 

1. Descarga el archivo: 
*  [MA-sample-id-2498680.jpg](https://docs.museosabiertos.org/editor-de-metadatos/MA-sample-id-2498680.jpg)
2. Abre una ventana de terminal en tu carpeta y ejecuta:
*  <code>exiftool -xmp-isadg:all MA-sample-id-2498680.jpg</code>

A continuación, se imprimirá en la pantalla lo siguiente:

| Etiqueta XPM ISAD(G) | Valor   |
|---|---|
|_Alliedmaterials Existencelocationcopies_    |Digital reproductions of the Christie family Civil War correspondence [...]   |
|_Alliedmaterials Existencelocationoriginals_ |Following sampling in 1985, the remaining case files were destroyed. [...]   |
|_Alliedmaterials Publication_                |The entire calendar has been published in 12 volumes from the set of cards held [...]   |
|_Alliedmaterials Relatedunits_               |Earlier files of a similar nature (1959-1968) are catalogued as Minnesota.[...]   |
|_Conditionsaccessuse Accessrestrictions_     |Unrestricted access, including display rights and consultation rights [...]   |
|_Conditionsaccessuse Findingaids_            |Series level descriptions available with associated box lists (Fonds) Canada [...]   |
|_Conditionsaccessuse Languagescripts_        |In Dakota, with partial English translation (File) U.S., Minnesota Historical [...]   |
|_Conditionsaccessuse Phystech_               |Videotapes are in ½ inch helical open reel-to-reel format. (Sub-series) U.S.,  [...]   |
|_Conditionsaccessuse Reprorestrictions_      |Copyright is retained by the artist (Fonds) Canada, York University Archives   |
|_Contentstructure Accruals_                  |Further accruals are expected (Fonds) Canada, York University Archives   |
|_Contentstructure Appraisaldestruction_      |An inventory to the former RG 43 (July 1998) is available. File lists  [...] |
|_Contentstructure Arrangement_               |The fonds is arranged into nine series: Railway Branch, Canal Branch, Legal records [...] |
|_Contentstructure Scopecontent_              |Consists of records created by the Department and received from its predecessor,  [...] |
|_Context Acqinfo_                            |Gift of Herbert Whittaker on 22 April 1994. (Fonds) Canada, York University Archives [...] |
|_Context Adminbiohistory_                    |The Department of Railways and Canals existed from 1879 to 1936. It was established on  [...] |
|_Context Archivalhistory_                    |Letters written by Herbert Whittaker and mailed to Sydney Johnson remained in the [...] |
|_Context Creator_                            |Canada. Dept. of Railways and Canals |
|_Descriptioncontrol Archivistsnote_          |Description prepared by S. Dubeau in October 1997; revised in April1999 (Fonds) Canada [...] |
|_Descriptioncontrol Descriptionsdate_        |Series registered, 24 September 1987. Description updated, 10 November 1999.  [...] |
|_Descriptioncontrol Rulesconventions_        |Rules for Archival Description (RAD), Bureau of Canadian Archivists, 1990. |
|_Identity Date_                              |1900 |
|_Identity Description Level_                 |File |
|_Identity Extent_                            |46 maps |
|_Identity Reference_                         |MET 19.164 |
|_Identity Title_                             |Sleeping Cat |
|_Notes Note_                                 |test notes |



![](MuseosNacioanlesCatalogoOnline.jpg)