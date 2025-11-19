---
title: "New Interest Charging System For Castleisland"
source: "New Interest Charging system for Castleisland.doc"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "New Interest Charging system for Castleisland"
long_description: "New Interest Charging system for Castleisland."
---


New Interest Charging system for Castleisland.

The NAS Sales Ledger menu has been altered so that now Option 4 looks like
this.
[pic]

If you select option for you get the following menu.

[pic]

To Calculate Interest on outstanding account you select option 1. This will
prompt you to enter a starting date. This is the date you want to start
charging interest and any transactions still outstanding prior to this date
will not have interest charged on them. You will then be prompted for an
end date. Again any transactions with a date newer than the date entered
here will not get interest charged on them. Therefore if you always want to
give buyers 2 week credit then always enter an end date 2 weeks before the
current date.

You then get prompted for an interest rate to charge and also the last 12
different interest rates set on the system.

You then get an option to enter a stock type to charge so if you press
RETURN to this prompt it will charge interest on all customers.

The last prompts are letter to start from and letter to end at. Once these
have been entered the program will run through all customer files and
calculate the interest on outstanding balances. These are written away to a
file in the master folder called INTFILE and it is 15 chars long.

View and Post Interest Calculated.
If you select this option you get the following screen with all the
interest calculated in option 1 visible for the user to view / print or
amend.

[pic]

You can make alterations to the list of interest charged and then click on
the save button to write this away to the file. If you make alterations to
the list and click on exit it will prompt you to save before exiting. Once
the user is happy with the interest being charged you can click on the
Update Ledger button and this will post the interest charged in the list to
the sales ledger. It will also at the same time create the sage nominal
file for updating Sage.

If the user wants a list of interest charged then they can click on the
print button.

Once the interest has been posted to the sales ledger the user can then
select the option to print buyer statements. This will print out statements
for outstanding transactions and will include the interest calculated in
this routine.


(Alterations that I still plan on doing.)
After the Sales Ledger update has been run to then automatically give the
user the option to print so that they have a report of what has been posted
to the sales ledger.

I then plan on deleting the interest file so that they cannot post the
amounts to the ledger more than once but will take a copy of the file so
that we can view this if required.



