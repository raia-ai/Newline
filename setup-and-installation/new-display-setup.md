---
title: "New Display Setup"
source: "NEW DISPLAY SETUP.pdf"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "NEW DISPLAY SETUP 3 Sections (1) ON THE SERVER (2) ON THE MEDIA PLAYER (3) ON THE LAPTOP ON THE SERVER In the folder below are the templates for..."
long_description: "3 Sections (1) ON THE SERVER (2) ON THE MEDIA PLAYER (3) ON THE LAPTOP"
---

                                              NEW DISPLAY SETUP

3 Sections (1) ON THE SERVER (2) ON THE MEDIA PLAYER (3) ON THE LAPTOP

ON THE SERVER

In the folder below are the templates for UK and Ireland. In this example I’ll use the UK template but
just do exactly the same with the Irish template.

\\nldc02\E\NEWLINESHARES\NEWNASDISPLAYSYSTEM




    •    Copy the DISPLAY SETUP.rar to the main server
    •    Inside the zipped folder is a “DISPLAYS” folder and “MYSQL” folder.
    •    Copy the mysql tables into the mysql on the server.
    •    Copy the DISPLAYS folder into the main folder (MASTER or MARKET) in nldata

Send the latest programs below from 14progs to nlprogs (use central)

    •    NASBEND, NLDBDEF, SALERING

Send all the dll’s and exes in the NASDISPLAYSYSTEM (14progs) to the main server nlprogs (use central)

Add the following key to SYSINFO in the mysql (using mysqlCC)

    •    NEWDISPLAYDLL = Y

ON THE MEIDA PLAYER

Copy the NASDISPLAYSYSTEM (14progs – nldc02) to c:\ of the media player

Right click the icon for NASDISPLAY and amend the properties to the xml file in the DISPLAYS folder in
the main folder you copied up to the server. Example below for a server called martserver and has a
master folder. It’s also set to look at ring1. The ring number will need to be changed if using more than
one ring, see later notes on ring2 setup.

C:\nasdisplaysystem\nasdisplay.exe \\martserver\master\displays\ring1\settings.xml

Also need to edit the Registry so it loads on reboot to the same as above

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Run]
"NasDisplaySystem"=" C:\nasdisplaysystem\nasdisplay.exe \\martserver\master\displays\ring1\settings.xml”
ON THE LAPTOP

Run nasclient from: www.newlineasp.com/installers/nasclient.exe

Salering settings:

    •   Make sure the display board is set to NEWLINE IP TV DISPLAY
    •   Under settings make sure you are set to the correct ring number, in this example, ring 1



That’s the main setup done but now need to do a few more bits before testing.

Need to amend the settings.xml to point to the correct server name and master/market folder. You
can do this in the software (see notes later) but find this an easy quick method for this part.

Open the settings.xml file you copied with the DISPLAYS folder.

Default path: \\martserver\master\displays\ring1\settings.xml

Then do a find and replace for the correct information for your server. Example below the server is
called testserver and it has a market main folder




Ok, you are now ready for testing.
Double click on the icon the media player, nothing else required now on media player as all config can
be done in NAS.

Go into sale ring on the laptop. You can now test the two basic layouts, Finished Grid and Store Grid.
Finished Grid is design to show one Animal at a time: Store Grid is designed to show many animals at
a time:




AMENDING THE LAYOUT OF THE DISPLAY




Click ok is for basic changes which the market can use to make simple changes.

Click on “Configure NasDisplaySystems” for newline admin changes (will show this below)




Note the screen below is also where to create more rings if they have more than one. I’d get one setup
first then copy it out to Ring2, Ring3, etc.

Ok, click Edit Config.




This opens the control editor.
Two parts to this, The Quick Editor or the Main more detailed editor




This allows you to update all the fonts, colours and bits on the layout with one click. See below for
font change.
The other method is for changing more complex things like the layout of data displayed. Not going
into detail as Ritchie has many documents on this already and a big area to cover but this is the location
you can now amend details for the display. Below example for Finished Grid, eartag.

Noticed the layout grid which is all table layout and pretty easy to understand.




Make sure you change your settings, the Media player will automatically reload with the new changes
after a few seconds of you saving the changes. It’s also takes a safe copy so you can go back.

There is a lot to the editing of this so please ask as it will do most stuff the clients request but we are
limited by sale ring with some bits.
