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

# jExifToolGUI: a cross-platform java Swing gui for ExifTool

## 1 Overview
**jExifToolGUI** is a java Swing program that reads and writes metadata from files, predominantly image files. It has some preformatted screens for exif, gps/location, xmp, gpano (and a very limited set of IPTC) tags to write/read from/to image files using **ExifTool** and it also supports geotagging. Next to that you can define your own combination of metadata tags to write to your images. This gives you the option to use any tag that Exiftool supports. Next to that you can also define "brand new" non-existing tags that can be added to your files using a user-defined configuration file and user define tag combination. jExifToolGUI: j for java, GUI for Graphical User Interface to ExifTool.

jExifToolGUI is only a graphical frontend for the excellent open source Perl command line ExifTool by Phil Harvey. ExifTool is the real "engine", but as it is a command-line tool it is to some users less userfriendly. jExifToolGUI is built around exiftool and tries to give a lot of funtionalities and flexibility without you having to remember every command line parameter. jExifToolGUI only implements part of the functionality of ExifTool. It is definitely not a complete GUI for Exiftool and can certainly not replace it (if only that ExifTool is still the engine "under the hood").

This program is Open Source and completely free and will always stay that way, but you can donate any amount to me to show your appreciation if you continue to use it (after all it took a lot of hours/days to write it). See the Help menu in the program or click here.

And when it comes to donation, the same is off course valid for ExifTool itself. For donation to exiftool (Phil Harvey), see here.

This manual and the jExifToolGUI version might not always run synchronously. If new functionality is added to the program which requires a new chapter or paragraph, the manual will be updated for that new section. However, not all parts of the manual will/might be updated which might lead to older program screens in the manual that might slightly deviate from the program version you will be working with.
Note also that you will see screen captures from several operating systems (Linux/Windows/MacOS) and/or window managers (on Linux).

**This manual will be worked on and slowly expand. It currently is in its infancy.**

## 2 Versions and "Installation"
This tool is written on Linux, used on Linux and mostly tested on Linux. However, as it is a java Swing cross-platform program it should run fine on MacOS, Windows and theoretically on all platforms that support java.

**Note:** jExifToolGUI comes without exiftool which you need to download yourself from Phil Harvey's exiftool site if you want the latest version. On Linux you can also use the version belonging to your distribution.

### Universal jar
* `jExifToolGUI.jar`: Just the bare jExifToolGUI.jar containing all dependencies. You need to have java version 8 (1.8) or newer installed on your system.
Start from a terminal with java -jar jExifToolGUI.jar &. This version should run on any system that comes included with java 8 or newer, or where you can install java 8 or newer. (Windows/Linux/MacOS (BSD*unix)/Solaris/AIX/HP*UX etc.)

### Windows
*     `jExifToolGUI-<version>-win-x86_64_with-jre.zip`: A windows 64-bit executable including java V11. Unzip with paths!
*     `jExifToolGUI-<version>-win-x86_64.zip`: A windows 32/64 bit executable without java. You need java 8 (1.8) or newer installed on your system.

    Both versions do not come with installers. Simply unzip (with paths) to a folder of your liking and optionally create a shortcut on your desktop.
   
### MacOS
* `jExifToolGUI-x86_64-macos-<version>-with_jre.dmg.zip`: A MacOS bundle including java V11. Note: Apple is very unfriendly to non-Apple stuff like java/perl and other software. This bundle IS a working Apple bundle but not entirely according Apple standards.
* `jExifToolGUI-x86_64-macos-<version>.dmg`: A MacOS bundle without java. You need java 8 (1.8) or newer installed on your system.

These are MacOS Application bundles. In case of the full version you first need to unzip it to get the dmg file. Open the dmg (by double-clicking it) and select it from the left navigation panel in your Finder where it will appear as a "virtual disk" (DMG Files are Mac-formatted Disk Image Files). Drag the "jExifToolGUI.app" bundle from the dmg into a folder of your liking where Applications is the most logical one.

**Note:** MacOS (the Gatekeeper software) does normally not allow applications to be started that do not originate from the AppStore or come from an "unidentified" developer (me). You need to add jExifToolGUI to the "list of exceptions". That is actually very simple. See Apple support

### Linux 
* `jExifToolGUI-<version>.deb`: a Linux .deb package. For all Debian based systems (Debian/Ubuntu/Mint/MX Linux/Raspbian etc. etc.). This is a linux multi-architecture version as the relevant java V11 version for your system/architecture will be downloaded as dependency.
Use `sudo dpkg -i jexiftoolgui-<version>.deb` to install. As of that moment it will also appear in your menu.
* `jExifToolGUI-<version>-x86_64.AppImage`: Linux universal Appimage including java V11. Runs on every 64bit intel Linux system (and also inside Chromebook Linux beta).
Simpy do a `chmod +x jExifToolGUI-<version>-x86_64.AppImage and start with ./jExifToolGUI-<version>-x86_64.AppImage &.`


## 2.1 Uninstall

    If you use the deb package on any Debian/Ubuntu like Linux OS, you can use apt-get or dpkg to uninstall it.
All other versions: be it the MacOS bundles, or windows .exes or linux appImage can simply be deleted.

* User data and program data: In your home/user folder, you will find a folder jexiftoolgui_data. Simply remove that folder.
* Logs:
jar/Windows exe/appImage: In the same folder where your run the application you will find a folder logs. Simply delete that one.
For the MacOS bundles and the jexiftoolgui.deb, the logs are written to folder logs inside your user/home folder. Simply delete the logs folder.

## 3 Quick Start
The program consists of a left pane containing your photos, and a right pane which consists of a set of tabs. One of these tabs ("Edit") contains a subset of tabs (Some of the sub tabs on the "Edit Data" tab will return in this manual for further explanation).
Next to the tabs on the right, the program also has several menus which contain more functionalities. A number of buttons and functions will not work, and are disabled, until you have loaded at least one photo. Most actions on your images which you perform in the right tabs or in the menus, only work after having selected at least one, or more of the loaded photos in the left pane.

[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/mainscreen-quickstart-01.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/mainscreen-quickstart-01.png)

### View data
Select an image and click one of the radiobuttons and select the desired metadata category from the drop-down. The "Common Tags" is not the ExifTool category "common", but what the author considers are "commonly selected categories". The "user defined metadata tags combinations" (see here) are also added to this drop down. If you have multiple images selected, the metadata for the last selected image will be displayed.

[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/ViewData.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/ViewData.png)

### Edit data
Here as well: All actions in the right "Edit" tab only work after having selected one or more of the loaded photos.

* You can select one image and modify the data for it.
* You can select multiple images at once and modify the data for all these images at once.
* You can select one image, copy data from it, then select multiple images, and paste the (copied) data to these multiple images at once.

[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/EditData.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/EditData.png)

All Edit sub tabs do have a "bottom line" of buttons "copy from", "save to" and "Help"

[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/CopyFromSaveToHelp.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/CopyFromSaveToHelp.png)

As mentioned in bullet #3: You can copy the relevant information from a selected image. Then you can write this info to many images.
Note: Under (menu) "Metadata -> SideCar Exports" you can export metadata to a number of format. Especially MIE is an excellent format to export to. You can read the MIE format back in like an image and use it to "Copy from".

Some of the sub tabs on the "Edit Data" tab will return in this manual for further explanation

### Copy Data
This options allows you to copy entire metadata categories from one image to multiple images.

[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/CopyData.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/CopyData.png)

### Your Commands
This program has quite a lot of functionality and flexibility in how you can read/write date from and to your images. In case that is not sufficient you can simply create your own command and run that on your images. Next to that you can also save your commands as "favorites" for later, repeated use.

[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/YourCommands.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/YourCommands.png)

### ExifTool Database
This tab does nothing with your images. It is simply a tool to query through all the metadata categories and tags that ExifTool supports. The number of tags is dependent on your ExifTool version. The tab mentions on which version the retrieved information is based (this doesn't have to be the version you have installed on your laptop/pc). Also here you can save your SQL queries as favorites.

[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/ExiftoolDatabase.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/ExiftoolDatabase.png)

## 4 Some Edit sub tabs further explained
In this chapter some of the edit tabs will be further explained. Others like Exif, XMP and GPS/locaion are too straight-forward to say something about them.

### 4.1 Geotagging
Geotagging adds GPS data to your images based on data from a GPS track log file.
This GPS track file can be used from your phone, gps device, navigation device, or whatever you have providing such a GPS track.
The GPS track log file is loaded, and linear interpolation is used to determine the GPS position at the time of the image, then the relevant tags are written to the image (if the corresponding information is available). It means that your camera needs to be set correctly with regard to the date/time of the location where you are.

jExifToolGUI also supports the "Geosync" feature of ExifTool. The Geosync tag is only needed when the image timestamps are not properly synchronized with GPS time.
For example, a value of "+1:20" specifies that 1 minute and 20 seconds is added to the Geotime value before checking with the GPS track file. This is for a camera running 1 minute 20 seconds slower than the GPS clock.
The Geosync time is specified as "SS", "MM:SS", "HH:MM:SS" or "DD HH:MM:SS" (where SS=seconds, MM=minutes, HH=hours and DD=days), and a leading "+" or "-" may be added for positive or negative differences.
**Note:** Do not use (double) quotes around the geosync time in jExifToolGUI. Simply use something like -25 or +1:20

In jExifToolGUI you have 2 options:

* Use (a selection of) the images you loaded in the left images pane.
* Specify a folder containing a set of images to be tagged.

In case of the first option you need to leave the folder empty. If the "Folder containing the images:" is not left empty, it will always use the second option being the folder.

"The "Make backup of Originals" checkbox can make backups when selected. When selected new images will be created and the original images will get the extension ".original".
**Note:** that jExifToolGUI will write both the EXIF GPS tags as well as the XMP GPS tags.

[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/geotaggingtab.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/geotaggingtab.png)

### 4.2 Use Lenses and create lens templates for your lenses
This screen has two purposes:

* Add/remove lens data to your photos (first row of buttons)
* Create/Modify a lens configuration (second row of buttons enclosed inside lined framework), and in this manual within the red frame.
  
Both options can be used to add lens data to your image if it is not complete.

Next to that: Still some add-on lenses are not completely recognized by the camera and therefore the info is not added to the image. For these cases you can create lens configs and save and load them for your images taken with that specific lens.

[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/lenses.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/lenses.png)

When you click the button "Save this lens configuration", the following popup will be displayed.
[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/createsavelens.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/createsavelens.png)
The "Load a lens configuration" is almost identical.

### 4.3 Create and use user defined metadata tag combinations
Version 1.6 of jExifToolGUI gives you the option to define your own set of metadata tags that you want to add to your images. You can even define multiple metadata combination sets for different purposes: landscapes, sport, archiving, wildlife, family, etcetera. The Maintenance screen can be found in the menu "Tools -> User defined Metadata combis".
The edit screen can be found under the "Edit Data" tab inside "User defined combinations".
Currently three metadata sets are "pre-installed":

* isadg: ISAD(G) data will be added to the XMP set as new category xmp-isadg. (ISAD(G) is General International Standard Archival Description)
* gps_location: All gps and location tags in the 3 categories EXIF,XMP and IPTC.
* Google Photos: All tags that Google Photos uses or recognizes.

Below the maintenance screen and edit screen.
Click the images to see a full-size version in a separate tab.
[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/maintain_user_defined_metadata_combis.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/maintain_user_defined_metadata_combis.png)
The maintenance and create screen	
[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/use_user_defined_metadata_combis.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/use_user_defined_metadata_combis.png)
The Edit screen where you use your defined metadata sets to write those tags to your images.

The below video shows:

* how to create combinations.
* how to use this combination on your images.

The created combinations in this movie are based om metadata tags already known to Exiftool. These are the standard Exif, XMP, IPTC, etcetera metadata tags. For 99% of the users this is all they will need.

#### jExifToolGUI #01: Create and use User defined Combinations
[plugin:youtube](https://youtu.be/FvTN-pMU7yM)
**Note:** The video is displayed by default in 1024x576 in 480p, but the maximum resolution is 1920x1080. (When playing select the gear icon in the bottom bar to set to 1080P and click the bottom right icon to play fullscreen)

This video shows the basis.
The tag names will not be stored in alphabetical order but in the order you created/saved them.
You can also cut/copy & paste tags: The second movie shows how to use Copy&Paste from (or to) other apps like spreadsheets (Excel, Google Spreadsheets, etc.) where you define your combinations.
#### jExifToolGUI #02: user combis copy paste
[plugin:youtube](https://youtu.be/8cXT2Aiy6bI)
Note: The video is displayed by default in 1024x576 in 480p, but the maximum resolution is 1920x1080. (When playing select the gear icon in the bottom bar to set to 1080P and click the bottom right icon to play fullscreen)

##### Creating non-existing tags to add to your images
Below only gives you a very brief overview what can be done.

Exiftool allows you to define metadata tags that "do not exist yet". For this you need to create a custom config file where you define those "brand new" metadata tags.
This is described at the [Exiftool site](https://exiftool.org/config.html)
Another example is delivered with jExifToolGUI itself. It is called _isadg-struct.cfg_ and is based on the isad(g) archiving standard (based on this xml scheme). The _isadg-struct.cfg_ I created can be found [here online](https://raw.githubusercontent.com/hvdwolf/jExifToolGUI/master/src/main/resources/isadg-struct.cfg), but it is also located in the jexiftoolgui_data folder inside your user home folder. (Just to make sure users do not corrupt this file, it is overwritten on every program start).
When wanting to use non-existing tags, you first create the cfg file containing these tags. Then you define your combination set in the Tools screen, based on the tagnames in your configuration file. Upon saving this set, you also use the file chooser to select the cfg file you created. jExifToolGUI will then copy the cfg file into the jexiftoolgui_data folder and will store the link between the tags and the configuration file in the database. When you want to use this combination set, jExifToolGUI will also use the configuration file (has to use the file otherwise the tags can't be written).
**Note:** Exiftool, thereby jExifToolGUI, can read those tags from the images at any time. You only need the config file when wanting to write the tags to your images.

## 5 Several menu options
In this chapter some of the menu options will be explained. Some because they are somewhat more complicated. Some other menus/screens because you might not know what the "usefullnes" is of these options.

### 5.1 Rename photos
jExifToolGUI gives you many options to rename your photos. These will explained here.
Inside the "striped" frame you see the options for dropdown boxes 1 and 2.
Renaming has 4 "subsections": the "prefix", the "suffix", "numbering" and the "extension" which give you for a filename "prefix_suffix_(numbering).extension".

* prefix: This is the first part of the name. You have 4 basic options to choose from, where the 2 dropboxes options are depicted in the striped frame. The "String" field gives you the option to give it any name you like with spaces (not supported: quotes, double-quotes, forward slashes, backward slashes, question marks, exclamation marks, colons and semicolons (and probably more "strange" characters).
* suffix: This is the second part of the name. You have (currently) 10 options to choose from where some are based on the metadata in your images (these might later change to a dropdown as well). Only remark here is that "${filename}" is the original filename your camera gives to the image like for example "DSC_1234.NEF" or "P10001234.JPG", etcetera.
* numbering: If you use a "name" (String) or "YearMonthDate", you might get images with the same name. To prevent this you can autonumber the images, giving e.g. "exiftool-001.jpg", "exiftool-002.jpg", etcetera.
* extension: You can't change the extension as such (a jpg is always a jpg). Some cameras/phones use uppercase extensions, other lowercase extensions. If this bothers you, you can simply change that here.

[![](https://hvdwolf.github.io/jExifToolGUI/manual/images/renamephotos.png)](https://hvdwolf.github.io/jExifToolGUI/manual/images/renamephotos.png)

### 5.2 Sidecar exports
Metadata for images and other file types can be stored in (exported to) separate metadata files. Exiftool supports and can create a number of these metadata files. The XMP "sidecar" file is probably the best know format. Other supported metadata file types are EXIF, XMP, MIE ("The only format that doesn't suck") and EXV. jExifToolGUI can export all contained metadata in images and other files that Exiftool supports, and this can be used via (Menu) "Metadata-> Export metadata". Supported formats are txt, tab, xml, html and csv.

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

! This manual will be worked on and slowly expand. It currently is in its infancy.

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