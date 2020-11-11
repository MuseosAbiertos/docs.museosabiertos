---
title: jExifToolGUI
external_links:
    no_follow: true
metadata:
    Keywords: 'jexiftoolgui, exiftool'
taxonomy:
    category:
        - docs
page-toc:
    active: true
---

# jExifToolGUI: una GUI multiplataforma [Java Swing] para ExifTool

## 1 Visión general
**jExifToolGUI** es un programa Java Swing que lee y escribe metadatos de archivos, predominantemente archivos de imágenes. Tiene algunas pantallas preformateadas para Exif, GPS/ Localización, XMP, GPano (y un conjunto muy limitado de etiquetas IPTC) para leer/escribir desde/hacia archivos de imagen usando ExifTool y también soporta geo-etiquetado. Además, puedes definir tu propia combinación de etiquetas de metadatos para escribir en tus imágenes. 
Esto te da la opción de usar cualquier etiqueta que ExifTool soporte. Además, también puedes definir etiquetas "totalmente nuevas" no existentes que pueden ser añadidas a sus archivos utilizando un archivo de configuración 'definido por el usuario' y una combinación de etiquetas definidas por el usuario. 
jExifToolGUI: '**j**' por Java, ‘**GUI**' por interfaz gráfica de usuario de ExifTool.

jExifToolGUI es sólo una interfaz gráfica para la excelente aplicaciñon de línea de comandos de código abierto en Perl, ExifTool de Phil Harvey. ExifTool es el verdadero "motor", pero como es una herramienta de línea de comandos es para algunos usuarios menos amigable. jExifToolGUI está construido alrededor de ExifTool e intenta dar muchas funcionalidades y flexibilidad sin tener que recordar cada parámetro de la línea de comandos. jExifToolGUI sólo implementa parte de la funcionalidad de ExifTool. Definitivamente no es un GUI completo para ExifTool y ciertamente no puede reemplazarlo (ExifTool es el motor "bajo el capó").

Este programa es de código abierto y completamente gratuito y siempre se mantendrá así, pero puedes donarme cualquier cantidad para mostrar tu agradecimiento si continúas usándolo (después de todo, me llevó muchas horas/días escribirlo). Mira el menú de Ayuda en el programa o [haz clic aquí](https://hvdwolf.github.io/jExifToolGUI/donate.html).
Y cuando se trata de la donación, lo mismo es válido, por supuesto, para la propia ExifTool. Para la donación a Exiftool (Phil Harvey), [ver aquí](https://exiftool.org/#donate).

Este manual y la versión de jExifToolGUI no siempre funcionan sincrónicamente. Si se añade una nueva funcionalidad al programa que requiera un nuevo capítulo o párrafo, el manual se actualizará para esa nueva sección. Sin embargo, no todas las partes del manual serán/podrán ser actualizadas, lo que podría llevar a pantallas de programas más antiguos en el manual que podrían desviarse ligeramente de la versión del programa con el que se está trabajando.
Ten en cuenta también que verás capturas de pantalla de varios sistemas operativos (Linux/Windows/MacOS) y/o gestores de ventanas (en Linux).

! Este manual se trabajará y se ampliará lentamente. Actualmente se encuentra en su infancia.

## 2 Versiones e "Instalación"
Esta herramienta está escrita en Linux, se usa en Linux y se prueba principalmente en Linux. Sin embargo, como es un programa multiplataforma de Java Swing debería funcionar bien en MacOS, Windows y teóricamente en todas las plataformas que soportan Java.

**Nota:** jExifToolGUI viene sin ExifTool, el cual debes descargar tú mismo del [sitio de ExifTool de Phil Harvey](http://www.sno.phy.queensu.ca/~phil/exiftool/) si quieres la última versión. En Linux también puedes usar la versión perteneciente a tu distribución.

### Universal jar
* `jExifToolGUI.jar`: Sólo el jExifToolGUI.jar desnudo, que contiene todas las dependencias. Necesitas tener la versión 8 (1.8) o más reciente de Java instalada en tu sistema.
Empieza desde una terminal con `java -jar jExifToolGUI.jar &.` Esta versión debe funcionar en cualquier sistema que venga incluido con java 8 o más reciente, o donde puedas instalar java 8 o más reciente. (Windows/Linux/MacOS (BSD*unix)/Solaris/AIX/HP*UX etc.)

### Windows
* `jExifToolGUI-<version>-win-x86_64_with-jre.zip`: Un ejecutable de 64 bits de Windows, incluyendo el Java V11. Descomprimir con las rutas!
* `jExifToolGUI-<version>-win-x86_64.zip`: Un ejecutable de 32/64 bits de Windows sin Java. Necesitas tener instalado en tu sistema el Java 8 (1.8) o uno más reciente.

Ambas versiones no vienen con instaladores. Simplemente descomprime (con rutas) en una carpeta de tu agrado y opcionalmente crea un acceso directo en tu escritorio.

### MacOS
* `jExifToolGUI-x86_64-macos-<version>-with_jre.dmg.zip`: Un paquete MacOS que incluye el Java V11. Nota: Apple es muy poco amigable con las cosas que no son de Apple como Java/Perl y otros softwares. Este paquete ES un paquete de Apple que funciona, pero no cumple totalmente con los estándares de Apple.
* `jExifToolGUI-x86_64-macos-<version>.dmg`: Un paquete de MacOS sin Java. Necesitas tener instalado en tu sistema el Java 8 (1.8) o uno más reciente.

Estos son paquetes de aplicaciones MacOS. En el caso de la versión completa, primero tienes que descomprimirla para obtener el archivo dmg. Abre el dmg (haciendo doble clic en él) y selecciónalo en el panel de navegación izquierdo de tu Finder, donde aparecerá como "disco virtual" (Los archivos DMG son archivos de imagen de disco con formato Mac). Arrastra el paquete "jExifToolGUI.app" de la dmg a la carpeta Aplicaciones o alguna otra de tu gusto.

**Note:** MacOS (el software Gatekeeper) normalmente no permite que se inicien aplicaciones que no se originen en la AppStore o que provengan de un desarrollador "no identificado" (yo). Necesitas añadir jExifToolGUI a la "lista de excepciones". Eso es en realidad muy simple. Ver soporte de Apple.

### Linux 
* `jExifToolGUI-<version>.deb`: Un paquete Linux.deb. para todos los sistemas basados en Debian (Debian/Ubuntu/Mint/MX Linux/Raspbian etc.). Esta es una versión multiarquitectura de Linux, ya que la versión relevante de Java V11 para su sistema/arquitectura será descargada como dependencia.
Usa `sudo dpkg -i jexiftoolgui-<versión>.deb` para instalar. A partir de ese momento también aparecerá en tu menú.
* `jExifToolGUI-<version>-x86_64.AppImage`: Linux universal Appimage incluyendo Java V11. Funciona en todos los sistemas Linux de 64 bits (y también dentro de la beta de Chromebook Linux).
Simplemente haz un `chmod +x jExifToolGUI-<version>-x86_64.AppImage` y ejecuta `./jExifToolGUI-<version>-x86_64.AppImage &.`


## 2.1 Uninstall

Si usas el paquete deb en cualquier sistema operativo Debian/Ubuntu como Linux, puedes usar apt-get o dpkg para desinstalarlo.
**Nota**: Todas las demás versiones, ya sean los paquetes de MacOS, o los de Windows .exes o linux appImage pueden ser simplemente borrados.

* Datos de usuario y datos de programa: En tu carpeta de usuario, encontrará una carpeta _jexiftoolgui_data_. Simplemente elimina esa carpeta.
* Logs: jar/Windows exe/appImage: En la misma carpeta donde se ejecuta la aplicación encontrarás una carpeta de registros. Simplemente elimínala.
Para los paquetes de MacOS y el jexiftoolgui.deb, los registros se escriben en registros de carpeta dentro de su carpeta de "/Users/(usuario)" Simplemente elimina la carpeta de registros.

## 3 Quick Start
El programa consiste en un panel izquierdo que contiene tus fotos y un panel derecho que consiste en un conjunto de pestañas. Una de estas pestañas ("Editar") contiene un subconjunto de pestañas (algunas de las subpestañas de la pestaña "Editar datos” serán tratadas en este manual para una mayor explicación).
Junto a las pestañas de la derecha, el programa también tiene varios menús que contienen más funcionalidades. Algunos botones y funciones no funcionarán, y están deshabilitados, hasta que no se haya cargado al menos una foto. La mayoría de las acciones sobre las imágenes que se realizan en las pestañas de la derecha o en los menús, sólo funcionan después de haber seleccionado al menos una o más de las fotos cargadas en el panel de la izquierda.

[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/mainscreen-quickstart-01.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/mainscreen-quickstart-01.png)

### View data
Selecciona una imagen y haga clic en uno de los radiobotones y luego selecciona la categoría de metadatos deseada en el desplegable. Las "Etiquetas comunes" no son la categoría "común" de ExifTool, pero lo que el autor considera son "categorías comúnmente seleccionadas". Las "combinaciones de etiquetas de metadatos definidas por el usuario" (ver sección "4.3 Create and use user defined metadata tag combinations") también se añaden a este desplegable. Si tienes varias imágenes seleccionadas, se mostrarán los metadatos de la última imagen seleccionada.

[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/ViewData.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/ViewData.png)

### Edit data
Aquí también; todas las acciones de la pestaña derecha "Editar" sólo funcionan después de haber seleccionado una o más de las fotos cargadas.

* Puedes seleccionar una imagen y modificar los datos de la misma.
* Puedes seleccionar varias imágenes a la vez y modificar los datos de todas ellas a la vez.
* Puedes seleccionar una imagen, copiar los datos de la misma, luego seleccionar varias imágenes y pegar los datos (copiados) en estas imágenes a la vez.

[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/EditData.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/EditData.png)

Todas las subpestañas de edición tienen una "línea inferior" de botones “Copiar de la imagen seleccionada", “Guardar en las imagenes seleccionadas" y “Ayuda".

[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/CopyFromSaveToHelp.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/CopyFromSaveToHelp.png)

Como se menciona en el punto #3: Puede copiar la información relevante de una imagen seleccionada. Luego puede escribir esta información en muchas imágenes.
Nota: En (menú) "Metadatos -> Exportar Sidecar" puede exportar los metadatos a varios de formatos. Especialmente MIE es un excelente formato para exportar. Puede leer el formato MIE como una imagen y usarlo para "Copiar desde".

Algunas de las subpestañas de la pestaña "Editar datos” se verán en este manual para una mayor explicación.

### Copy Data
Esta opción permite copiar categorías enteras de metadatos de una imagen a múltiples imágenes.

[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/CopyData.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/CopyData.png)

### Your Commands
Este programa tiene muchas funcionalidades y flexibilidad en la forma en que puede leer/escribir la fecha desde y hacia sus imágenes. En caso de que eso no sea suficiente, puedes simplemente crear tu propio comando y ejecutarlo en tus imágenes. Además, puedes guardar tus comandos como "favoritos" para usarlos repetidamente más tarde.

[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/YourCommands.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/YourCommands.png)

### ExifTool Database
Esta pestaña no hace nada con sus imágenes. Es simplemente una herramienta para consultar a través de todas las categorías de metadatos y etiquetas que ExifTool soporta. El número de etiquetas depende de la versión de ExifTool. La pestaña menciona en qué versión se basa la información recuperada (no tiene que ser la versión que tiene instalada en su equipo). También aquí puede guardar sus consultas SQL como favoritas.

[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/ExiftoolDatabase.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/ExiftoolDatabase.png)

## 4 Some Edit sub tabs further explained
En este capítulo se explicarán con más detalle algunas de las pestañas de edición. Otras como Exif, XMP y GPS/localización son demasiado directas para decir algo sobre ellas.

### 4.1 Geotagging
El geoetiquetado añade datos GPS a las imágenes basándose en los datos de un archivo de registro de seguimiento de GPS.
Este archivo de rastreo de GPS se puede usar desde el teléfono, el dispositivo gps, el dispositivo de navegación o cualquier otro dispositivo que proporcione dicho rastreo de GPS.
Se carga el archivo de registro de rastreo del GPS y se utiliza la interpolación lineal para determinar la posición del GPS en el momento de la imagen, luego se escriben las etiquetas pertinentes en la imagen (si se dispone de la información correspondiente). Esto significa que la cámara debe estar correctamente ajustada con respecto a la fecha/hora del lugar en el que se encuentra.

jExifToolGUI también soporta la función "Geosync" de ExifTool. La etiqueta Geosync sólo es necesaria cuando las marcas de tiempo de la imagen no están correctamente sincronizadas con la hora del GPS.
Por ejemplo, un valor de "+1:20" especifica que se añade 1 minuto y 20 segundos al valor de geotiempo antes de comprobarlo con el archivo de seguimiento del GPS. Esto es para una cámara que funciona 1 minuto 20 segundos más lento que el reloj del GPS.
El tiempo de Geosync se especifica como "SS", "MM:SS", "HH:MM:SS" o "DD HH:MM:SS" (donde SS=segundos, MM=minutos, HH=horas y DD=días), y se puede añadir un "+" o "-" para las diferencias positivas o negativas.
**Nota:** No uses (dobles) citas alrededor del tiempo de geosincronización en jExifToolGUI. Simplemente usa algo como -25 o +1:20

**En jExifToolGUI tienes 2 opciones:**

* Utiliza (una selección de) las imágenes que has cargado en el panel de imágenes de la izquierda.
* Especifique una carpeta que contenga un conjunto de imágenes a etiquetar.

En el caso de la primera opción es necesario dejar la carpeta vacía. Si la "Carpeta que contiene las imágenes:" no se deja vacía, siempre utilizará la segunda opción que es la carpeta.

"Hacer copia de seguridad de los originales" puede hacer copias de seguridad cuando se selecciona. Cuando se selecciona, se crearán nuevas imágenes y las imágenes originales obtendrán la extensión” .original".
**Nota:** jExifToolGUI escribirá tanto las etiquetas GPS EXIF como las etiquetas GPS XMP.

[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/geotaggingtab.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/geotaggingtab.png)

### 4.2 Usar lentes y crear 'plantillas de lentes' para sus lentes
Esta pantalla tiene dos propósitos:

* Agregar/quitar datos de la lente en tus fotos (primera fila de botones)
* Crear/Modificar la configuración de una lente (segunda fila de botones encerrada dentro del marco rayado), y en este manual dentro del marco rojo.
  
Ambas opciones se pueden usar para añadir datos de la lente a su imagen si no está completa.

Al margen de esto: Aún así, algunas lentes adicionales no son reconocidas completamente por la cámara y por lo tanto la información no se agrega a la imagen. Para estos casos puedes crear configuraciones de lentes y guardarlas y cargarlas para tus imágenes tomadas con esa lente específica.

[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/lenses.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/lenses.png)

Al hacer clic en el botón "Guardar esta configuración de lentes", aparecerá la siguiente ventana emergente.
[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/createsavelens.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/createsavelens.png)
La configuración de "Cargar una lente" es casi idéntica.

### 4.3 Crear y utilizar combinaciones de etiquetas de metadatos definidas por el usuario
Desde la versión 1.6 de jExifToolGUI le da la opción de definir su propio conjunto de etiquetas de metadatos que quiere añadir a sus imágenes. Incluso puedes definir múltiples conjuntos de combinación de metadatos para diferentes propósitos: paisajes, deportes, archivos, vida salvaje, familia, etcétera. 
La pantalla de mantenimiento se encuentra en el menú "Herramientas -> "Conjuntos de metadatos definidos por el usuario".
La pantalla de edición se encuentra en la pestaña "Editar Datos" dentro de “Combinaciones definidas por el usuario".

Actualmente hay tres conjuntos de metadatos "preinstalados":

* isadg: Los datos de ISAD(G) se añadirán al conjunto de XMP como nueva categoría xmp-isadg. (ISAD(G) es General International Standard Archival Description)
* gps_location: Todos los gps y etiquetas de localización en las 3 categorías EXIF, XMP e IPTC.
* Google Photos: Todas las etiquetas que Google Photos usa o reconoce.

Debajo de la pantalla de mantenimiento y la pantalla de edición.

[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/maintain_user_defined_metadata_combis.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/maintain_user_defined_metadata_combis.png)
La pantalla de creación y mantenimiento
[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/use_user_defined_metadata_combis.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/use_user_defined_metadata_combis.png)
The Edit screen where you use your defined metadata sets to write those tags to your images.

El siguiente video muestra:

* cómo crear combinaciones.
* cómo usar esta combinación en tus imágenes.

Las combinaciones creadas en este video se basan en etiquetas de metadatos ya conocidas por ExifTool. Estas son las etiquetas de metadatos estándar de Exif, XMP, IPTC, etc. Para el 99% de los usuarios esto es todo lo que necesitarán.

#### jExifToolGUI #01: Crear y utilizar combinaciones definidas por el usuario
[plugin:youtube](https://youtu.be/FvTN-pMU7yM)
**Nota:** El video se muestra por defecto en 1024x576 en 480p, pero la resolución máxima es de 1920x1080. (Al reproducirlo, selecciona el icono del engranaje en la barra inferior para ajustarlo a 1080P y haz clic en el icono inferior derecho para reproducirlo a pantalla completa).

Este video muestra las bases.
Los nombres de las etiquetas no se almacenarán en orden alfabético sino en el orden en que los creaste/guardaste.
También puedes cortar/copiar y pegar etiquetas: El segundo video muestra cómo usar Copiar & Pegar desde (o hacia) otras aplicaciones como hojas de cálculo (Excel, Google Spreadsheets, etc.) donde defines tus combinaciones.

#### jExifToolGUI #02: user combis copy paste
[plugin:youtube](https://youtu.be/8cXT2Aiy6bI)
**Nota:** El video se muestra por defecto en 1024x576 en 480p, pero la resolución máxima es 1920x1080. (Al reproducirlo selecciona el icono del engranaje en la barra inferior para ponerlo en 1080P y haz clic en el icono inferior derecho para reproducirlo a pantalla completa)

##### Creando etiquetas inexistentes para añadirlas a sus imágenes
A continuación sólo se ofrece un breve resumen de lo que se puede hacer.

ExifTool permite definir etiquetas de metadatos que "no existen todavía". Para ello es necesario crear un archivo de configuración personalizado en el que se definen esas etiquetas de metadatos "totalmente nuevas".
Esto se describe en [Sitio ExifTool](https://exiftool.org/config.html)
Otro ejemplo se entrega con el propio jExifToolGUI. Se llama _isadg-struct.cfg_ y se basa en el estándar de archivo ISAD(G) (basado en este esquema XML). El _isadg-struct.cfg_ que he creado se puede encontrar [aquí en línea]
(https://raw.githubusercontent.com/hvdwolf/jExifToolGUI/master/src/main/resources/isadg-struct.cfg), pero también se encuentra en la carpeta jexiftoolgui_data dentro de su carpeta de usuario. (Para asegurarse de que los usuarios no corrompan este archivo, se sobrescribe en cada inicio del programa).
Cuando se desea utilizar etiquetas inexistentes, primero se crea el archivo cfg que contiene estas etiquetas. A continuación, define su conjunto de combinaciones en la pantalla de Herramientas, basándose en los nombres de las etiquetas en su archivo de configuración. Al guardar este conjunto, también se utiliza el selector de archivos para seleccionar el archivo cfg que se ha creado. jExifToolGUI copiará entonces el archivo cfg en la carpeta jexiftoolgui_data y almacenará el enlace entre las etiquetas y el archivo de configuración en la base de datos. Cuando quiera utilizar este conjunto de combinaciones, jExifToolGUI también utilizará el archivo de configuración (tiene que utilizar el archivo, de lo contrario las etiquetas no se pueden escribir).
**Nota:** ExifTool, por lo tanto jExifToolGUI, puede leer esas etiquetas de las imágenes en cualquier momento. Sólo necesitas el archivo de configuración cuando quieras escribir las etiquetas en tus imágenes.

## 5 Varias opciones de menú
En este capítulo se explicarán algunas de las opciones del menú. Algunas porque son algo más complicadas. Otros menús/pantallas porque puede que no sepas cuál es la "utilidad" de estas opciones.

### 5.1 Rename photos
jExifToolGUI te da muchas opciones para renombrar tus fotos. Esto se explicará aquí.
Dentro del marco "a rayas" se ven las opciones de los cuadros desplegables 1 y 2.
El renombramiento tiene 4 "subsecciones": el "prefijo", el "sufijo", la "numeración" y la "extensión" que te dan para un nombre de archivo "prefijo_sufijo_(numeración).extensión".

* prefijo: Esta es la primera parte del nombre. Tienes 4 opciones básicas para elegir, donde las 2 opciones de los desplegables están representadas en el marco a rayas. El campo "Cadena" te da la opción de darle cualquier nombre que quieras con espacios (no se admiten: comillas, comillas dobles, barras oblicuas hacia adelante, barras oblicuas hacia atrás, signos de interrogación, signos de exclamación, dos puntos y comillas (y probablemente más caracteres "extraños").
* sufijo: Esta es la segunda parte del nombre. Tiene (actualmente) 10 opciones para elegir, algunas de las cuales se basan en los metadatos de sus imágenes (éstas también podrían cambiar más tarde a un desplegable). La única observación aquí es que "${nombre del archivo}" es el nombre de archivo original que su cámara da a la imagen como por ejemplo "DSC_1234.NEF" o "P10001234.JPG", etcétera.
* numeración: Si usas un "nombre" (String) o "AñoMesFecha", podrías obtener imágenes con el mismo nombre. Para evitar esto, puede autonumerar las imágenes, dando por ejemplo "exiftool-001.jpg", "exiftool-002.jpg", etc.
* extensión: No se puede cambiar la extensión como tal (un jpg es siempre un jpg). Algunas cámaras/teléfonos usan extensiones en mayúsculas, otras en minúsculas. Si esto te molesta, puedes cambiarlo aquí.

[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/renamephotos.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/renamephotos.png)

### 5.2 Sidecar exports
Los metadatos de las imágenes y otros tipos de archivos pueden almacenarse en (exportados a) archivos de metadatos separados. ExifTool soporta y puede crear varios de estos archivos de metadatos. El archivo "sidecar" XMP es probablemente el formato más conocido. Otros tipos de archivos de metadatos soportados son EXIF, XMP, MIE ("El único formato que no apesta") y EXV. jExifToolGUI puede exportar todos los metadatos contenidos en las imágenes y otros archivos que ExifTool soporta, y esto se puede usar a través de (Menú) "Metadata-> Exportar metadatos". Los formatos soportados son TXT, TAB, XML, HTML y CSV.

The Sidecar exports can be found via (menu) "Metadata -> Sidecar exports". The Sidecar exports are slighly different.
[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/metadatasidecar.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/metadatasidecar.png)

All Sidecar files can be read as "images". This makes it possible to read (for example) a .mie file together with a number of images. You use the .mie metadata file as "Copy from selected image" and use it to populate one or more images. For this reason there is no import function for these Sidecar files as you can use them as just described.

## 6 Preferences
The Preferences can be found under the menu "File -> Preferences"
Currently the Preferences screen has 3 tabs: General (Linux LXDE), Language (Windows), System (MacOS). See below (reduced size) images.
[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/01-preferences-general-500.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/01-preferences-general-500.png)

### The "General" tab (left):

* W.r.t. the "Raw Image viewer". jExiftoolGUI can show quite a lot of images like jpg/png/tif/bmp/pgm, but not Raw Images (it can convert some to jpg thumbnails for viewing in the left pane), and neither can most operating systems show Raw Images. So if you have Raw Images and you want to see them full screen, you need to install a Raw Image Viewer.
* Values to always add to your images: These are 3 input fields writing to multiple metadata tags. The xmp and iptc tags are used by Google Photos and many professional photographers. The somewhat older exif tags are meant for the same purposes but slightly outdated.

### The "Language" tab (top right):

* jExifToolGUI can be translated. jExifToolGUI will try to start in the operating system language, but only if that is available as translated "property language". It is currently translated in (American) English (default), Spanish, German and Dutch. On this tab you can select one of those languages if you prefer that over your system language, or in case your system language is not supported but your American English is not as good as your Spanish or German.
* Many Exiftool users have helped to translate the desciption of metadata tags in Exiftool. (This has nothing to do with jExifToolGUI, but with ExifTool). You can select a number of languages and if the tag is translated you will see the tag in that language.

Translating the application in your language is a volunteers/community effort. [Please help in translating this application](https://hvdwolf.github.io/jExifToolGUI/translate.html).

* The "System" tab (bottom right): W.r.t. the log level: Do not set it too high. That will create huge files and slow down the application (due to all the logging). The author or someone else might ask you to put it to the highest level for trobleshooting.

The "Check for new jExifToolGUI version on program start" is useful as you will automatically be informed of a new release on startup.

## Appendix A GNU Free Documentation License
[https://www.gnu.org/licenses/old-licenses/fdl-1.2.html#]

Version 1.2, November 2002
     Copyright © 2000, 2001, 2002 Free Software Foundation, Inc.
     51 Franklin St, Fifth Floor, Boston, MA  02110-1301, USA

     Everyone is permitted to copy and distribute verbatim copies
     of this license document, but changing it is not allowed.

### 0. PREAMBLE
The purpose of this License is to make a manual, textbook, or other functional and useful document free in the sense of freedom: to assure everyone the effective freedom to copy and redistribute it, with or without modifying it, either commercially or noncommercially. Secondarily, this License preserves for the author and publisher a way to get credit for their work, while not being considered responsible for modifications made by others.

This License is a kind of “copyleft”, which means that derivative works of the document must themselves be free in the same sense. It complements the GNU General Public License, which is a copyleft license designed for free software.

We have designed this License in order to use it for manuals for free software, because free software needs free documentation: a free program should come with manuals providing the same freedoms that the software does. But this License is not limited to software manuals; it can be used for any textual work, regardless of subject matter or whether it is published as a printed book. We recommend this License principally for works whose purpose is instruction or reference.

### 1. APPLICABILITY AND DEFINITIONS
This License applies to any manual or other work, in any medium, that contains a notice placed by the copyright holder saying it can be distributed under the terms of this License. Such a notice grants a world-wide, royalty-free license, unlimited in duration, to use that work under the conditions stated herein. The “Document”, below, refers to any such manual or work. Any member of the public is a licensee, and is addressed as “you”. You accept the license if you copy, modify or distribute the work in a way requiring permission under copyright law.

A “Modified Version” of the Document means any work containing the Document or a portion of it, either copied verbatim, or with modifications and/or translated into another language.

A “Secondary Section” is a named appendix or a front-matter section of the Document that deals exclusively with the relationship of the publishers or authors of the Document to the Document's overall subject (or to related matters) and contains nothing that could fall directly within that overall subject. (Thus, if the Document is in part a textbook of mathematics, a Secondary Section may not explain any mathematics.) The relationship could be a matter of historical connection with the subject or with related matters, or of legal, commercial, philosophical, ethical or political position regarding them.

The “Invariant Sections” are certain Secondary Sections whose titles are designated, as being those of Invariant Sections, in the notice that says that the Document is released under this License. If a section does not fit the above definition of Secondary then it is not allowed to be designated as Invariant. The Document may contain zero Invariant Sections. If the Document does not identify any Invariant Sections then there are none.

The “Cover Texts” are certain short passages of text that are listed, as Front-Cover Texts or Back-Cover Texts, in the notice that says that the Document is released under this License. A Front-Cover Text may be at most 5 words, and a Back-Cover Text may be at most 25 words.

A “Transparent” copy of the Document means a machine-readable copy, represented in a format whose specification is available to the general public, that is suitable for revising the document straightforwardly with generic text editors or (for images composed of pixels) generic paint programs or (for drawings) some widely available drawing editor, and that is suitable for input to text formatters or for automatic translation to a variety of formats suitable for input to text formatters. A copy made in an otherwise Transparent file format whose markup, or absence of markup, has been arranged to thwart or discourage subsequent modification by readers is not Transparent. An image format is not Transparent if used for any substantial amount of text. A copy that is not “Transparent” is called “Opaque”.

Examples of suitable formats for Transparent copies include plain ascii without markup, Texinfo input format, LaTeX input format, SGML or XML using a publicly available DTD, and standard-conforming simple HTML, PostScript or PDF designed for human modification. Examples of transparent image formats include PNG, XCF and JPG. Opaque formats include proprietary formats that can be read and edited only by proprietary word processors, SGML or XML for which the DTD and/or processing tools are not generally available, and the machine-generated HTML, PostScript or PDF produced by some word processors for output purposes only.

The “Title Page” means, for a printed book, the title page itself, plus such following pages as are needed to hold, legibly, the material this License requires to appear in the title page. For works in formats which do not have any title page as such, “Title Page” means the text near the most prominent appearance of the work's title, preceding the beginning of the body of the text.

A section “Entitled XYZ” means a named subunit of the Document whose title either is precisely XYZ or contains XYZ in parentheses following text that translates XYZ in another language. (Here XYZ stands for a specific section name mentioned below, such as “Acknowledgements”, “Dedications”, “Endorsements”, or “History”.) To “Preserve the Title” of such a section when you modify the Document means that it remains a section “Entitled XYZ” according to this definition.

The Document may include Warranty Disclaimers next to the notice which states that this License applies to the Document. These Warranty Disclaimers are considered to be included by reference in this License, but only as regards disclaiming warranties: any other implication that these Warranty Disclaimers may have is void and has no effect on the meaning of this License.

### 2. VERBATIM COPYING
You may copy and distribute the Document in any medium, either commercially or noncommercially, provided that this License, the copyright notices, and the license notice saying this License applies to the Document are reproduced in all copies, and that you add no other conditions whatsoever to those of this License. You may not use technical measures to obstruct or control the reading or further copying of the copies you make or distribute. However, you may accept compensation in exchange for copies. If you distribute a large enough number of copies you must also follow the conditions in section 3.

You may also lend copies, under the same conditions stated above, and you may publicly display copies.

### 3. COPYING IN QUANTITY
If you publish printed copies (or copies in media that commonly have printed covers) of the Document, numbering more than 100, and the Document's license notice requires Cover Texts, you must enclose the copies in covers that carry, clearly and legibly, all these Cover Texts: Front-Cover Texts on the front cover, and Back-Cover Texts on the back cover. Both covers must also clearly and legibly identify you as the publisher of these copies. The front cover must present the full title with all words of the title equally prominent and visible. You may add other material on the covers in addition. Copying with changes limited to the covers, as long as they preserve the title of the Document and satisfy these conditions, can be treated as verbatim copying in other respects.

If the required texts for either cover are too voluminous to fit legibly, you should put the first ones listed (as many as fit reasonably) on the actual cover, and continue the rest onto adjacent pages.

If you publish or distribute Opaque copies of the Document numbering more than 100, you must either include a machine-readable Transparent copy along with each Opaque copy, or state in or with each Opaque copy a computer-network location from which the general network-using public has access to download using public-standard network protocols a complete Transparent copy of the Document, free of added material. If you use the latter option, you must take reasonably prudent steps, when you begin distribution of Opaque copies in quantity, to ensure that this Transparent copy will remain thus accessible at the stated location until at least one year after the last time you distribute an Opaque copy (directly or through your agents or retailers) of that edition to the public.

It is requested, but not required, that you contact the authors of the Document well before redistributing any large number of copies, to give them a chance to provide you with an updated version of the Document.

### 4. MODIFICATIONS
You may copy and distribute a Modified Version of the Document under the conditions of sections 2 and 3 above, provided that you release the Modified Version under precisely this License, with the Modified Version filling the role of the Document, thus licensing distribution and modification of the Modified Version to whoever possesses a copy of it. In addition, you must do these things in the Modified Version:

* A. Use in the Title Page (and on the covers, if any) a title distinct from that of the Document, and from those of previous versions (which should, if there were any, be listed in the History section of the Document). You may use the same title as a previous version if the original publisher of that version gives permission.
* B. List on the Title Page, as authors, one or more persons or entities responsible for authorship of the modifications in the Modified Version, together with at least five of the principal authors of the Document (all of its principal authors, if it has fewer than five), unless they release you from this requirement.
* C. State on the Title page the name of the publisher of the Modified Version, as the publisher.
* D .Preserve all the copyright notices of the Document.
* E. Add an appropriate copyright notice for your modifications adjacent to the other copyright notices.
* F. Include, immediately after the copyright notices, a license notice giving the public permission to use the Modified Version under the terms of this License, in the form shown in the Addendum below.
* G. Preserve in that license notice the full lists of Invariant Sections and required Cover Texts given in the Document's license notice.
* H. Include an unaltered copy of this License.
* I. Preserve the section Entitled “History”, Preserve its Title, and add to it an item stating at least the title, year, new authors, and publisher of the Modified Version as given on the Title Page. If there is no section Entitled “History” in the Document, create one stating the title, year, authors, and publisher of the Document as given on its Title Page, then add an item describing the Modified Version as stated in the previous sentence.
* J. Preserve the network location, if any, given in the Document for public access to a Transparent copy of the Document, and likewise the network locations given in the Document for previous versions it was based on. These may be placed in the “History” section. You may omit a network location for a work that was published at least four years before the Document itself, or if the original publisher of the version it refers to gives permission.
* K. For any section Entitled “Acknowledgements” or “Dedications”, Preserve the Title of the section, and preserve in the section all the substance and tone of each of the contributor acknowledgements and/or dedications given therein.
* L. Preserve all the Invariant Sections of the Document, unaltered in their text and in their titles. Section numbers or the equivalent are not considered part of the section titles.
* M. Delete any section Entitled “Endorsements”. Such a section may not be included in the Modified Version.
* N. Do not retitle any existing section to be Entitled “Endorsements” or to conflict in title with any Invariant Section.
* O. Preserve any Warranty Disclaimers.

If the Modified Version includes new front-matter sections or appendices that qualify as Secondary Sections and contain no material copied from the Document, you may at your option designate some or all of these sections as invariant. To do this, add their titles to the list of Invariant Sections in the Modified Version's license notice. These titles must be distinct from any other section titles.

You may add a section Entitled “Endorsements”, provided it contains nothing but endorsements of your Modified Version by various parties—for example, statements of peer review or that the text has been approved by an organization as the authoritative definition of a standard.

You may add a passage of up to five words as a Front-Cover Text, and a passage of up to 25 words as a Back-Cover Text, to the end of the list of Cover Texts in the Modified Version. Only one passage of Front-Cover Text and one of Back-Cover Text may be added by (or through arrangements made by) any one entity. If the Document already includes a cover text for the same cover, previously added by you or by arrangement made by the same entity you are acting on behalf of, you may not add another; but you may replace the old one, on explicit permission from the previous publisher that added the old one.

The author(s) and publisher(s) of the Document do not by this License give permission to use their names for publicity for or to assert or imply endorsement of any Modified Version.

### 5. COMBINING DOCUMENTS
You may combine the Document with other documents released under this License, under the terms defined in section 4 above for modified versions, provided that you include in the combination all of the Invariant Sections of all of the original documents, unmodified, and list them all as Invariant Sections of your combined work in its license notice, and that you preserve all their Warranty Disclaimers.

The combined work need only contain one copy of this License, and multiple identical Invariant Sections may be replaced with a single copy. If there are multiple Invariant Sections with the same name but different contents, make the title of each such section unique by adding at the end of it, in parentheses, the name of the original author or publisher of that section if known, or else a unique number. Make the same adjustment to the section titles in the list of Invariant Sections in the license notice of the combined work.

In the combination, you must combine any sections Entitled “History” in the various original documents, forming one section Entitled “History”; likewise combine any sections Entitled “Acknowledgements”, and any sections Entitled “Dedications”. You must delete all sections Entitled “Endorsements.”

### 6. COLLECTIONS OF DOCUMENTS
You may make a collection consisting of the Document and other documents released under this License, and replace the individual copies of this License in the various documents with a single copy that is included in the collection, provided that you follow the rules of this License for verbatim copying of each of the documents in all other respects.

You may extract a single document from such a collection, and distribute it individually under this License, provided you insert a copy of this License into the extracted document, and follow this License in all other respects regarding verbatim copying of that document.

### 7. AGGREGATION WITH INDEPENDENT WORKS
A compilation of the Document or its derivatives with other separate and independent documents or works, in or on a volume of a storage or distribution medium, is called an “aggregate” if the copyright resulting from the compilation is not used to limit the legal rights of the compilation's users beyond what the individual works permit. When the Document is included in an aggregate, this License does not apply to the other works in the aggregate which are not themselves derivative works of the Document.

If the Cover Text requirement of section 3 is applicable to these copies of the Document, then if the Document is less than one half of the entire aggregate, the Document's Cover Texts may be placed on covers that bracket the Document within the aggregate, or the electronic equivalent of covers if the Document is in electronic form. Otherwise they must appear on printed covers that bracket the whole aggregate.

### 8. TRANSLATION
Translation is considered a kind of modification, so you may distribute translations of the Document under the terms of section 4. Replacing Invariant Sections with translations requires special permission from their copyright holders, but you may include translations of some or all Invariant Sections in addition to the original versions of these Invariant Sections. You may include a translation of this License, and all the license notices in the Document, and any Warranty Disclaimers, provided that you also include the original English version of this License and the original versions of those notices and disclaimers. In case of a disagreement between the translation and the original version of this License or a notice or disclaimer, the original version will prevail.

If a section in the Document is Entitled “Acknowledgements”, “Dedications”, or “History”, the requirement (section 4) to Preserve its Title (section 1) will typically require changing the actual title.

### 9. TERMINATION
You may not copy, modify, sublicense, or distribute the Document except as expressly provided for under this License. Any other attempt to copy, modify, sublicense or distribute the Document is void, and will automatically terminate your rights under this License. However, parties who have received copies, or rights, from you under this License will not have their licenses terminated so long as such parties remain in full compliance.

### 10. FUTURE REVISIONS OF THIS LICENSE
The Free Software Foundation may publish new, revised versions of the GNU Free Documentation License from time to time. Such new versions will be similar in spirit to the present version, but may differ in detail to address new problems or concerns. See http://www.gnu.org/copyleft/.

Each version of the License is given a distinguishing version number. If the Document specifies that a particular numbered version of this License “or any later version” applies to it, you have the option of following the terms and conditions either of that specified version or of any later version that has been published (not as a draft) by the Free Software Foundation. If the Document does not specify a version number of this License, you may choose any version ever published (not as a draft) by the Free Software Foundation.