---
title: "Salering Next Lot Option And Lot Edit Option"
source: "Salering Next Lot Option and Lot Edit Option.pdf"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "New Salering Next Lot Option and Lot Edit Option New Next Lot Option There is a new sysinfo setting to trigger the new Next Lot Input screen in S..."
long_description: "New Salering Next Lot Option and Lot Edit Option"
---

               New Salering Next Lot Option and Lot Edit Option


New Next Lot Option
There is a new sysinfo setting to trigger the new Next Lot Input screen in Salering. The key is called
USINGNEWSALERINGSCREEN and just needs to be set to Y. If this key is there then after selecting the
section and other start up options the Salering screen will display as per the below.




This has a new blue box across the top of the screen for the user to be able to enter the next weight
and lot number while having full access to the main selling screen so they can enter Remarks or do
anything else as required.

The new options are not available until the user has clicked on Start Sale. Once they have they can
enter the next lot number in to the Lot Number box and click on Next Lot and the system will bring
this lot in to the main salering screen and display on the display.

When the user types in the next lot number the program will look up the lot details and display the
number of heads in the Heads box next to the lot number.

The rest of the salering process is the same as before. If there is no lot number to type in to the next
lot box then the user can just click on Next Lot and the program will allow them to enter the price
and purchaser for the lot being sold and take the user back to the next lot number box once this
information has been entered.

New Lot Edit Option
There is a new option to amend basic lot details in the salering screen. Once a lot has been sold and
it appears in the grid bottom right of the screen the user can double click on any lot in this grid and
they will get this new Lot Edit screen.
This will allow the user to be able to amend the Weight, Selling Price, Grade, Breed, Remarks and
Purchaser. If the lot was originally unsold the user can amend the price and buyer.

It is not possible to split a batch of cattle in this edit screen or amend the seller.

New Stored Remarks Option.
There is a new option in Salering to enable the user to set up a standard list of remarks for different
sections and markets. This option is on the initial setup screen under the configuration option called
Setup Standard Remarks.

This option will then display the following screen.




The program will automatically tick the section and market that the user is already in and display on
the right any remarks already set up for this sale.

The user then enters the standard remark required and clicks on Save and the details are written
away to the table SaleringRemarks.
You then end up with a screen something like this.




Then when in the selling process if the user wants to enter a remark against the current lot in the
ring they press F4 and will get the following screen.




This drop down list will display all the standard remarks for that section and market and the user can
select from the list. If the remarks they want to enter is not in the list then the user can just type the
remarks in to the text box and the remarks will be saved to that lot.

If the user has clicked on Next Lot and brought the next lot in to the main selling screen then the
user can press SHIFT + F4 and enter /remarks for the last lot where the user is entering the price and
buyer information.




Important
This new option will not work with a direct connection to a weighbridge so this has to be
run with this option not in SYSINFO.
