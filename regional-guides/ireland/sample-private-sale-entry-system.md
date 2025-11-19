---
title: "Sample Private Sale Entry System"
source: "Sample Private Sale Entry System.docx"
tags: [Regional Operations]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Sample Private Sale Entry Screen with Keyboard on Panasonic Toughbook with a screen resolution of 1024 x 600 and the screen size is 7 inches"
long_description: "Sample Private Sale Entry Screen with Keyboard on Panasonic Toughbook with a screen resolution of 1024 x 600 and the screen size is 7 inches."
---

Sample Private Sale Entry Screen with Keyboard on Panasonic Toughbook with a screen resolution of 1024 x 600 and the screen size is 7 inches.

It has an auto rotate option so if the tablet is turned to portrait mode the screen will resize to the below.

There is a button on the front of the tablet to turn this feature off if the user wants to use the form in a particular orientation.

New Main Form Details.

Vendor / Purchaser Look up.

Option to search for a Vendor or Purchaser by Name, Phone Number or e-mail address. It will also be possible to find a customer by entering their JDE number in to the JDE number field on the Vendor or Purchaser details area.

This part of the screen will be the actual data entry screen for the transactions being sold.

The Section column is a drop down combo selection which will populate the details from the Sections table used in NAS.

The Animal Type Column is a drop down combo selection and will alter based on the Section selected from the first column. This information will be populated from the item type table used in NAS.

The Tally, Total Kgs and Price columns are free text entry columns so the rep can enter what they require in here.

The Per Head / Per Kilo column is a drop down combo selection with these two options in.

The Description is currently a free text input column but it could be designed to show a different form based on the section and item type selected so specific information can be obtained based on the item type being entered.

I think the information in the red box might need a bit of looking at so we can make this a bit simplified for the rep.

If the user presses the Signature button in either the Vendor area or Purchaser area then the system will display a form on screen so the rep can get the vendor or purchaser to sign the entry form. There is also a button for the PGGW rep to sign the form. All of these signatures will then be stored in a PDF as part of the lot information and sent back to the HQ server as part of the data transfer operation.

The below are the different parts of the process that we need to facilitate the private sale transaction process for the reps with their tablet computers.

Rep Log on Screen to identify which rep is using the device.

Tablet Update from HQ server. There would be an option to run this and this would update the latest customer changes so the customer database on the tablet was up to date. It would also update the sections and item types so these were up to date and had all the information that was at HQ. It might be useful to display any of the rep’s customers that have been updated as Closed or On Stop in case they were going to use them as buyers.

Option to Enter a Private Sale Transaction for the above form or the Prime Stock Form if this needs to be different.

Option to transfer the private sale transaction back to the HQ server. This would operate in background and try to connect when the device has a suitable network connection. The process will keep on trying to send the information until all transactions have been flagged as having been updated.

Option at HQ to view private sale transactions that have been entered by the rep and which are waiting to be updated to NAS and JDE. This would show a report of Seller, Lot details and buyer with the option to view any signatures. This would enable the HQ user to check that a transaction was not being processed for an account that had recently been closed or put on stop. If all transactions are ok the user can select the sale to update in NAS and process the information to print out invoices and account sale documents. This will then update JDE and the rep commission reports and KPI reports.

There will be an option in Central to view when each rep last connected to the data transfer service and also switch off the log in to the NAS rep tablet software so if a tablet is lost or stolen access to the application can be stopped the next time the unit has an internet connection.

Hopefully this covers all the steps required in the process.

I have a few questions on the operation and setup.

Do we need to number the private sale transactions with a unique number so the rep can quote the seller or buyer a unique number for that transaction?

Will there be e-mail available on the Tablet so the user can e-mail a copy of the private sale form to the buyer and seller?

Do we need to restrict the vendor name search to just displaying customers allocated to the rep logged on to the tablet?

If Yes to point 4 do we do the same for the purchaser or can the rep view all buyers?

What sort of data connection will the device have back to HQ?

Will the rep need to print out the form for the buyer or seller?

Do we need to force the rep to run the customer update so their customer database is not too out of date?