---
title: jExifToolGUI
---

jExifToolGUI: a cross-platform java Swing gui for ExifTool
Table of Contents
1 [Chapter 1](#chapter-3)
2 Versions and "Installation"
2.1 Uninstall
3 Quick Start
4 Some Edit sub tabs further explained
4.1 Geotagging
4.2 Use Lenses and create lens templates for your lenses
4.3 Create and use user defined metadata tag combinations
5 Several menu options
5.1 Rename photos
5.2 Sidecar exports
6 Preferences
Appendix A GNU Free Documentation License


# 1 Overview
**jExifToolGUI** is a java Swing program that reads and writes metadata from files, predominantly image files. It has some preformatted screens for exif, gps/location, xmp, gpano (and a very limited set of IPTC) tags to write/read from/to image files using **ExifTool** and it also supports geotagging. Next to that you can define your own combination of metadata tags to write to your images. This gives you the option to use any tag that Exiftool supports. Next to that you can also define "brand new" non-existing tags that can be added to your files using a user-defined configuration file and user define tag combination. jExifToolGUI: j for java, GUI for Graphical User Interface to ExifTool.

jExifToolGUI is only a graphical frontend for the excellent open source Perl command line ExifTool by Phil Harvey. ExifTool is the real "engine", but as it is a command-line tool it is to some users less userfriendly. jExifToolGUI is built around exiftool and tries to give a lot of funtionalities and flexibility without you having to remember every command line parameter. jExifToolGUI only implements part of the functionality of ExifTool. It is definitely not a complete GUI for Exiftool and can certainly not replace it (if only that ExifTool is still the engine "under the hood").

This program is Open Source and completely free and will always stay that way, but you can donate any amount to me to show your appreciation if you continue to use it (after all it took a lot of hours/days to write it). See the Help menu in the program or click here.

And when it comes to donation, the same is off course valid for ExifTool itself. For donation to exiftool (Phil Harvey), see here.

This manual and the jExifToolGUI version might not always run synchronously. If new functionality is added to the program which requires a new chapter or paragraph, the manual will be updated for that new section. However, not all parts of the manual will/might be updated which might lead to older program screens in the manual that might slightly deviate from the program version you will be working with.
Note also that you will see screen captures from several operating systems (Linux/Windows/MacOS) and/or window managers (on Linux).

**This manual will be worked on and slowly expand. It currently is in its infancy.
**
