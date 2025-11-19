---
title: "Calvat Irish Vat Calcs For Invoices And Cheques"
source: "CALVAT Irish VAT calcs for invoices and cheques.docx"
tags: [Regional Operations]
version: "1.0"
last_updated: "2025-11-17"
short_description: "CalVat file is in every livestock sale folder to calculate the flat rate VAT top-up and determine how this is worked out"
long_description: "CalVat file is in every livestock sale folder to calculate the flat rate VAT top-up and determine how this is worked out. Different marts in Ireland view the calculation differently."
---

CalVat file is in every livestock sale folder to calculate the flat rate VAT top-up and determine how this is worked out. Different marts in Ireland view the calculation differently.

The file has 6 rows currently (August 2012) as shown above.

The VAT can be worked out on the gross or total depending on the 6th line of calvat. If deduct commission first is set to N the calc is:

4130 (gross) * .9541984 =  (NET) 3940.85

If 6th line set to Y the calc is:

4196.01 (total inc comm) * .9541984 =  (NET) 4003.83

The VAT element is the gross less the net or the total less the net depending on which way the 6th line is set.

2015.

Setup looks like this for buyers invoice side.

Seller Example Donegal

In your example

Gross 2960 * .9541984 = net 2824.427

Gross 2960 – net 2824.427 = VAT 135.573

VAT 135.573 – 2.08 = 133.5