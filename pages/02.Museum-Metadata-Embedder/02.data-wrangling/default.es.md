---
title: 'Data Wrangling'
hide_hypothesis: false
menu: 'Data Wrangling'
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

Al momento de hacer un análisis de esos datos, todos esos registros tienen que preprocesarse. Es decir, se tienen que limpiar, unificar, consolidar y normalizar para que se puedan utilizar y lograr extraer información de valor. De esto se trata el Data Wrangling, de preparar los datos para poder ser aprovechados.

Comúnmente los datos de archivos y catálogos se guardan en archivos separados por comas (CSV), y en menor medida separados por un tabulador (TSV).

Para esta tarea utilizamos principalmente tres herramientas:
* [Open Refine](https://openrefine.org/)
* Una planilla de cálculo, como [Google Sheets](https://www.google.com/intl/es_ar/sheets/about/), [Libre Office](https://es.libreoffice.org/), [Microsoft Excel](https://www.microsoft.com/es-ww/microsoft-365/excel) u otros.
* Herramientas para el cambio de nombre de los archivos, como [Transnomio](https://transnomino.bastiaanverreijt.com/), [A Better Finder Rename](https://www.publicspace.net/ABetterFinderRename/index.html), [KRename](https://apps.kde.org/es/krename/), [Bulk Rename Utility](https://www.bulkrenameutility.co.uk/) u otros.

## OpenRefine
* [Limpieza de datos con OpenRefine; Seth van Hooland, Ruben Verborgh, y Max De Wilde](https://programminghistorian.org/es/lecciones/limpieza-de-datos-con-OpenRefine)
* [Guía para la limpieza de datos sobre biodiversidad con OpenRefine; Paula F. Zermoglio, Camila A. Plata Corredor, John R. Wieczorek, Ricardo Ortiz Gallego, Leonardo Buitrago. Versión 3.0](https://docs.gbif.org/openrefine-guide/3.0/es/)
* [Limpieza de bases de datos con OpenRefine; Claudia Báez – CdR-LAB](https://fundacionperiodismo.org/formacion-dual/wp-content/uploads/2018/10/Limpieza-de-datos-con-Open-Refine.pdf)
* [Funcionalidades Open Refine; Ministerio TIC Colombia](https://youtu.be/tzXExfZCA1w)


## Google Sheets
Para este manual hemos creado una 'hoja de cálculo' con un conjunto de tags 'VRA Core' y 'Dublin Core' y datos, provenientes de la 'Colección Bruzzone' que nos servirán de guía: [Museum Metadata Embedder dataset](https://docs.google.com/spreadsheets/d/1k9P2fkDYwJ8bVRJMhavEeiJyV-49ZRujuFBtLyGAjdg/), la cual contiene varias formulas y hojas de soporte.
_Los permisos de comentarios están habilitados; eres libre de descargarla o comentar en ella._


## Convención de nombres de archivos / Convenciones de nomenclatura de archivos

1. Pais
2. Institución
3. Colección
4. Artista
5. Nombre obra
6. Numeración objeto
7. Idioma

AR-MA-Bruzzone-Agesta-Antonella-Je-suis-la-2014-00-EN.jpg

Comience con información general (a la izquierda) y sea más específico a medida que avanza por el nombre de su archivo, al igual que lo hace en su estructura de carpetas. Esto ayuda a que sus archivos se ordenen de forma lógica, de arriba hacia abajo.
Considere incluir un prefijo general (cliente, producto) y/o un sufijo específico (número de versión, color).
Mantenga sus abreviaturas cortas pero significativas, 2-3 letras si es posible, siempre que tengan un significado de sentido común.
Use guiones bajos, guiones o letras mayúsculas o minúsculas para ayudar con la legibilidad, y no use espacios.
Los puntos solo deben usarse para separar el nombre del archivo de la extensión de formato (por ejemplo, logotipo.jpg), nunca en el nombre del archivo en sí.
Las fechas deben ir año-mes-día (con nuestros sin guiones) para que los archivos se ordenen cronológicamente.
Si termina con más de un nombre de archivo similar, use 2-3 puntos numéricos al final y comience con ceros (001, 002). Del mismo modo, si usa números al principio del nombre del archivo, use 2-3 puntos numéricos y comience con ceros para que sus archivos se ordenen correctamente.
Al aplicar versiones de archivos, utilice el designador "V" y un número, por ejemplo, "V01".
Evite los caracteres especiales (< > | [ ] & $ + \ / : * ? “) para que sus nombres de archivo sean utilizables en la web y compatibles entre plataformas
Evite los nombres de archivo demasiado largos. Por ejemplo, la API de Windows impone una longitud máxima de nombre de archivo tal que un nombre de archivo, incluida la ruta de acceso al archivo, no puede exceder entre 255 y 260 caracteres.

