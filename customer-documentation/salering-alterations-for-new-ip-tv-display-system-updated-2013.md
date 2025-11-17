---
title: "Salering Alterations For New Ip Tv Display System Updated 2013"
source: "Salering Alterations for new IP TV Display System - Updated 2013.docx"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Salering Alterations for IP TV Display System (version 7.0.401) Setup / Configuration Salering To use the Newline Media Player IP TV system you ..."
long_description: "Salering Alterations for IP TV Display System (version 7.0.401)"
---

Salering Alterations for IP TV Display System (version 7.0.401)

Setup / Configuration

Salering

To use the Newline Media Player IP TV system you first need to set up the IP addresses for the media player(s) and also the ftp username and password for the media player(s). To do this you need to go in to Salering and select the Configuration option and then select the ‘Setup Newline Display TV Settings’.

This will display the following screen.

The user enters the IP address for each media player driving the different TV’s in each of the salerings. You can also enter the IP address of the media player driving the display in the Canteen. The user must specify which office / site  / sale they are setting the media player up for. This provides flexibility for roaving laptop scenarios.

You also need to enter the ftp username and password for the main control unit.

If an IP Address is entered in to any of the salering boxes the program will then automatically default the display board to display board 1 which is the new IP TV Display board Option.

The user must select the correct salering number when using the salering with media players. They can check this by looking at the label top right hand corner on the main salering screen. They can click it to amend it.

Sale Operation.

You should be able to check that the TV’s are updating correctly from the salering program by clicking on the display board top right of the screen and then clicking on TEST to get 7 lines of numbers to appear or click on CLEAR to clear the display.

The program creates the different lines to display as it does currently for the current display boards but then instead of converting this to a data string and sending this out of the relevant comm. port to the display board it create a TXT file on the C drive working folder for each of the lines to display. The program then connects to the IP address set up for that salering and FTP’s this file to the pre set folder in the control unit set up notes above. Once the file has been sent the program disconnects from the unit. It does this for each lot in the sale that needs to be displayed.

The TXT file is called RING + salering number + .TXT.

I have added a couple of new labels to the main salering screen to show the user the salering number they have selected for that sale and also the IP address for the TV display set for that salering. (See Below)

The user can amend the salering number if they have this set incorrectly by clicking on the salering label. This will display the salering selection form as per the above and allow the user to change the salering number for operation. Once this has been saved the salering number and IP address details above will alter to the new settings.

Tech Notes:

Table

IPDeviceAddresses stores this data in the site database. The data is based on unittype, e.g. D for display, C for canteen, W for weighbidge. Market No which corresponds to the office number and IP address.

Program Code Alterations

There is a new sub called UpdateIPTVSystem which is run from updatesalelist and the sub that clears the board and the sub that sends a test message to the board.

Control Unit

This unit needs to have a folder on all units called ad_hock_media/SALEDISPLAY + Sale Ring Number. This will be the folder that is used in the software to FTP file required TXT files. This is a Linux box that we are sending data to so case is important so this MUST be set up in lower case as per the above. For the Canteen display I think we should have a folder called CANTEEN + Sale Ring Number which each salering will update with a file called LOTNO  .TXT.