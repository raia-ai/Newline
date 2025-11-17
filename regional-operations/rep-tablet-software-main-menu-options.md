---
title: "Rep Tablet Software Main Menu Options"
source: "Rep Tablet Software Main Menu Options.pdf"
tags: [Regional Operations]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Rep Tablet Software Menu Options"
long_description: "Rep Tablet Software Menu Options."
---

                      Rep Tablet Software Menu Options.

Main Menu.

Once the user has logged in to the software they will get this menu appear.




The two bigger buttons across the top of the menu are the options to enter NEW bookings in to the system.
If the user wants to view a booking already entered so they can confirm it or make alterations then they
need to select the Reports button. The Customer Update button will run the Customer Update option
which will update the tablet with any alterations made to existing customers and update any new
customers to the database on the tablet.
New Livestock Sale Docket.




The user will need to click on the Search Buttons to enter the search details that they want to use to find
the required Vendor or Purchaser. This will give the user the option to be able to search for a customer by
name, JDE Number, Phone Number or GST Number.
The Section and Item Type boxes are drop down combo boxes so the user will need to make a selection
from these boxes. They will not have the option to just type anything in here. The Item Type selection box
will only display the item types for the section selected.
If the user needs to enter a Grazing Transaction then if they click on the Grazing Button then the screen
will change to the below.




If the user clicks in the From or To Columns they will get the option to select the required date from a
calendar view. See below.
Once the From and To Dates have been entered the program will automatically calculate the Total Days.
Can you check we have the Total Days calculated as required.
When the user wants to specify which party is going to be doing the Nait Reporting if they click on the
PGGW to do NAIT move area they will get the below option appear.




If they press the PGGW to do the NAIT move they will then be prompted to enter the Fee and to check they
have a Vendor and Purchaser Nait ID entered. This is not required if Other Party Selected.
Once these details have been entered they will then show on the main screen as below.
The user would then enter the commission values to the vendor and purchaser in the relevant boxes and
select if this value is to be charged on a per head or % basis.
If there are any special condition to enter for this transaction they click on the Special Conditions button
and will get this screen appear.




Once all the details have been entered for the private sale or grazing transaction the user needs to click on
Save and the details will be saved to the database on the tablet. If the user is happy that everything on the
entry is correct and tallies have been confirmed then before saving they should click on the confirm button
bottom left and this will update this transaction has having been confirmed and will then appear in the
required reports at HQ. They will not then have to bring this record up again to confirm details but they
will not be able to amend any of the details again once they have updated the record to confirmed.
It is possible to enter any number of transactions on to the same entry form as long as the Nait details and
charges are the same for each record. See below for an example of 2 sheep transactions.
New Prime Stock Docket.




The information for the Meat Company and Plant drop down combo’s is entered via the Drafting Fee
system at HQ. Details below.
To add a Meat Company Plant you need to select the Meat Company Plants option above and this will
show this screen.




You then need to select the Meat Company from the Drop Down Combo on the right and then enter the
Plant name.
This will update the MeatCompanyPlants table on the HQ server. This information along with the
MeatCompany details are then updated to the tablet database when the remote user runs the Customer
Update option on the tablet.
Prime Drafting Fee Record entered.
You have to enter these records one at a time there is no multi entry option. When the record is saved the
program will keep the same Meat Company and Plant details in the boxes ready for the next entry. If you
go back to the main menu and back in to the prime stock entry screen then these details are lost.
If the details entered are correct and the rep knows it is ready to send back to HQ and update the Drafting
Fee System then if they click on Confirm Transaction the system will update this record as confirmed and
the rep will see the button change to the below.




Then when the user clicks on save they will get this message appear.
If the user changes their mind and does not want to save the details as confirmed then they should click
No and they will return back to the main entry screen. The user can then click on Confirmed and the button
will change back to ‘Confirm Transaction’.



Reports

The reports menu from the main screen will give the rep the chance to view details they have already
entered.
The report will give the user the option to view Unconfirmed or Confirmed records and it will give the user
a counter for the number of records in each group. If there are no Unconfirmed records to view then this
button will not be visible.




If you select the type of records you want to view you will then get the option of viewing Prime, Private
or Grazing.
Again if there are no records for a particular type you will not get that button to appear and there is a
counter of the number of records to view against each type.
Below is a report of Private Transactions.




You will see from the report that each transaction entered is shown as a separate row on the report even
if entered as part of a multi entry.
To view the transaction in detail you just need to select the required row in the report and you will get
the details back on the original entry screen.
It does not matter which of the two record on the report you select because they were entered on the
one original screen they will both show again together on the screen.



Data Transfer Operation.
There is a data transfer service currently running on the NAS HQ server that the saleyards use for sending
sales from the remote servers back to HQ and picking up sales from HQ. The tablet data transfer service
that runs on the tablet will connect to the data transfer service on the HQ server for sending information
back to the HQ server.
The service running on the tablet will check to see if there are any records in the local database that have
not been sent back to HQ and if there are then the service on the tablet will try and connect to the service
running on the HQ server. It will try and connect to the service using the connection method configured in
Windows and it will try and connect at a set interval. If the tablet can connect to the HQ service then it will
start to send any new transaction back to HQ. When the completed record has been received at HQ the
service will flag this transaction on the tablet as being updated and move to the next record. If during the
transfer the connection is lost then this record is not update and the service will try and send it again the
next time it has a connection to HQ.
The transfer operation will display an icon in the system tray to tell the user the current state of play.
There are three different icons depending upon the current operation.




If you click on the icon you will get a screen appear that will give you more details if there is an error.




When a transaction has been successfully sent back to HQ it will get a Docket Number and this will show
up on the report screen on the tablet and also at the top of the screen if the user is reviewing an updated
record.
