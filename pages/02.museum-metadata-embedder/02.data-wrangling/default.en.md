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

Data, in its natural state ("Raw Data"), often have recording errors that make it difficult to analyze. As they are recorded by different systems and people, it is normal that we end up with a file in which the same value is expressed in different ways (for example, a date may be recorded as June 28, or as 28/06), as there may be blank records and of course, grammatical errors.

"Data Wrangling" is a frequently used term in different Data Science processes and is used to define the procedure that consists of extracting, transforming and mapping information.

When analyzing these data, all these records must be preprocessed. In other words, they must be cleaned, unified, consolidated and normalized so that they can be used to extract valuable information. This is what Data Wrangling is all about, preparing the data to be used.

Commonly, data from files and catalogs are stored in comma separated files (CSV), and to a lesser extent separated by a tabulator (TSV).

For this task we mainly use three tools:

|                        |                                                                                                                                                                                                                                                                 |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Data Wrangling         | [Open Refine](https://openrefine.org/)                                                                                                                                                                                                                          |
| Spreadsheet    | [Google Sheets](https://www.google.com/intl/es_ar/sheets/about/), [Libre Office](https://es.libreoffice.org/), [Microsoft Excel](https://www.microsoft.com/es-ww/microsoft-365/excel) and others.                                                                  |
| File renaming | [Transnomio](https://transnomino.bastiaanverreijt.com/), [A Better Finder Rename](https://www.publicspace.net/ABetterFinderRename/index.html), [KRename](https://apps.kde.org/es/krename/), [Bulk Rename Utility](https://www.bulkrenameutility.co.uk/) and others. |



## OpenRefine
### Selected resources
* [Data Wrangling with Open Refine](https://towardsdatascience.com/data-wrangling-with-open-refine-d7e94ef2ac7b#:~:text=Open%20Refine%20is%20a%20free,your%20data%20to%20the%20public.)
* [Using OpenRefine to Clean Your Data](https://multimedia.journalism.berkeley.edu/tutorials/openrefine/)
* [Cleaning Data with OpenRefine](https://programminghistorian.org/en/lessons/cleaning-data-with-openrefine)

## Google Sheets
For this manual we created a 'spreadsheet' with a set of 'VRA Core' and 'Dublin Core' tags and data, coming from the 'Bruzzone Collection' that will serve as a guide: [Museum Metadata Embedder dataset](https://docs.google.com/spreadsheets/d/1k9P2fkDYwJ8bVRJMhavEeiJyV-49ZRujuFBtLyGAjdg/), which is not only used to contain the data, but also to apply various formulas and support sheets and string translation.
_Comment permissions are enabled; you are free to download it or comment on it._

## File naming convention

The Bruzzone Collection catalog uses the following convention:

1. Country: _AR_
2. Institution: _MA (Museos Abiertos)_
3. Collection: _Bruzzone_
4. Artist: _Agerta Antonella (Apellido, Nombre)_
5. Work Name: _Je suis la_
6. ID object: _2014_
7. Object numbering: _00_
8. Language: _EN_

Example: <code>AR-MA-Bruzzone-Agesta-Antonella-Je-suis-la-2014-00-EN.jpg</code>

* Start with general information (on the left) and get more specific as you move through your file name, just as you do in your folder structure. This helps your files to be ordered logically, from top to bottom.
* Consider including a general prefix (customer, product) and/or a specific suffix (version number, color).
* Keep your abbreviations short but meaningful, 2-3 letters if possible, as long as they have a common sense meaning.
* Use underscores, hyphens, or upper or lower case letters to help with legibility, and do not use spaces.
* Dots should only be used to separate the file name from the format extension (e.g. logo.jpg), never in the file name itself.
* Dates should be in [ISO 8601](https://es.wikipedia.org/wiki/ISO_8601) 'year-month-day' format, so that files are sorted chronologically. Example: 2022-12-31
* When applying file versions, use the designator "v" or "V" and a number, e.g. "v01".
* Avoid special characters (< > | [ ] & $ + : * ? ") to make your filenames usable on the web and compatible across platforms.
* Avoid file names that are too long. For example, the Windows API imposes a maximum filename length such that a filename, including the path to the file, cannot exceed between 255 and 260 characters.

### Resources

* [PhotoMetadata.org](https://www.photometadata.org/META-Resources)
* [Developing a file naming convention, University of Glasgow](https://edshare.gla.ac.uk/807/1/File_Naming_v2_20200608.pdf)
* [Best Practice for Naming Electronic Files, The J. Paul Getty Trust](https://files.archivists.org/groups/museum/standards/3.%20Records%20Management/Getty%20Records%20Management%20User%20Guides.pdf)
* [Controlled Vocabulary. “Recommendations for Limitations on Image Filenaming.”](http://www.controlledvocabulary.com/imagedatabases/filename_limits.html)

