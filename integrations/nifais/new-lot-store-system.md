---
title: "New Lot Store System"
source: "New lot store system.doc"
tags: [NIFAIS Integration]
version: "1.0"
last_updated: "2025-11-17"
short_description: "There is a new option on the main sale menu in NAS for FURN sales"
long_description: "There is a new option on the main sale menu in NAS for FURN sales. This is option 6 and is called Lot Store. This will then display the following menu."
---


New lot store system.

There is a new option on the main sale menu in NAS for FURN sales. This is
option 6 and is called Lot Store. This will then display the following
menu.

[pic]

Option 1 is currently not completed so will only display a message box to
this effect.

Option 2 is the option to move unsold lots from the current sale to a lot
store so that they can then be moved to any subsequent sale. This option
will display the following information for the user to select the lots that
they want to move to the Lot Store.

[pic]

This screen will display all unsold lots for the current sale, that have
not already been moved to the Lot Store and all lots are automatically
selected ready to be moved to the Lot Store. If you want to be selective
and not move all unsold lots to the Lot Store then click on the UnSelect
All button and this will de-select the lots ready for the user to select
the required ones. There are 3 different options as to what you want to do
with the un sold lots and these options are under the Status column. This
default to Move to Store if an unsold pass has not been printed for any
lots. If a pass out has been printed then this will default to ‘Returned to
Vendor’. The other option in this list is Skip / Dump.

Once the lots have been selected to Move then you should click on the
Update button and the system will move the selected lots to the store and
you will be informed that the lots have been moved sucessfully.

All of the columns are resizeable so you can view more of the vendor or lot
details if required.

The lots can be selected by either clicking on the selected column of
moving up and down the list and pressing the space bar.

Option 3 on the Lot Store Menu will display the following screen.

[pic]

This will list all the lots in the Lot Store with the Last Sale Date and
Lot number listed along with the Vendor details and the lot description. To
select the lots to move to the current sale you must enter the lot number
for the sale and this will then automatically tick the selected column. If
you scroll to the right of the screen you will see the last reserve price
and the last price guide. These can also be altered at this point when the
lot is being moved to the new sale.

Once the lots have been selected if you click on Update the system will
move the selected lots from the Lot Store to the current sale and inform
the user of the number of lots moved. These lots will then not appear in
the list of lots in the Lot Store the next time this option is run.

When the lots are removed from the Lot Store it updates a Lot Store
Movements table so that the system know how many times the lots are moved
to and from the Lot Store.

This option has the same three Status options along with one extra one and
this is Delete lot from Store. This will just remove the lot from the Lot
Store and flag the transaction that it has just been deleted and not moved.

When you are entering the new lot number for the new sale it will check to
make sure that this lot number has not already been entered for a lot in
the sale and inform the user if it has.

The system works on the basis that the item types are the same in the sales
where the lots are being moved. This is something that we can look into if
required at a later date but will mean more entry for the user.

Option 4 displays the same screens and information as Option 3. but I
thought it might save a few phone calls from people asking how to view lots
in the lot store. I might look at moving option 1 and option 4 to a button
on the main form along the top but this can come at a later date when we
have more time and more users using the system.


