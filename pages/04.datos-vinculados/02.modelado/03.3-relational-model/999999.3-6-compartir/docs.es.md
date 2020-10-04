---
title: '3.6 Compartir'
taxonomy:
    category:
        - docs
---

Como se mencionó al comienzo de este capítulo, las instituciones ya pensaron en la interoperabilidad entre colecciones desde el principio, cuando se implementaron RDMS en algunas instituciones pioneras del patrimonio cultural. Existía (y sigue existiendo) una fuerte creencia de que adquirir el mismo sistema de gestión de colecciones proporciona la base necesaria para la interoperabilidad. Sin embargo, la personalización de estas herramientas de software para adaptarse a los requisitos específicos de cada institución a menudo resultó en diferentes enfoques con respecto al uso de elementos de metadatos. Esto hizo que el intercambio de registros entre instituciones, que podrían haber estado usando exactamente el mismo software, fuera problemático. Dejar que las bases de datos se comuniquen entre sí y compartan su contenido es un asunto complejo, independientemente del dominio de la aplicación.

En esta etapa, es importante señalar la diferencia entre archivos binarios y no binarios. La sección anterior ilustró cómo los formatos de archivo tabular utilizan archivos de texto, lo que le permite abrir un archivo .tsv o .csv con cualquier editor de texto estándar o software de hoja de cálculo, lo que hace que el intercambio de metadatos sea muy sencillo.

Sin embargo, las bases de datos se almacenan en archivos binarios que introducen una dependencia de una aplicación de software específica. Si, por ejemplo, quisiera reutilizar una base de datos de una institución, estaría obligado a utilizar el mismo RDMS. Las licencias para RDMS propietario cuestan fácilmente alrededor de US $ 10,000 y podría tener problemas de compatibilidad si usa diferentes versiones del mismo software. También puede crear una consulta de lenguaje de consulta estructurado (SQL), lo que le permite crear un volcado de datos y luego importarlo en otra aplicación. Pero incluso si existe una versión estandarizada de SQL, tenga en cuenta que los proveedores implementan el estándar de diversas formas. Ciertos RDMS tienen sus propias extensiones patentadas, por ejemplo, para tipos de columna, lo que conduce nuevamente a posibles problemas de compatibilidad de datos.

Por tanto, podemos concluir que la interoperabilidad de las bases de datos es bastante problemática. Afortunadamente, se han desarrollado métodos para facilitar la exportación e importación de datos estructurados desde y hacia diferentes bases de datos.