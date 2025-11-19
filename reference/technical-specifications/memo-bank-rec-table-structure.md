---
title: "Memo Bank Rec Table Structure"
source: "Memo - Bank Rec Table Structure.docx"
tags: [Overview and Introduction]
version: "1.0"
last_updated: "2025-11-17"
short_description: "NAS Bank Rec All individual bank transaction data is stored in the bankrec table"
long_description: "All individual bank transaction data is stored in the bankrec table."
---

NAS Bank Rec

All individual bank transaction data is stored in the bankrec table.

Bankrec

All end of sale (EOS) cheques and BACs records are posted to this table, either when the sale is closed or if the update is run before the sale is closed. Manually added records are added to this table for lodgements, debits and credits.

This has records for:

Cheques; lodgements; debits; credits and BACs

Bankinouttypes

These always have the same bankinoutid and this table is populated by default in NAS.

Bankrecbalances

This table stores the bank statement data. Start and end date. Opening and closing balances.

Bankcontrol

This table stores all the data for the monthly bank control account reconciliation.

Bankbacpayments

GROUPBACS = Y in sysinfo means the BACs payment from a sale is shown as one figure on the bank statement. This is written to the bankrec table as one record. Individual BACs records from the sale are written to the bankbacspayments table.

GROUPBACS=N in sysinfo means each individual BACs from a sale is written to the bankrec table and nothing written to the bankbacspayments table.

Bankaccounts

Stores the bank accounts or bank account that the auction uses.

Bankfilters

Custom filters can be setup to record transactions as a specific type.