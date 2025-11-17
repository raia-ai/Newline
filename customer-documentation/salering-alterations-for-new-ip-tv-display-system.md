---
title: "Salering Alterations For New Ip Tv Display System"
source: "Salering Alterations for new IP TV Display System.docx"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Salering Alterations for new IP TV Display System Setup / Configuration Control Unit This unit needs to have a folder on all units called ad_hoc..."
long_description: "Salering Alterations for new IP TV Display System"
---

Salering Alterations for new IP TV Display System

Setup / Configuration

Control Unit

This unit needs to have a folder on all units called ad_hock_media/SALEDISPLAY + Sale Ring Number. This will be the folder that is used in the software to FTP file required TXT files. This is a Linux box that we are sending data to so case is important so this MUST be set up in lower case as per the above. For the Canteen display I think we should have a folder called CANTEEN + Sale Ring Number which each salering will update with a file called LOTNO  .TXT.

Salering

To use the new IP TV system you first need to set up the IP addresses for the different TV Control boxes and also the username and password for the main control unit. To do this you need to go in to Salering and select the Configuration option and then select the ‘Setup OneLan TV Settings’. This will display the following screen.

You enter the IP address in for the IP address of each unit driving the different TV’s in each of the salerings. You can also enter the IP address of the unit driving the display in the Canteen but currently the alterations to update this have not been completed.

You also need to enter the username and password for the main control unit.

If an IP Address is entered in to any of the salering boxes the program will then automatically default the display board to display board 1 which is the new IP TV Display board Option. I have replaced the old display board 1 with this new option to save adding even more display boards to the list as hopefully this is going to be the way of the future.

You also need to check that you have selected the correct salering number for this sale. Again this is in configuration from the main Salering menu and you then need to select the ‘Sale Ring Number’ option from the menu. This will display the following screen and you need to tick which salering the computer is in.

Sale Operation.

You should be able to check that the TV’s are updating correctly from the salering program by clicking on the display board top right of the screen and then clicking on TEST to get 7 lines of numbers to appear or click on CLEAR to clear the display.

The program creates the different lines to display as it does currently for the current display boards but then instead of converting this to a data string and sending this out of the relevant comm. port to the display board it create a TXT file on the C drive working folder for each of the lines to display. The program then connects to the IP address set up for that salering and FTP’s this file to the pre set folder in the control unit set up notes above. Once the file has been sent the program disconnects from the unit. It does this for each lot in the sale that needs to be displayed.

The TXT file is called RING + salering number + .TXT.

I have added a couple of new labels to the main salering screen to show the user the salering number they have selected for that sale and also the IP address for the TV display set for that salering. (See Below)

The user can amend the salering number if they have this set incorrectly by clicking on the salering label. This will display the salering selection form as per the above and allow the user to change the salering number for operation. Once this has been saved the salering number and IP address details above will alter to the new settings.

Program Code Alterations

There is a new sub called UpdateIPTVSystem which is run from updatesalelist and the sub that clears the board and the sub that sends a test message to the board.