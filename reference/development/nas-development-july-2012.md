---
title: "Nas Development July 2012"
source: "NAS Development July 2012.pdf"
tags: [Development and Technical]
version: "1.0"
last_updated: "2025-11-17"
short_description: "NAS Updates July 2012 • Lotstore o Additional checking to prevent duplicating lots from store into sale o Warning if..."
long_description: "• Lotstore o Additional checking to prevent duplicating lots from store into sale o Warning if adding new lot numbers to lotstore ready to transfer to a sale but then applying a filter • Sales Ledger o Option in Ireland mode to print herd no and flock no on payment receipts o Development begun on updating aged list of debtors option. New filter options. • Salering o New board type and layout for Dumfries..."
---

NAS Updates July 2012

    •   Lotstore
            o Additional checking to prevent duplicating lots from store into sale
            o Warning if adding new lot numbers to lotstore ready to transfer to a sale but then
                applying a filter
    •   Sales Ledger
            o Option in Ireland mode to print herd no and flock no on payment receipts
            o Development begun on updating aged list of debtors option. New filter options.
    •   Salering
            o New board type and layout for Dumfries
    •   Invoices
            o New print layout to show TB dates, FABBL no and weights clearer
            o Tidy’s up long descriptions on printouts
    •   Lot input Bugs
            o Changing seller using F1 did not clear TB Date
            o Manually adding lots to lotstore did not add short description
            o Temporary seller bug at remote sales on new db format
            o Increment to next lot no on furniture sales


Lotstore
When putting in new lot numbers to the lot store ready to transfer them into a sale if they
subsequently went to filter the store in some way the new lot numbers would disappear without
warning. A message box now warns the customer they have entered new lot numbers and they have
a yes no option to determine how they wish to proceed.

Duplicate lots could be entered from the store to the sale if the user added the same lot number to
the grid in the store. This has now been prevented. Also a bug existed if the user entered lot 10 with
a space after it in the lotstore and lot 10 existed in the sale this was being imported. The space is
now trimmed so a mistake like this will not be imported in error.

Sales ledger
The aged list of debtors option is being updated to match the rest of NAS it should be ready for
release in August.

Invoices
Amendments have been made to the system to show the TB dates on the invoices. There are options
in the menus to set this and further documentation with details on this update.
Salering
A new board type has been added to the suite of boards compatible with Newline.
