---
title: 'Manipulación de datos'
hide_hypothesis: false
menu: 'Manipulación de datos'
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

Los datos, en su forma natural (lo que llamamos “Raw Data”), suelen tener errores de registro que imposibilitan un análisis. Al ser registrados por distintos sistemas y personas es normal que terminemos con un archivo en el que un mismo valor esté expresado de distintas maneras (por ejemplo, una fecha puede estar registrada como 28 de Junio, o como 28/06), como pueden haber registros en blanco y por supuesto, errores gramaticales.

"Data Wrangling" puede traducirse al Español como "manipulación de datos", "disputa de datos" o "gestión de datos". Es un término que se usa con frecuencia en distintos procesos del Data Science o Ciencia de Datos y se utiliza para definir el procedimiento que consiste en extraer, transformar y mapear la información.

Al momento de hacer un análisis de esos datos, todos esos registros tienen que preprocesarse. Es decir, se tienen que limpiar, unificar, consolidar y normalizar para que se puedan utilizar y lograr extraer información de valor. De esto se trata el Data Wrangling, de preparar los datos para poder ser aprovechados.

Comúnmente los datos de archivos y catálogos se guardan en archivos separados por comas (CSV), y en menor medida separados por un tabulador (TSV).

Para esta tarea utilizamos principalmente tres herramientas:

|                        |                                                                                                                                                                                                                                                                 |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Data Wrangling         | [Open Refine](https://openrefine.org/)                                                                                                                                                                                                                          |
| Planilla de cálculo    | [Google Sheets](https://www.google.com/intl/es_ar/sheets/about/), [Libre Office](https://es.libreoffice.org/), [Microsoft Excel](https://www.microsoft.com/es-ww/microsoft-365/excel) entre otros.                                                                  |
| Renombrado de archivos | [Transnomio](https://transnomino.bastiaanverreijt.com/), [A Better Finder Rename](https://www.publicspace.net/ABetterFinderRename/index.html), [KRename](https://apps.kde.org/es/krename/), [Bulk Rename Utility](https://www.bulkrenameutility.co.uk/) entre otros. |



## OpenRefine
### Recursos seleccionados
* [Limpieza de datos con OpenRefine; Seth van Hooland, Ruben Verborgh, y Max De Wilde](https://programminghistorian.org/es/lecciones/limpieza-de-datos-con-OpenRefine)
* [Guía para la limpieza de datos sobre biodiversidad con OpenRefine; Paula F. Zermoglio, Camila A. Plata Corredor, John R. Wieczorek, Ricardo Ortiz Gallego, Leonardo Buitrago. Versión 3.0](https://docs.gbif.org/openrefine-guide/3.0/es/)
* [Limpieza de bases de datos con OpenRefine; Claudia Báez – CdR-LAB](https://fundacionperiodismo.org/formacion-dual/wp-content/uploads/2018/10/Limpieza-de-datos-con-Open-Refine.pdf)
* [Funcionalidades Open Refine; Ministerio TIC Colombia](https://youtu.be/tzXExfZCA1w)


## Google Sheets
Para este manual creamos una 'hoja de cálculo' con un conjunto de tags 'VRA Core' y 'Dublin Core' y datos, provenientes de la 'Colección Bruzzone' que nos servirán de guía: [Museum Metadata Embedder dataset](https://docs.google.com/spreadsheets/d/1k9P2fkDYwJ8bVRJMhavEeiJyV-49ZRujuFBtLyGAjdg/), la cual no solo es utilizada para contener los datos, sino para aplicar varias formulas y hojas de soporte y traducción de cadenas de texto.
_Los permisos de comentarios están habilitados; eres libre de descargarla o comentar en ella._


## Convención de nombres de archivos

El catálogo de la Colección Bruzzone utiliza la siguiente convención:

1. Pais: _AR_
2. Institución: _MA (Museos Abiertos)_
3. Colección: _Bruzzone_
4. Artista: _Agerta Antonella (Apellido, Nombre)_
5. Nombre obra: _Je suis la_
6. ID objeto: _2014_
7. Numeración objeto: _00_
8. Idioma: _EN_

Ejemplo: <code>AR-MA-Bruzzone-Agesta-Antonella-Je-suis-la-2014-00-EN.jpg</code>

* Comienza con información general (a la izquierda) y sea más específico a medida que avanza por el nombre de su archivo, al igual que lo hace en su estructura de carpetas. Esto ayuda a que tus archivos se ordenen de forma lógica, de arriba hacia abajo.
* Considera incluir un prefijo general (cliente, producto) y/o un sufijo específico (número de versión, color).
* Mantén sus abreviaturas cortas pero significativas, 2-3 letras si es posible, siempre que tengan un significado de sentido común.
* Usa guiones bajos, guiones o letras mayúsculas o minúsculas para ayudar con la legibilidad, y no use espacios.
* Los puntos solo deben usarse para separar el nombre del archivo de la extensión de formato (por ejemplo, logo.jpg), nunca en el nombre del archivo en sí.
* Las fechas deben ser en formato [ISO 8601](https://es.wikipedia.org/wiki/ISO_8601) 'año-mes-día', para que los archivos se ordenen cronológicamente. Ejemplo: 2022-12-31
* Al aplicar versiones de archivos, utilice el designador "v" o "V" y un número, por ejemplo, "v01".
* Evita los caracteres especiales (< > | [ ] & $ + \ / : * ? “) para que sus nombres de archivo sean utilizables en la web y compatibles entre plataformas.
* Evita los nombres de archivo demasiado largos. Por ejemplo, la API de Windows impone una longitud máxima de nombre de archivo tal que un nombre de archivo, incluida la ruta de acceso al archivo, no puede exceder entre 255 y 260 caracteres.


### Recursos

* [PhotoMetadata.org](https://www.photometadata.org/META-Resources)
* [Developing a file naming convention, University of Glasgow](https://edshare.gla.ac.uk/807/1/File_Naming_v2_20200608.pdf)
* [Best Practice for Naming Electronic Files, The J. Paul Getty Trust](https://files.archivists.org/groups/museum/standards/3.%20Records%20Management/Getty%20Records%20Management%20User%20Guides.pdf)
* [Controlled Vocabulary. “Recommendations for Limitations on Image Filenaming.”](http://www.controlledvocabulary.com/imagedatabases/filename_limits.html)

