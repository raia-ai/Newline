---
title: "Calf System Using Nait Id"
source: "Calf System Using NAIT ID.pdf"
tags: [Regional Operations]
version: "1.0"
last_updated: "2025-11-17"
short_description: "New Calf System Using NAIT Ids and EID Tags"
long_description: "New Calf System Using NAIT Ids and EID Tags."
---

                    New Calf System Using NAIT Ids and EID Tags.

Step 1
Calves come in to sale yard and are unloaded by the seller. Before the calves are sorted and penned
in to their selling groups the NAIT EID tag needs to be scanned in to the reader and one of the 4 data
fields populated with one of the following vendor identifiers. NAIT ID, AHD number,Lams No or
Unique ID. When all the calves for that Seller have been scanned in to the reader the operator
presses F2 to end that session and can then press F1 to start the next session and enter the details
for the next seller. This information is stored on the reader ready for transfer back to the server in
the office when ready.

When suitable the EID reader is taken to the office and plugged in to a computer using the USB cable
that came with the reader. The user will then select the new option to Download EID tags from
Reader.




This will display the screen below and when the user clicks on the ‘Get Reader ID’ button the
program will go and search for the reader. The program will search for a reader 20 times so if the
reader is not switched on when the user clicks on this button they can still switch it one while it is
searching and it should then be found. If the reader is not attached to the computer or switched on
while the program is searching you will get the message ‘No EID Reader Found’. Once the program
has found a reader connected to the computer and it will display the reader ID on screen so the user
knows which reader they are connected to and that they are connected correctly before trying to
download tags. See below.




The user will then click on the option to Download Tags. The program will then download all the tag
details from the reader. While it is downloading the user should see the following screen with the
Session ID currently being downloaded.
When the download has completed the system will display the number of sessions and tags
downloaded from the reader on the screen. See Below




If all looks correct and all tags have been downloaded from the reader then the tag details need to
be deleted from the reader so they are not downloaded again the next time the reader comes in to
the office. (Do you want the program to do this automatically Ian or will you get the user to do this
via the reader menu?)

Once all the tags are deleted from the reader the reader can be unplugged from the computer and
taken outside for more tags to be scanned.


This means we now have a lot of EID tag numbers and Seller Nait ID’s or Seller Names in the current
sale that need Lams Numbers allocated against them. To do this you go to Step 2
Step 2
The user will select option 6 from the EID menu below.




This will display a list of all the sellers that we have downloaded EID tags for in the current sale. If
there is a Lams Number already entered in the Lams Number column then this means that these
sellers have already been crossed referenced so it is just the rows without a number allocated
against them that need matching. See Below.




If you know the Lams Number for the customer in the grid you can just type it in to the Lams No
column against the row you are working on and this will update the record accordingly. If however
you do not know the Lams number for a customer you can either Press F1 to Search for a Customer
or Click on File and then Search.

If you select this option you will get the normal customer search screen appear and you can then
search for a customer using any of the normal search options. See Below.




Once you have found the customer you are searching for you need to exit the Customer look up
screen and type the Lams Number in to the grid for the customer you are working on.

Once all the sellers in the grid are allocated a Lams Number you are ready to progress to Step 4. You
cannot process any calves in Step 4 without allocating a Lams Number to the seller of anyone with
Calves that you are going to download in Step 4. You do not however need to allocate all sellers a
Lams Number before progressing to Step 4.



Step 3
When the calves are sold the Lot Number is entered in to the EID reader and the eid tags are
scanned of the calves being sold. This information is stored on the EID reader ready for taking to the
office for downloading. The lot number entered in to the reader MUST be the same as the lot
number written down on the sale sheets with the price and buyer details so this can be matched up
later in the process.

Step 4
The EID reader is taken back to the office when suitable and plugged in to the computer using the
same cable as in Step 1. The user will then select the same option as in Step 1. The process is exactly
the same as Step 1. The program will then download all the EID data from the reader and do the
following. First it will check to see if there are any new Step 1 records that have not been updated to
the sale. This will mean that the system can deal with sold and pre entered records at the same time.
Once all the pre entered records have been downloaded, if there are any, the system will process
the sold records. To do this the program takes the Pen Number and EID tag number from the reader
and looks these up the EID tag from the new table populated at point 1 to get the seller LAMS
number. If no LAMS number found then the system will use the default calf account for that sale
yard.

When the seller number has been found the program will then check to make sure that this EID tag
number is not already entered in to the current sale and if not automatically create a LAMS
transaction with the seller, lot number, item type and tag number ready for the sale sheet to come
back to the office and the price and buyer to be entered.

This new process will have all the calves that have been sold together entered with the same lot
number so when selling the calves all the user has to do is enter the lot number, price and buyer and
the program will sell all the calves at the same time thereby speeding up the selling process. To do
this you will need to make sure you have the following options set for the calf section.
You will need to UN tick lot checking and tick Auto Sell Same Lot Number.
