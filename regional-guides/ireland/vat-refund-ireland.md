---
title: "Vat Refund Ireland"
source: "VAT REFUND IRELAND.docx"
tags: [Regional Operations]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Intro: NI or UK buyers purchasing livestock from Irish marts are exempt from VAT on the livestock if they prove they have exported the animals"
long_description: "NI or UK buyers purchasing livestock from Irish marts are exempt from VAT on the livestock if they prove they have exported the animals."
---

Intro:

NI or UK buyers purchasing livestock from Irish marts are exempt from VAT on the livestock if they prove they have exported the animals.

How can this be setup in NAS?

Set up an other deduction called:

VAT REFUND (for example)

Set sysinfo key:

EXPORTVATCHARGENO and whatever number the charge is in the otherdes file.

Any buyer that has a VAT number beginning with U will have a VAT Refund automatically added to the invoice.