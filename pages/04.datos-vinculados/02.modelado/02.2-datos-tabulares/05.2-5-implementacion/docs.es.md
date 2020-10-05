---
title: '2.5 Implementación'
taxonomy:
    category:
        - docs
---

<mark>Los datos tabulares son uno de los formatos conceptuales más fáciles y, como tal, cualquier paquete de software ofrecerá soporte.</mark>

La forma más común son las aplicaciones de hojas de cálculo como Microsoft Excel o Libre Office, que en esencia ofrecen una tabla gigante que se puede modificar. Todo software de hoja de cálculo ofrece la posibilidad de exportar a TSV o CSV, aunque por supuesto con la pérdida de fórmulas (celdas que se calculan en base a otras celdas), formato (como color y bordes) y funcionalidades como macros, que mencionamos anteriormente. Los tipos de datos también se pierden: todo el contenido de la celda se almacena como texto.

<mark>Incluso con el modelo de datos más simple, muchas cosas pueden salir mal en la práctica.<mark> Varios elementos son dignos de mención aquí:

* Los datos se pueden separar con una coma, pero dependiendo de la configuración local del sistema, ¡esto podría ser un punto y coma! Por ejemplo, en muchos idiomas europeos, se utiliza una coma en lugar de un punto como separador decimal en los números (por lo que 1,5 es en realidad 1 1/2). En estos sistemas, por lo tanto, no sería práctico usar una coma como separador de columnas, por lo que la elección de un punto y coma ~ para que CSV no siempre sea fiel a su nombre. En la práctica, CSV ha llegado a representar cualquier tipo delimitado por separadores, que confusamente también incluye TSV.

* Las filas terminan con un salto de línea. Desafortunadamente, diferentes sistemas pueden producir resultados diferentes. Por ejemplo, en los sistemas Windows, un salto de línea en realidad consta de dos caracteres (un retorno de carro seguido de una nueva línea), mientras que en los sistemas basados en Linux, es solo un carácter (solo una nueva línea). Además, los sistemas basados en Linux pueden esperar que la última línea termine con un salto de línea, aunque esto no es necesario en Windows.

* No hay forma de indicar la diferencia entre la fila del encabezado y el resto de los datos. Esto significa que tendremos que decirle esto explícitamente al analizador.

* Si el valor del campo en sí contiene una coma o un salto de línea, como Koons, Jeff aquí, el valor generalmente se incluye entre comillas dobles, por lo que se puede analizar correctamente como un solo valor y no como varias filas o columnas. Tenga en cuenta que no todos los analizadores admiten ambos casos; Los saltos de línea, especialmente, pueden resultar confusos. En general, se permite encerrar cualquier campo con comillas dobles, incluso si no aparecen caracteres especiales dentro del valor.

* Otro problema peligroso es la codificación de caracteres. Los diferentes sistemas utilizan diferentes códigos de bytes para representar caracteres, en particular si estos caracteres se encuentran fuera del alfabeto ASCII tradicional, como letras acentuadas o caracteres japoneses. Si un sistema ha escrito un archivo con una determinada codificación, es importante que otro sistema utilice la misma codificación para leer el archivo. De lo contrario, un carácter acentuado en una codificación podría transformarse accidentalmente en uno o más caracteres en una codificación diferente. Este fenómeno se llama [mojibake](https://en.wikipedia.org/wiki/Mojibake), que no es más que una presentación incorrecta de caracteres debido a una falta de coincidencia de codificación. El Capítulo 3 explorará cómo los problemas mencionados anteriormente afectan la calidad de los metadatos y qué se puede hacer para mitigarlos.

* ¿Qué pasa si el valor del campo contiene comillas dobles? Esto se resuelve escapando de la cita, agregando un carácter delante de ella que indica que el siguiente carácter no tiene un significado especial. En el caso de CSV, este escape se realiza duplicando la cotización. Por ejemplo, el valor ancho: <kbd> 7", alto: 5" </kbd> se codifica como <kbd> "ancho: 7"", alto: 5"" " </kbd>, donde cada comilla literal es precedido de otro.

* El principal problema con CSV es que hay muchas formas de codificar un archivo. El Grupo de trabajo de ingeniería de Internet (IETF) propuso una forma estándar de serializar CSV (Shafranovich, 2005), y la mayoría de los analizadores pueden leer este formato. Sin embargo, esto de ninguna manera implica que todos los generadores lo harán. Afortunadamente, la mayoría de los analizadores son adaptativos: aplican una heurística al archivo en cuestión para determinar qué convenciones se utilizaron. Por ejemplo, si cada línea del archivo contiene el mismo número de punto y coma, es probable que se asuma que el delimitador es un punto y coma. Además, si la tercera columna siempre consta de dígitos decimales, excepto la primera fila (como en nuestro ejemplo), se puede suponer que la primera línea contiene datos de encabezado. Por supuesto, ninguna de estas estrategias es perfecta; en la práctica, la verificación humana es necesaria para un análisis correcto.
