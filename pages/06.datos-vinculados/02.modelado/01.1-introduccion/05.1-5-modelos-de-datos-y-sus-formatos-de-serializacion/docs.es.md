---
title: '1.5 Modelos de datos y sus formatos de serialización'
taxonomy:
    category:
        - docs
---

Antes de pasar a la descripción general del modelado de datos, es importante distinguir claramente cada modelo conceptualmente de los formatos que se han desarrollado para serializar el modelo de datos. El proceso de serialización convierte las estructuras de datos en un formato. El formato permite la traducción de la información que está representando en un flujo de bits que puede manipularse por software, comunicarse a través de una red, etc. El formato permite una conversión a nivel de bits a los datos originales.

<mark>La diferencia entre un modelo y una serialización se puede comparar con un plato y su receta.</mark> El modelo en memoria es la cosa en sí y es accesible para su manipulación, o está inmediatamente listo para ser comido, como un plato preparado.
La serialización contiene todos los elementos necesarios para construir el modelo en memoria, al igual que una receta contiene toda la información que necesita para preparar el plato. 
La Tabla 2.1 ofrece una descripción general de los diferentes modelos de datos y sus formatos de serialización que se discutirán en las siguientes secciones.
 
<table>
<thead>
  <tr>
    <th colspan="4">Tabla 2.1 Los modelos de datos y sus formatos de serialización</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td><strong>modelo de datos</strong></td>
    <td><strong>formatos de serialización</strong></td>
  </tr>
  <tr>
    <td>datos tabulares</td>
    <td>CSV, TSV</td>
  </tr>
  <tr>
    <td>modelo relacional</td>
    <td>archivos binarios patentados</td>
  </tr>
  <tr>
    <td>lenguajes de metamarcado</td>
    <td>XML SGML</td>
  </tr>
  <tr>
    <td>RDF</td>
    <td>Turtle, N-Triples, RDF-XML</td>
  </tr>
</tbody>
</table>

Tabla 2.1 Modelos de datos y sus formatos de serialización