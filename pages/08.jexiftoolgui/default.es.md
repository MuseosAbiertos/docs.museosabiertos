---
title: jExifToolGUI
external_links:
    no_follow: true
---

# jExifToolGUI: a cross-platform java Swing gui for ExifTool


### Table of Contents

* 1 Overview
* 2 Versions and "Installation"
 * 2.1 Uninstall
* 3 Quick Start
* 4 Some Edit sub tabs further explained
 * 4.1 Geotagging
 * 4.2 Use Lenses and create lens templates for your lenses
 * 4.3 Create and use user defined metadata tag combinations
* 5 Several menu options
 * 5.1 Rename photos
 * 5.2 Sidecar exports
* 6 Preferences
* Appendix A GNU Free Documentation License 

# 1 Overview
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

#### Universal jar
* `jExifToolGUI.jar`: Just the bare jExifToolGUI.jar containing all dependencies. You need to have java version 8 (1.8) or newer installed on your system.
Start from a terminal with java -jar jExifToolGUI.jar &. This version should run on any system that comes included with java 8 or newer, or where you can install java 8 or newer. (Windows/Linux/MacOS (BSD*unix)/Solaris/AIX/HP*UX etc.)

#### Windows
*     `jExifToolGUI-<version>-win-x86_64_with-jre.zip`: A windows 64-bit executable including java V11. Unzip with paths!
*     `jExifToolGUI-<version>-win-x86_64.zip`: A windows 32/64 bit executable without java. You need java 8 (1.8) or newer installed on your system.

    Both versions do not come with installers. Simply unzip (with paths) to a folder of your liking and optionally create a shortcut on your desktop.
   
#### MacOS
* `jExifToolGUI-x86_64-macos-<version>-with_jre.dmg.zip`: A MacOS bundle including java V11. Note: Apple is very unfriendly to non-Apple stuff like java/perl and other software. This bundle IS a working Apple bundle but not entirely according Apple standards.
* `jExifToolGUI-x86_64-macos-<version>.dmg`: A MacOS bundle without java. You need java 8 (1.8) or newer installed on your system.

These are MacOS Application bundles. In case of the full version you first need to unzip it to get the dmg file. Open the dmg (by double-clicking it) and select it from the left navigation panel in your Finder where it will appear as a "virtual disk" (DMG Files are Mac-formatted Disk Image Files). Drag the "jExifToolGUI.app" bundle from the dmg into a folder of your liking where Applications is the most logical one.

**Note:** MacOS (the Gatekeeper software) does normally not allow applications to be started that do not originate from the AppStore or come from an "unidentified" developer (me). You need to add jExifToolGUI to the "list of exceptions". That is actually very simple. See Apple support

#### Linux 
* `jExifToolGUI-<version>.deb`: a Linux .deb package. For all Debian based systems (Debian/Ubuntu/Mint/MX Linux/Raspbian etc. etc.). This is a linux multi-architecture version as the relevant java V11 version for your system/architecture will be downloaded as dependency.
Use `sudo dpkg -i jexiftoolgui-<version>.deb` to install. As of that moment it will also appear in your menu.
* `jExifToolGUI-<version>-x86_64.AppImage`: Linux universal Appimage including java V11. Runs on every 64bit intel Linux system (and also inside Chromebook Linux beta).
Simpy do a `chmod +x jExifToolGUI-<version>-x86_64.AppImage and start with ./jExifToolGUI-<version>-x86_64.AppImage &.`


#### 2.1 Uninstall

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

## 4.3 Create and use user defined metadata tag combinations
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