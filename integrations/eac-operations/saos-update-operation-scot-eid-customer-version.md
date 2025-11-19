---
title: "Saos Update Operation Scot Eid Customer Version"
source: "SAOS Update Operation Scot EID Customer Version.docx"
tags: [Export Assembly Centre (EAC) Operations]
version: "1.0"
last_updated: "2025-11-17"
short_description: "SAOS Update Operation"
long_description: "There are two different web services for the SAOS update. One of them updates the Lot Number and all the EID tag numbers and the other one updates the Lot Number, Sale Date and holding numbers of where the sheep were read, where the sheep came from and where the sheep are going to."
---

SAOS Update Operation.

There are two different web services for the SAOS update. One of them updates the Lot Number and all the EID tag numbers and the other one updates the Lot Number, Sale Date and holding numbers of where the sheep were read, where the sheep came from and where the sheep are going to.

Race Reading Real Time Update.

There is a new option in the race reading option to send the lot number and eid tag numbers to SAOS.  This option can be turned on / off from the Configuration Menu on the main Race Reading screen. If you select the configuration option and then SAOS Settings you will get the following screen appear.

This has the user details and password to allow access to the Scot EID web site and these details will need to be sent to us from Scot EID. If the Realtime Update is ticked then the race reading option will run this web service each time the user presses the end lot button on the screen shot below. This option can be turned off at anytime so if there is a problem sending details to SAOS the user can untick this option and then send the details to them later.

There is an SAOS status display at the top of the race reading form that will alter depending upon if the user has ticked the Real Time SAOS update.

When the program is sending tag details to SAOS is will display ‘Sending Tags to SAOS’ and then if the details have been send successfully the caption will display ‘Tag Details Sent to SAOS’ and if there is a problem with the sending the caption will display ‘Problem Sending this Lot to SAOS’

After Sale SAOS Update.

This option will display all the lots in the current sale and show the current SAOS Status so the user can see which lots have been sent to SAOS and which ones still need to be updated.

This option can be found in the  and

This program will list all the lots in the sale and display the holding number of where they have come from and where they have gone to. It also shows the number of tags read in each lot and the number of heads entered in each lot. If the number of reads match the number of heads then these cells will display as green. See screen below.

There are a number of totals at the top of the screen to show the number of eid tags read and the number of sheep in each of the lots with a tag read. It also shows the % of sheep read with EID tags compared with the total number of sheep in a lot with an EID tagged sheep. It also shows the % of lots read 100%.

There is an Updated field after the To Holding and this will display the status of the lot with regard to what information has been sent to SAOS. If all the details for the lot have been sent to SAOS then this cell will display ‘Complete Lot Sent’ so there is nothing else to do with this lot. If the cell shows ‘Only Tags Sent’ then this means that the eartags have been sent to SAOS but the system still needs to send the holding details for the lot and flag the fact that the lot is complete. If nothing has been sent to SAOS then this cell will display ‘Nothing Sent’.

When sending the details to SAOS the program will run through the grid and try and send all the in complete lot details first e.g. just the lot number and eid tag numbers and then once all of these have been sent it will then go through all the records in the grid and send the complete lot details. For each lot sent we will get a reply message back from SAOS to say if all ok or not and if there is a problem they send back information on what the problem is. If the lot is sent successfully then the program will amend the Updated cell to ‘Complete Lot Sent’ and there will be just an OK in the reply cell. If there is a problem sending the details to SAOS then we will get the problem sent back in the reply and the program will display the problems in the Reply cell. It will leave the status as it was before trying to send.

If you want to see any of the ear tag numbers in a lot then you can double click on any of the rows in the grid and the program will then display the screen below.

This screen will display all the individual ear tag numbers in a lot with the date and time that the sheep were read. This will be useful to identify if the user has forgotten to press the end lot button and read two lots of sheep in to the same lot. You can see from the above that the last 8 sheep here should have been read in lot 808A and not 808 as you can see that the time read is 30 seconds later than the rest of the reads in this lot. You can also see from the list of lots screen that the system says there are 10 sheep in lot 808 and 9 sheep in lot 808A so this would also highlight the fact that the user might have made a mistake here.

To correct this the user can amend the lot number for these 8 ear tags in the list to 808A and this will update the main lot list as below.

List of all EID Tags Number Read.

If you click on the View Menu option at the top of the screen you have the option to view All the Tags entered for the sale or view the details by Lot. The program when first run will display the information on screen by lot but you can switch this to all tags but selecting the All Tags Option. If this option is selected then the system will display the information as per the screen below.

The tags are listed in time read order so it should be easy to see if anything has been allocated to a lot number out of order.

There could be a possible problem with the lots on the screen shot below as the lot numbers jump from 687 to 415 and then back to 699. See screen below.