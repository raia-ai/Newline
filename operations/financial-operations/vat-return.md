---
title: "Vat Return"
source: "VAT Return.docx"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Q The total value of sales, excluding VAT (Box 6) does not agree with my Sales Daybooks"
long_description: "Q The total value of sales, excluding VAT (Box 6) does not agree with my Sales Daybooks. Why is this?"
---

Q   The total value of sales, excluding VAT (Box 6) does not agree with my Sales Daybooks. Why is this?

A   This may be due to the way Box 6 is calculated. The figure is made up of net sales invoices minus net sales credit notes and it also takes into account Bank Receipts, Cash Receipts, Credit Card Receipts and Journal Credits posted with tax codes between T0 to T8.

You may have posted some journals with a tax code T0 instead of tax code T9. The easiest way to find out is to display the VAT Return, choose Box 6, by double-clicking or pressing ENTER on the total, to show you the breakdown of the total into transaction type and tax code. 

Double-click on the amount and it will even show you the individual transactions. If you have posted transactions with T0 instead of T9, T9 being reserved for transactions not applicable to the VAT Return, for example salary journals, then you can change the tax code using your software’s error corrections option.

Which boxes the tax codes affect on the VAT Return

Note: This table is for Standard VAT accounting and VAT Cash Accounting only. If you are using Sage 50 Accounts 2011 and UK Flat Rate - Invoice Based please refer to article 26095 . If you are using Sage 50 Accounts 2011 and UK Flat Rate - Cash Based please refer to article 26097 .

Sage default tax codes

In Sage to view or amend the tax codes open the Settings menu, choose Configuration then click Tax Codes.

Example of our nominal file for export to Sage. See T9’s should be T1’s?