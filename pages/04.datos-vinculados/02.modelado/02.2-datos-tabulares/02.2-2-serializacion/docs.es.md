---
title: '2.2 Serialización'
taxonomy:
    category:
        - docs
---

<mark>Los formatos de serialización más populares de datos tabulares son los valores separados por comas (CSV) y los valores separados por tabulaciones (TSV).</mark>
    La única, pero importante, diferencia entre estos dos formatos son los caracteres, apropiadamente llamados delimitadores, que se utilizan para indicar la separación entre valores. Como su nombre lo indica, los archivos CSV usan una coma como delimitador y tabulador el TSV. Tenga en cuenta que se puede utilizar cualquier tipo de carácter como delimitador. 
    Los datos CSV de la Tabla 2.2 están separados por una coma y las filas terminan con un salto de línea de la siguiente manera:

```
titulo, creador, fecha, coleccion
Guernica, Pablo Picasso,1937,Museo Reina Sofia
First Communion,Picasso,1895,Museo Picasso
Puppy. “Koons, Jeff",1992, Guggenheim
```

La versión de TSV se vería exactamente igual, pero las comas serían reemplazadas por tabulaciones. Estrictamente hablando, las citas en torno a <kbd>Koons, Jeff</kbd> no serían necesarias porque la coma no tiene un significado especial. Sin embargo, si un valor debe contener un carácter de tabulación real, serían necesarias las comillas.