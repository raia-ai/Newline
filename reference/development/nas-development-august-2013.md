---
title: "Nas Development August 2013"
source: "NAS Development August 2013.docx"
tags: [Development and Technical]
version: "1.0"
last_updated: "2025-11-17"
short_description: "NAS Updates August 2013 Invoices option to block temporary customers from unpaids Third Party Cheques Record Lot Store tweaks Closed Account Wa..."
long_description: "Invoices option to block temporary customers from unpaids"
---

NAS Updates August 2013

Invoices option to block temporary customers from unpaids

Third Party Cheques Record

Lot Store tweaks

Closed Account Warning Message

Country Code Combo in Customer Account

AIM communication improvement

Batch Emails

Bug fix emailing copy invoices from ledger options

Configure Media Player Layouts

Cheques Different Postal Commission Rate

August sees a big improvement to handling pink communication errors with AIM when there are broadband issues. There are also some useful features to help with better credit control of temporary buyer accounts and more informative messages for customer account status.

Invoices – Block Temporary Accounts Having Unpaid

This option can be set by Newline staff. If it would be useful in your business please get in touch and we will set it for you. When a temporary buyer is created in salering or sell pre-booked lots a T for temp will be added to their customer account. See below.

The mart user can remove this if they want to, or it will be removed automatically when the sale is closed and temp becomes a permanent account. If the user tries to take out an unpaid invoice for a temp with a T against their account status the invoice program will warn them as below.

Third Party Cheques Record

The third party cheques recorded in paying an invoice will now be show separately in the  option.

Users can now edit chq no, sort code, etc straight into the grid.

Lot Store Tweaks

If you want to move a lot from the store to the sale it will check that the item type exists in that sale before allowing you to move it. It will not let you move a lot from the store recorded as an itemtype that does not exist in the sale in question.

Bug fix: The condition field was not being transferred from and to the lot store. It is now.

Closed Account Warning Message

If a customer account status is marked as C for closed the account will not be found in name searches or number searches but can be found from Customer List reports.

A customer search for this account number or name will prompt a warning message.

Country Codes

There are combo boxes to show the available country code on the customer account for the main account and under the invoice address and payment address tabs also. If these are empty you need Newline staff to run an update to populate this table.

AIM Communication Improvement

When NAS trys to communicate with AIM during eartag scanning a dip in the Internet connectivity may cause problems and create a pink error code. Newline have developed a method to auto correct this problem which should massively reduce pink errors.

Batch Emails

When sending out large email mailshots the system will now break them down and send in batches to reduce likelihood of email being seen as spam.

Bug Fix emailing copy invoices from ledger options

Users can now click the email copy option when they drill down to a copy invoice from the sales ledger and it will email the copy invoice. Previously it did nothing when clicked.

Configure Media Player Layouts

This option is currently under development and will let users change the layout, colour, font size, options of the media player layouts.

See separate documentation to describe detailed use of this app.

Cheques Different Postal Commission Rate

It is possible to offer sellers a deduction from their standard commission rates if they wait for a posted cheque rather than an immediate one on the day or BACs.