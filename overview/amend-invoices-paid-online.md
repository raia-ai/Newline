---
title: "Amend Invoices Paid Online"
source: "Amend Invoices Paid Online.pdf"
tags: [Overview and Introduction]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Amend Invoices Paid Online Date of document: 2025-03-10 There is a new feature where after importing any online payments for sale invoices, the ..."
long_description: "Amend Invoices Paid Online Date of document: 2025-03-10"
---

            Amend Invoices Paid Online
Date of document: 2025-03-10



There is a new feature where after importing any online payments for sale invoices, the system will
update the copy invoices with the payment details and outstanding status and then email the copies
to the relevant customers. This routine can also print the copies of the amended invoices.

By default, once the payment importing is finished, if there were any sale invoices paid off then this
screen will appear:




Choose Yes to print the copies, or No to not print the copies. The routine will then run through in
two phases – the first phase will go through and amend the copy invoices, then the second phase will
go back around and email (and print if set to do so) any invoices that were successfully amended.

Phase 1:
After doing the Amending phase, the system will then display the template email which will go out
with each emailed copy invoice:




Alter/amend this as desired, and click “F5 – Send Email” to carry on. The system will then
proceed to phase 2, where it will email out the amended copy invoices, and print them if this
was chosen.




Once done, the window will then close and return you to the online payments import screen.
The prompt to print copies can be changed through the System Info Config option in the Invoice
program.




There are three options for this:

-   Prompt Each Time
    This is the out-of-the-box default. The routine will prompt the user each time it is run.
-   Yes, print copies.
    If set to this, then the routine will not prompt the user at the beginning of a run and will just
    automatically print the copies of any amended invoices.
-   No, don’t print copies.
    If set to this, then the routine will not prompt the user at the beginning of a run and will not
    print any copies.
