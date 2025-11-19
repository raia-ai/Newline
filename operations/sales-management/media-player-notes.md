---
title: "Media Player Notes"
source: "Media Player Notes.docx"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Newline buy in the media player box and change the hard drive for an SSD"
long_description: "Newline buy in the media player box and change the hard drive for an SSD. Windows 7 is then loaded."
---

Newline buy in the media player box and change the hard drive for an SSD. Windows 7 is then  loaded.

VLC Media player is installed (an app which supports webcams)

FTP Server is installed and configured (Filezilla Server). Configuration involves setting a username, password and data path to shared folders.

There is no installation image for the Media player at present so it is done manually. An image would speed up and standarise the  deployment process.

Salering:

Full Lot & Price / Sell Pre booked Lots:

One Lan:

Required FTP for moving data, and our media players are currently using FTP to move files also. However technically there is no need for the media players to use this method as they could browse for data on our server (salering and alinput would need to be amended to write data there). The benefit to making this change would be we do not need to install, configure or maintain FTP servers. There should be a timesaving and reduce the number of steps in the process.

In use -  Wallets Marts / NWA  (no further sales of On Lan product intended).

Newline Media Player:

Currently uses FTP method to move data from server to files on the media player to keep process the same as was used for the One Lan method. Worth considering changing this process as not technically necessary with the Newline Media Player solution.

Configuring the Media Player Display \ Screen:

Currently there is an xml file call settings.xml which has all the settings in for the number of rows and columns that comprise the screen layout. There is an F12 option to show a grid which shows the rows and columns. In the XML there are different controls which determine what type of object can be displayed and where it goes on the screen and where it gets data from. Such as the ImageControl has a path to the company logo, has the rows and columns position it is located in. The grid rows have different properties like auto, fill and fixed. Auto means the row will resize to fit the font size for text in the row. Fixed is a fixed height. Fill is set by a percentage of screen.

No Front End Configuration for screen layout:

There is no front-end configuration for the front end currently. It is possible to use XML editors like XML notepad to aid Newline edit the XML, but essentially it is very much like having to edit one of our tpl files. Manual process which requires high level skill set. Not something a user could do. Time consuming and should be taken into account in sales costing.

User Front End in NAS Add-Ins for adding text  /adverts:

The user can add a message / advert to display on the Media Player. They can set a start time and end time for the message to run.

Newline Process from Order to Working at client site:

Media Player hardware added at HQ (SSD)

Windows 7 installed

VLC Media Player installed

FTP Server Filezilla installed, configured

Graphics tailored for client

Media Player layout configured via settings.xml

Tested in-house

Sent to client site

Fitted in location by engineer

Salering or alinput settings set

Adverts configured in NAS add-ins

Tested by client and engineer

Media Player Uses:

Replace display boards in the rings

Display pre-booked cattle details

Display sheep from pre-booked lots or full lot and price

Display Last Lot info for sheep

Canteen display

Show current lot number in ring

Show last lot detail in ring

Show powerpoint presentations

Show adverts

Show messages

Show web cams