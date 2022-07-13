---
title: Download
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

## GitHub
https://github.com/MuseosAbiertos/Museum-Metadata-Embedder

### Instructions
* Clone the repository or download the .zip file to the folder you want to work in; it is correct to name it 'mme'.
  * on MacOS, you can use this path: <code>/Users/<user\>/mme</code>
  * on Windows, you can use this path: <code>C:\Users\<user\>\mme</code>
* You must keep the file structure inside the .zip file you download.
* The image files to be processed must be located inside the 'images' folder, inside 'mme'.
    
### System requirements
    
|          |                                             |
| -------- | ------------------------------------------- |
| Perl     | https://www.activestate.com/products/perl/  |
| Python 3 | https://www.python.org/downloads/ |

    
### Custom configuration
**MME** uses a JSON map to map the _"Display Name" (CSV Column Header) <-> "Label Name"_, for each of the standards. The file must be located inside the 'data' directory, in a JSON file named 'maps.json'.
This file can be edited to add new tags.

Only the headers (first row of the spreadsheet) needs to be edited to fit the schema. This may involve splitting some columns to fit the schema, adding columns, and other edits. All of this is probably easier, faster and more accurate to do in a spreadsheet.

### Repository files
| Path                              | Description                                                       |
| :-------------------------------- | :---------------------------------------------------------------- |
| csv/                               | Suggested folder for hosting CSV files                     |
| csv/test.csv                      | CSV test file for the first run and test            |
| exiftool/                          | Exiftool executable                                               |
| data/exiftool_configs/             | Configuration files for ExifTool                           |
| data/notion_maps_txts/             | Internal work folder -not mandatory-.                    |
| data/maps.json                    | Relationship map between CSV headers and ExifTool tags |
| images/                            | Test files for first run and test               |
| images/vrae_exiftool_example.tiff | VRA Core sample file                                       |
|                                   |                                                                   |
