---
title: 'Museum Metadata Embedder'
hide_hypothesis: false
menu: 'museum metadata embedder'
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

A veces, los donantes tienen hojas de cálculo que enumeran el contenido de sus colecciones. En lugar de volver a teclear todo esto en una herramienta como Archivists' Toolkit o en un editor XML, ¿no sería bueno generar automáticamente un documento XML de EAD a partir de la hoja de cálculo?

Con Stead puede hacerlo. Sólo hay que editar las cabeceras (primera fila de la hoja de cálculo) para que se ajusten al esquema de Stead. Esto puede implicar la división de algunas columnas para ajustarse al esquema, la adición de columnas y otras ediciones. Todo esto es probablemente más fácil, más rápido y más preciso de hacer en una hoja de cálculo que tratar de hacerlo en otro lugar volviendo a escribir todo.

Una vez que la hoja de cálculo esté lista, guárdela como CSV y utilice la herramienta de línea de comandos csv2ead para obtener un documento XML de EAD. Que lo disfrutes.
