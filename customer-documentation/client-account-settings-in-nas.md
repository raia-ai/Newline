---
title: "Client Account Settings In Nas"
source: "Client Account Settings in NAS.docx"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Intro: Some auctioneers operate a client account sale and bank account process under RICS rules"
long_description: "Some auctioneers operate a client account sale and bank account process under RICS rules."
---

Intro:

Some auctioneers operate a client account sale and bank account process under RICS rules.

http://www.rics.org/uk/

A "client account" is an account of a practice kept at a bank or building society for holding client money. When operating this way the auctioneer does not pay the seller for lots sold until the buyer has paid for the lot(s).

NAS Client Account Features:

There are features in NAS to help operate an auction in this way.

Setup –

The sales must be run under client account settings. To check the settings go to the system configuration menu.

Tick client bank account for sales that operate this way.

Tech Note:

Markname requires Y in client acc. Field

SYSINFO key – USINGCLIENTACCBLOCK = Y

Seller Statements –

Using this setting shows the user if the sellers lot(s) have been paid for.

If the user tries to produce a cheque or pay cash to the seller for lots that have not been paid for they get this message.

Reports –

The unpaid lots report shows which lots have not been paid for and therefore which lot the auction firm should not pay the seller out for yet under client account rules and procedures.

This report shows how many lots a seller has sold and how many of them are still unpaid. The user can double click on the row to view the seller statement.

Client Account Sale Closing –

The system prevents a sale being closed until all lots have been paid for.