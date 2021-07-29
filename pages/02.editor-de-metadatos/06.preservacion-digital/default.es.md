---
title: '[DRAFT] Preservación digital'
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

Este nuevo enfoque pretende colaborar con OAIS y PREMIS anticipándose a su implementación al ofrecer una capa previa, con simpleza y costes mínimos para los gestores e instituciones.

El modelo de preservación y divulgación diseñado está enfocado en acelerar la divulgación de los contenidos patrimoniales y no pretende reemplazar una propuesta robusta, sino permitirle a los pequeños actores dar un paso hacia adelante en la implementación de los metadatos descriptivos.

Actualmente, el -simplísimo- modelo de edición de metadatos colaborativa + preservación puesto a prueba consta de:

- Carpetas compartidas en [Box](https://www.box.com/), con gestión de usuarios y versionado de archivos
- 'Cold' backup en [Amazon S3 Glacier Deep Archive](https://aws.amazon.com/es/s3/glacier/)

Con este modelo, varios usuarios pueden editar metadatos y sincronizarlos a la nube por lotes, al mismo tiempo que se guarda una copia semanal en el backup frio.

**Desventaja:** Editar los metadatos de un archivo, implica que este se modifica, por lo que la sincronización puede ser lenta/costosa en el caso de archivos de gran tamaño.

**Solución:** Existen varias estrategias para mitigar este problema;
A- Durante la etapa de edición local, solo hacer un sincronización al final del día o tarea
B- Editar los metadatos en un archivo XMP externo durante el período de trabajo y al final de este, inyectarlo en el/los archivos