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
