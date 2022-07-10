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

Los datos, en su forma natural (lo que llamamos “Raw Data”), suelen tener errores de registro que imposibilitan un análisis exacto. Al ser registrados por distintos sistemas y personas, es normal que terminemos con un archivo en el que un mismo valor esté expresado de distintas maneras (por ejemplo, una fecha puede estar registrada como 28 de Junio, o como 28/06 en un mismo archivo), pueden haber registros en blanco, y por supuesto, errores gramaticales.

Al momento de hacer un análisis de esos datos, todos esos registros tienen que preprocesarse. Es decir, se tiene que limpiar, unificar, consolidar y normalizar los datos para que se puedan utilizar y lograr extraer información de valor. De esto se trata el Data Wrangling, de preparar los datos para poder ser aprovechados.

Comúnmente, estos datos los guardamos en archivos separados por comas (CSV), y en menor medida separados por un tabulador (TSV).

Para esta tarea utilizamos principalmente dos herramientas:
* [Open Refine](https://openrefine.org/)
* [Google Sheets](https://www.google.com/intl/es_ar/sheets/about/), [Libre Office](https://es.libreoffice.org/), [Microsoft Excel](https://www.microsoft.com/es-ww/microsoft-365/excel) u otros.

## OpenRefine
* [Limpieza de datos con OpenRefine; Seth van Hooland, Ruben Verborgh, y Max De Wilde](https://programminghistorian.org/es/lecciones/limpieza-de-datos-con-OpenRefine)
* [Guía para la limpieza de datos sobre biodiversidad con OpenRefine; Paula F. Zermoglio, Camila A. Plata Corredor, John R. Wieczorek, Ricardo Ortiz Gallego, Leonardo Buitrago. Versión 3.0](https://docs.gbif.org/openrefine-guide/3.0/es/)
* [Limpieza de bases de datos con OpenRefine; Claudia Báez – CdR-LAB](https://fundacionperiodismo.org/formacion-dual/wp-content/uploads/2018/10/Limpieza-de-datos-con-Open-Refine.pdf)
* [Funcionalidades Open Refine; Ministerio TIC Colombia](https://youtu.be/tzXExfZCA1w)


## Google Sheets
Para este manual hemos creado una 'hoja de cálculo' con un conjunto de tags 'VRA Core' y 'Dublin Core' y datos, provenientes de la 'Colección Bruzzone' que nos servirán de guía: [Museum Metadata Embedder dataset](https://docs.google.com/spreadsheets/d/1k9P2fkDYwJ8bVRJMhavEeiJyV-49ZRujuFBtLyGAjdg/), la cual contiene varias formulas y hojas de soporte.
_Los permisos de comentarios están habilitados; eres libre de descargarla o comentar en ella._




