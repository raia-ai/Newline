---
title: "Vb Ledger"
source: "VB Ledger.doc"
tags: [NIFAIS Integration]
version: "1.0"
last_updated: "2025-11-17"
short_description: "See Purchaser Record: Is/Was this: [pic] [pic] [pic] I need to know where to pick up the data for date last paid; paid since last statement an..."
long_description: "I need to know where to pick up the data for date last paid; paid since last statement and date last paid. Other than that I think the new VB changes to SIMPLE show all the required data and produce a printout."
---


See Purchaser Record:

Is/Was this:

[pic]

[pic]

[pic]

I need to know where to pick up the data for date last paid; paid since
last statement and date last paid. Other than that I think the new VB
changes to SIMPLE show all the required data and produce a printout.

At the moment there is no separate command line for this and the user needs
to double-click on the customer row to display this. I would anticipate we
need either a text box for the user just to enter the account number in, or
a full search option for purchasers with debts.

[pic]

There are options for the user to view the purchaser record by outstanding
debts or all debts, or between dates, or from a given record number or by a
given office or offices or all.

The user see the debt info as shown:

[pic]

The user can print or preview these details by clicking the Print button
and selecting landscape or porttrait.

[pic]

Transaction Payment:

The user selects the purchaser by double clicking the debt list grid and
the focus is taken to the payment type drop down combo option.

[pic]

The user can press enter if the user has paid by cheque and the focus goes
to the Enter Payment Value textbox.

Pay Account in Full:

If the full account balance is paid by the cheque, enter the value and
press return. The user will see.

[pic]

When the user clicks save these changes will be posted to the ledger (code
still to be done to save to the files).

Pay some debts from an account (Part-Pay):

Enter the payment value and press enter.

[pic]

The Amount Unallocated is made the same as the payment value, the focus
goes to  the payment date which defaults to today. Press enter to accept
this. The focus goes to the first pay column in the grid.

[pic]

Press enter or spacebar to tick this if you wish to pay this debt. If it
matches the unallocated amount the user will see.

[pic]

Click save to commit changes.

If there is more money to allocate the focus will move down to the next
debt to pay the user can keep pressing enter to pay the debts until there
is no more money to allocate or there is not enough to entirely pay a given
debt.

[pic]

If the user clicks yes the debt is part-paid.

[pic]

And a transaction balance is left against the second row in this example.

Over Pay:

If the payment value entered is greater than the account balance the user
sees:

[pic]

[pic]

This over pays the transaction balance.

Pay in Advance:

Enter the amount to pay and click the pay in advance tick box.

[pic]

The user is asked to confirm the amount to pay in advance.

[pic]

And an additional record is added to the grid. Click save to commit the
changes.

[pic]

Over pay to a specific record:

Pay the record and then click the save button whilst there is still
unallocated money.

[pic]

Do as prompted.

Transaction Input:

I’ve added a grid with the sections so the user knows which number to pick,
but I’ve not done anything more than that at present.
