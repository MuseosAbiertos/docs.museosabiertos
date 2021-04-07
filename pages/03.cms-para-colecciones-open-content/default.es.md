---
title: 'CMS para Colecciones Open Content'
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

**“Ofrecer la vía más rápida y simple para publicar colecciones abiertas”**
_Opt title: _-Lightweight & Fast Drupal Distro for implementing web GLAM Collections-_

Existen numerosas herramientas para la catalogación de colecciones, pero la implementación de ellas es costosa y requiere de personal experto tanto para la catalogación, como para el desarrollo y mantenimiento de la infraestructura técnica. 

Emprender la catalogación de una colección y posteriormente ofrecerla online, con estándares internacionales, es una tarea compleja que requiere de varios actores, dejando 'fuera de partido' a numerosas instituciones y a la gran parte de las colecciones.
Nuestro objetivo es acortar los tiempos y lograr en el menor tiempo posible, estén accesibles online el mayor número de colecciones.

El proceso de edición de metadatos y publicación está compuesto de dos herramientas principales: Un '[Editor de metdatos GLAM](https://docs.museosabiertos.org/editor-de-metadatos)' y este [CMS para Colecciones Open Content](https://docs.museosabiertos.org/cms-para-colecciones-open-content).

!!! Nuestra meta es obtener las [5 estrellas de datos abiertos vinculados](https://5stardata.info/es/) 

## Workflow

### Normalización de datos de archivo/colecciones
Esta fase consta de la recolección de datos de la colección para su normalización. Para ello utilizamos diferentes técnicas y herramientas de [data scraping](https://en.wikipedia.org/wiki/Data_scraping) que nos devuelven datos crudos y que posteriormente son 'formateados' según las necesidades específicas.

### Edición de metadatos de archivos documentales
En esta fase se escriben los metadatos en las imágenes de los objetos mediante scripts automatizados o manualmente con varias herramientas como [jExifToolGUI](https://github.com/hvdwolf/jExifToolGUI) o [presets GLAM específicos](https://github.com/MuseosAbiertos/Adobe-Bridge-Custom-Metadata-JSON-Presets) para [Custom Metadata Panel for Adobe Bridge](https://github.com/adobe-dmeservices/custom-metadata).

* Publicación de datasets como Datos Abiertos Vinculados
* Publicación de un webesite para la consulta de datos
* Implementación de un SPARQL Endpoint. 
* Se recolectarán los siguientes datos: (autor, obra, muestras, galerías, fecha, coordenadas geográficas) 
