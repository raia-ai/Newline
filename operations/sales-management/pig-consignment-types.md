---
title: "Pig Consignment Types"
source: "Pig Consignment Types.docx"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "New Pig Consignment Type Input There is a new option when entering pigs for the user to enter the Consignment Type so when reporting the movement ..."
long_description: "There is a new option when entering pigs for the user to enter the Consignment Type so when reporting the movement details to BPEX via the eAML web service the XML contains the Consignment Type which will trigger if the Trichinella test is required."
---

New Pig Consignment Type Input

There is a new option when entering pigs for the user to enter the Consignment Type so when reporting the movement details to BPEX via the eAML web service the XML contains the Consignment Type which will trigger if the Trichinella test is required.

There is a new table in the def so we can store the different Consignment types as required and currently I think we just need to have Controlled and Non Controlled. The table is called PigConsignmentTypes.

If this table does not exist or there are no records in the table then the system will operate as it does currently.

Lot Input

If there are records in this new table then these will be displayed on screen as below.

This will default to Controlled if this is the first record in the table so the user should not have to amend this very often. If they need to amend this then they just need to click on the combo and amend to the Consignment type required.

This updates the ExportStatus on the transaction as currently this field is not actually used for Pigs but is in rest of the system.

Invoices

When printing the invoices for the pigs the system generates the XML required for the movement reporting for sending to the BPEX web service. This XML will now have an additional node in it for FCI Information.

This information is only generated for movements from Market to Slaughter.

The program will check all the different Consignment types for the transactions on the invoice and if they are all the same then it will look up the Consignment Description from the new table and add this to the XML file in the ConsignmentType Node.

If the Consignment types are different on the invoice then the system will update the Consignment Type node with Mixed.

If the Consignment Types are all 0, means that the system is not set up on this server, then the system will just add a blank node to the ConsignmentType Node.