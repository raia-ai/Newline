---
title: "Sample Private Sale Entry System Ver 2"
source: "Sample Private Sale Entry System Ver 2.pdf"
tags: [Regional Operations]
version: "1.0"
last_updated: "2025-11-17"
short_description: "REP PRIVATE SALE PROCESS 2013 Revision 1.2 Sample Private Sale Entry Screen with Keyboard on Panasonic ToughPad with a screen resolution of 1024 ..."
long_description: "Sample Private Sale Entry Screen with Keyboard on Panasonic ToughPad with a screen resolution of 1024 x 600 and the screen size is 7 inches."
---

                                                                     REP PRIVATE SALE PROCESS 2013

Revision 1.2

Sample Private Sale Entry Screen with Keyboard on Panasonic ToughPad with a screen resolution of
1024 x 600 and the screen size is 7 inches.




It has an auto rotate option so if the tablet is turned to portrait mode the screen will resize to the
below.
                                                                     REP PRIVATE SALE PROCESS 2013

There is a button on the front of the tablet to turn this feature off if the user wants to use the form
in a particular orientation.




New Main Form Details.

Vendor / Purchaser Look up.

Option to search for a Vendor or Purchaser by Name, Phone Number or e-mail address. It will also be
possible to find a customer by entering their JDE number in to the JDE number field on the Vendor or
Purchaser details area.




This part of the screen will be the actual data entry screen for the transactions being sold.

The Section column is a drop down combo selection which will populate the details from the
Sections table used in NAS.

The Animal Type Column is a drop down combo selection and will alter based on the Section selected
from the first column. This information will be populated from the item type table used in NAS.

The Tally, Total Kgs and Price columns are free text entry columns so the rep can enter what they
require in here.

The Per Head / Per Kilo column is a drop down combo selection with these two options in.
                                                                     REP PRIVATE SALE PROCESS 2013

The Description is currently a free text input column but it could be designed to show a different form
based on the section and item type selected so specific information can be obtained based on the
item type being entered. (This needs to be confirmed if required and if it is there will be extra
development costs to include this.)

I think the information in the red box might need a bit of looking at so we can make this a bit
simplified for the rep. (This needs to be checked and alterations made known to us so these can be
included in the new form.)

If the user presses the Signature button in either the Vendor area or Purchaser area then the system
will display a form on screen so the rep can get the vendor or purchaser to sign the entry form. There
is also a button for the PGGW rep to sign the form. All of these signatures will then be stored in a PDF
as part of the lot information and sent back to the HQ server as part of the data transfer operation.



The below are the different parts of the process that we need to facilitate the private sale
transaction process for the reps with their tablet computers.

    1. Rep Log on Screen to identify which rep is using the device. This will then load a new cut down
       menu screen applicable to the reps and their requirements. It will be designed using a few
       large buttons with the following options. New Private Sale Transaction, View Private Sale
       Transactions, Tablet Update.
    2. Tablet Update from HQ server. This option would update the latest customer changes so the
       customer database on the tablet was up to date. It would also update the sections and item
       types so these were up to date and had all the information that was at HQ. It will display any
       of the rep’s customers that have been updated as Closed or On Stop in case they were going
       to use them as buyers.
    3. Option to Enter a NEW Private Sale Transaction for the above form or the Prime Stock Form if
       this needs to be different. This will display an option for Private Sale or Prime Stock Form and
       once the user has selected the required input they would get the form on screen and would
       enter the details of the transaction. Once all the data is entered and saved to the Tablet
       database the system will check to see if it has a connection to HQ and if it does the transaction
       will be updated to HQ. If there is no connection to HQ then the tablet will continue to check
       for a connection, at a pre-set interval and once a connection is made transfer the data back
       to HQ. (See ** for more info on how the data transfer will work). Each private sale transaction
       will be automatically numbered with a numbering sequence based on the rep number
       following by a sequencial number e.g. 701006 would be the 6th private sale transaction
       entered on the system for rep 701. This numbering system will be run from HQ and will be
       passed back to the tablet and updated to the transaction when the transaction has been
       updated to the HQ server. The vendor and purchaser selection on the private sale entry form
       will be either by entering the JDE number for that person or by clicking on the search icon.
       This will display a form for the user to enter any of the following search details. Name, Initials,
       Address,Phone Number or email address. The initial search will be restricted to just customers
       allocated to that particular rep but if they cannot find the customer they are looking for they
       will be able to expand this out to search the whole database.
    4. The View Private Sale Transactions option will display a list of all private sale transactions
       entered by that rep that have not yet been confirmed. Until a lot has been confirm it will be
       possible for the rep to amend any of the details relating to that transaction and once the rep
       is happy everything has been completed they will mark the transaction as completed. This will
                                                                 REP PRIVATE SALE PROCESS 2013

   update a completed flag on the transaction and the system will download this completed
   transaction to HQ for processing.
5. There will be a report at HQ of all transactions entered by the reps that have not been updated
   as confirmed so the HQ users can see what transactions are in the process of being completed
   so if there are any queries relating to any of these transactions HQ users will be aware of them.
   It will also have a value against each pending transactions so this might be useful for the credit
   team.
6. There will also be an option at HQ to view private sale transactions that have been entered by
   the rep and sent back to HQ waiting to be updated to NAS and JDE. This would show a report
   of Seller, Lot details and buyer with the option to view any signatures. It would also show the
   date the record was sent back to HQ and also the date it was entered on the Tablet. This would
   enable the HQ user to check that a transaction was not being processed for an account that
   had recently been closed or put on stop. If all transactions are ok the user can select the sale
   to update in NAS and process the information to print out invoices and account sale
   documents. This will then update JDE and the rep commission reports and KPI reports.
7. There will be an option in Central to view when each rep last connected to the data transfer
   service and also switch off the log in to the NAS rep tablet software so if a tablet is lost or
   stolen access to the application can be stopped the next time the unit has an internet
   connection. This will be in a separate group from the saleyards.


    **
    The data transfer operation will be run via two services connecting to each other and moving
    the data from the Tablet computer directly in to the database on the HQ server. There will be
    a new service installed on the tablet computer that will try and connect to the service running
    on the HQ server. This service is already running on the HQ server and is used by the saleyards
    to send sale data back to HQ. There will be some modifications required to this service to
    update different details to different tables. Once the service on the tablet gets a connection
    to the service on the HQ service it will try and send a transaction back to HQ. If the record is
    successfully sent back the HQ service will return a success flag back to the service on the tablet
    and pass back the unique transaction number for this transaction. It will then move on to the
    next transaction and check that it still has a connection to HQ and if it does it will send the
    next transaction. If there is no connection to HQ it will keep trying every so many minutes
    (This can be set in a configuration option) and there will be an icon showing the connection
    status in the system tray on the tablet.

    Cost.
    The cost for the above operation based on the options required above will cost £12,600.00
    stirling. If there are additional options required or major alterations to the above
    requirements then I will need to re look at how this will effect the time I have costed and the
    cost might need to alter.

    I am not sure currenlty of any timescales that you might have on starting this process or when
    you would like to run tests with any pilot reps or when you expect to have the system running
    LIVE. If you have any of these details it would be really helpful if I can have a copy so I can
    factor these in to our current work schedule.
                                     REP PRIVATE SALE PROCESS 2013

Details of the Panasonic ToughPad.
