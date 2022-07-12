---
title: 'Why MME'
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
menu: 'Why MME'
media_order: 'EXIF Data Configuration.png,xmpquote.gif'
---

Usually, collections of art objects are recorded in two files, in spreadsheets that list the contents of your collections and in images, which represent them. 
In other words, to 'see' the metadata of an image, you must have a spreadsheet application; if you want to send it by email, you must send both files, where the CSV file usually contains the entire collection.

## Where to save the metadata ?
In the GLAM universe, traditionally, it is considered that **an archival image should never be altered**, so metadata is written 'outside the image', either in a database or in an external file (XMP, CSV...). This philosophy is what most applications have today, for example, [Tropy](https://tropy.org/).

However, this assumption is wrong, since EXIF or XMP, while recording the data within the image file, does not alter the image, since it records it within a header area. Furthermore, metadata writing applications do not have the ability to alter images.

**MME** follows an opposite philosophy and embeds the metadata in an area reserved for them, so that they are always 'inside' the image, facilitating ingestion and simplifying the registration and dissemination processes, although it does not discourage 'also' saving them in a CSV file. In fact, **MME** embeds the metadata from a CSV file.

## Why write metadata on images ?

### EXIF (Exchangeable Image File Format)
The Exif standard was established in 1985 by the JCIA (Japan Camera Industry Association), the predecessor of CIPA (Camera & Imaging Products Association). Today, [JEITA](https://www.jeita.or.jp/english/) (Japan Electronics and Information Technology Industries Association) manages the standard, while CIPA discusses new technology and promotes the standard.

The main feature of Exif is its ability to record camera information in an image file at the point of capture. Some common data fields include the make and model of the camera, its serial number, the date and time the image was captured, the shutter speed, aperture, lens used, and ISO speed setting. Exif metadata often includes other technical details, such as white balance and distance to the subject.

![EXIF%20Data%20Configuration](EXIF%20Data%20Configuration.png "EXIF%20Data%20Configuration")

Read more:
* [EXIF](https://es.wikipedia.org/wiki/Exchangeable_image_file_format)
* [EXIF Data Explained](https://photographylife.com/what-is-exif-data)

### XMP (Extensible Metadata Plataform)

Adobe's Extensible Metadata Platform (XMP) is a tagging technology created by Adobe Systems Incorporated in 2001. XMP records metadata in a syntax formed by a subset of [W3C](https://www.w3.org/), which is written in [XML](https://www.w3.org/XML/).
It was created to extend the concept, created by EXIF to its range of products, extending it to other file types with new and more data types.
XMP allows the creation of new data sets for different purposes.

![xmpquote](xmpquote.gif "xmpquote")

So we have created a repository with a set of GLAM presets: [Adobe Bridge Custom Metadata JSON GLAM Presets](https://github.com/MuseosAbiertos/Adobe-Bridge-Custom-Metadata-JSON-Presets) for Abobe Bridge's [Custom Metadata Panel](https://github.com/adobe-dmeservices/custom-metadata).
These presets were added to Photoshop and Illustrator, as well as with Bridge, InDesign and Premiere Pro in early 2022.
We will be grateful if you use them and share your experience with us !

## What does Museum Metadata Embedder do?

**MME** is very simple; it gets data from a CSV file and embeds it in [all kinds of images](https://exiftool.org/#supported) and PDF files thanks to [ExifTool](https://exiftool.org/) (by Phil Harvey).
This command line script (CLI) is written in Python 3 and has a graphical interface that we named **'gmme'**.
It uses a map to relate the "Display Name" (CSV Column Header) and "Label Name", for each of the standards.
Once installed you can use it without prior configuration, but you can also modify it for your needs.
It can handle hundreds or thousands of files and has a very detailed logging system that allows you to see the progress as well as any errors that may occur.

That is, import the metadata from a CSV file. You can also extract them from images to other CSVs, simply by running:
<code>exiftool -csv test.jpg > test.csv</code>
or extracting only the VRA Core metadata
<code>exiftool -csv -xmp-vrae:all test.jpg > test.csv</code>



