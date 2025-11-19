---
title: "Nas Interface With Sage Line 50"
source: "NAS interface with Sage Line 50.doc"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Contents NAS interface with Sage Line 50 2 Sales Ledger Control Account: 2 Bank: 2 VAT: 3 Sales VAT Control Account: ..."
long_description: "Contents NAS interface with Sage Line 50 2"
---



Contents
NAS interface with Sage Line 50   2

  Sales Ledger Control Account:    2

  Bank:     2

  VAT:      3

   Sales VAT Control Account:     3

   Purchase VAT Control Account:  3

  Suspense/Holding Account:  3

  Debtors Control Account:   3

Double Entry T Accounts:     6

  SALES LEDGER CONTROL ACCOUNT – NOMINAL 4000s range     6

  BANK – NOMINAL 1200  6

  VAT Sales Control Account – NOMINAL 2200    6

  VAT Purchase Control Account – NOMINAL 2201 6

  Debtors Control Account – NOMINAL 1110 (May vary)      6

  Suspense Account – NOMINAL 9999 (May vary)  7

  Transfer Cheques to Sage for bank reconciliation in sage     7

How to import the files into sage?      8

  Sage setup in NAS    9










NAS interface with Sage Line 50



NAS will create a csv for import into sage line 50 after each auction is
archived into history. The csv posts various figures to sage nominals,
updating the nominal ledger in sage only.

See sample file below:

[pic]


Sales Ledger Control Account:

Commission may be recorded against one nominal in sage or it  may  be  split
into different nominals for the different  sections  (groups  of  goods  for
auction) in NAS. NAS can deal with either scenario. The example above  shows
different nominal codes used for each section set up in NAS. The  commission
nominals in sage will tend to be in the  4000s  range.  This  is  the  sales
side, i.e. the auctions income. It is a credit to the sales  ledger  control
account.


Bank:

Buyers/purchasers paying off debts is likely to be nominal 1200 in sage.
This is the bank nominal. This is a debit to the bank i.e. a payment
increasing the money in the bank.


VAT:


Sales VAT Control Account:

VAT on sales is likely to be posted against nominal 2200.


Purchase VAT Control Account:

VAT on purchases (sellers/vendors) is likely to be posted against nominal
2201.


Suspense/Holding Account:

The gross total of the vendors cheques is normally posted to nominal 9999.
A suspense account to balance off … ??




Debtors Control Account:

Unpaid bills/invoices will be posted as a  debit  to  the  nominal  for  the
debtors control account which may be something like 1110. This is  the  debt
owed to you by buyers/purchasers. This figure  will  agree  with  the  debts
posted to the NAS sales ledger during the archive process. This  helps  keep
the debtors nominal figure in agreement with the NAS sales ledger total.  In
addition to this figure posted at sale  close  NAS  creates  csv  files  for
import to sage when an old debt is paid off in the NAS sales  ledger  (after
auctions) or a debt is manually added to the sales ledger.

[pic]

£227,333.00 has been paid off  in  the  sales  ledger  in  NAS  through  the
transaction payment option. £194,348.33 has been paid by cheque. The  figure
is posted as a debit to the Bank nominal in sage.  It  is  a  journal  debit
(JD) to the bank nominal 1200. i.e. it is money the auction firm  is  paying
into the bank and increasing the funds in  the  bank  account.  This  figure
must balance to another account in sage, so a journal  credit  is  necessary
against the debtors control account 1110. This reduces the outstanding  debt
from the overall debt list, because the debt has been paid.

In the above example a cash payment or payments have been  made  which  also
reduces the outstanding debt  figure  but  is  posted  as  a  debit  against
another bank account or cash nominal.

[pic]

This shows the batch payment figure in the NAS sales ledger daybook.

Likewise if a debt is added manually to the NAS sales ledger it needs to  be
recorded in sage. The transaction input option in NAS  creates  a  csv  file
for sage.

[pic]

A manual credit  of  £7027.99  has  been  made  to  purchaser  number  S1797
possibly because he was invoiced in error for  purchaser  S199’s  purchases.
The debtors control account is therefore credited to  clear  the  debt  from
his account. It needs to be added to the debtors control account again as  a
journal debit though to reflect the debt of purchaser S199. If  a  debt  was
added to reflect a rent deal or something like that instead  of  an  account
adjustment then there would only be 2 lines in the example above.

[pic]






Double Entry T Accounts:


SALES LEDGER CONTROL ACCOUNT – NOMINAL 4000s range

|DR (DEBIT)  JD (Journal Debit)      |CONTROL ACCOUNT JC(Journal Credit)  |
|SALES LEDGER                        |CR(CREDIT)                          |
|                                    |Commission                          |
|                                    |                                    |



BANK – NOMINAL 1200

|DR                                  |                                    |
|BANK                                |CR                                  |
|Sale day payments                   |                                    |
|Old debt ledger payments            |                                    |


VAT Sales Control Account – NOMINAL 2200

|DR                                  |Control Account                     |
|VAT Sales                           |CR                                  |
|                                    |                                    |
|                                    |                                    |


VAT Purchase Control Account – NOMINAL 2201

|DR                                  |Control Account                     |
|VAT Purchase                        |CR                                  |
|                                    |                                    |
|                                    |                                    |


Debtors Control Account – NOMINAL 1110 (May vary)

|DR                                  |Control Account                     |
|Debtors                             |CR                                  |
|Unpaid bills/invoices               |Ledger Payments                     |
|Manually input debts                |                                    |


Suspense Account – NOMINAL 9999 (May vary)

|DR                                  |Control Account                     |
|Suspense                            |CR                                  |
|                                    |                                    |
|                                    |                                    |



Transfer Cheques to Sage for bank reconciliation in sage

NAS can produce a cheque file when archiving sales.

[pic]

This file has 2 nominal codes in each row. Nominal  1200  reduces  the  Bank
control account. It is a credit to the bank  control  account  reducing  the
money in the bank as  you  pay  out  a  cheque  to  the  seller/vendor.  The
suspense account 9999 is debited. This should then balance off the  suspense
account  credit  from  the  import  of  the  sale  nominal  file  previously
imported.






How to import the files into sage?



Log into sage.

[pic] [pic] [pic]

Click the File Menu and the Import option.

[pic]

[pic]

[pic]




Sage setup in NAS

Select 10 Auction System from the Main menu and select 3 View Sale
Settings.

[pic]

[pic]

Select one of the sales in the list.

[pic]

Click 4 Amend Charges, etc

[pic]

Click 3 Amend Nominal Codes

[pic]

Enter the 4 digit nominal codes from your sage system into the appropriate
NAS options show below. Save these changes and contact Newline to finish
setting up the csv export from NAS to sage when each sale is closed or a
debt is posted.

[pic]

-----------------------
1 Montpellier Terrace, Montpellier Road,
Torquay, Devon, TQ1 1BJ                       Tel: 0044(0) 1803 202140
                                   Fax: 0044(0) 1803 202148



Partners: D.R. Jones, BA
J.K.M Jones
S.D.W Jones, BA (Hons)
P.C.W Jones, BSc (Hons)


Vat No: 699 1408 89



E-mail:     info@newlineasp.com
Web:  www.newlineasp.com
      www.auctionmarts.com





