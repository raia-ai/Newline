---
title: "Bank Rec Auto Match Bank Reconciliation Inc Bacs"
source: "Bank Rec Auto Match Bank Reconciliation inc BACs.docx"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Auto Match Cheques There is a facility in NAS to auto match cheques using a bank statement file downloaded from the auction firms online banking w..."
long_description: "There is a facility in NAS to auto match cheques using a bank statement file downloaded from the auction firms online banking website. In 2018 Newline have added an auto match credits, debits and lodgements as well from the bank statement download. In 2019 BACs functionality has been added."
---

Auto Match Cheques

There is a facility in NAS to auto match cheques using a bank statement file downloaded from the auction firms online banking website. In 2018 Newline have added an auto match credits, debits and lodgements as well from the bank statement download. In 2019 BACs functionality has been added.

Bank Reconciliation

Select the correct bank account from the drop-down list. Enter the statement date and statement number you want to auto reconcile and enter the opening and closing balance.

Auto Match Statement

Select auto match statement.

Browse to the file you have downloaded from the bank website and click the open button.

The user is warned if they have tried to import the file already.

Matched Cheques

The system will show the user which cheques it can auto match. Any differences are highlighted with a red background. The bank value is data from the bank the comp value is the data in NAS. These should be the same but if they are different you need to work out why. You may need to talk to your bank.

The system will through up a warning message if you have matched some of these cheques before or have bank differences.

Cheques Not Found

There is also a list of cheques not found. These have gone through the bank but may not be in your system. You may need to add these manually to the system and then match them.

Bank Differences

The bank differences are highlighted in red and status shows as “Difference”. When the user clicks the Update button they will see a msgbox each time a row has a difference. The system can automatch the difference and store the bank value in the system and use it to match the statement. Alternatively you may prefer to not auto match differences and handle it manually by adding a credit or debit and notes accordingly. The choice is yours.

Other Debits & Credits

Other debits and credits that are note cheque payments will be shown in the debits and credits grid, with totals. This can be printed out.

Update Jan 2018 –

New column shows a computer column which matches by value in debits or credits manually added to the bank rec against the bank statement.

An ID from the database shows ones that can be matched. When you click update you will be prompted do you want to auto update debits and credits. If you click yes these will be matched automatically to the statement. The ones with no value with a bold red background are not in the database and need to be manually added.

Update date April 2019 –

Added a BCs value and BACs date column. If there is a BACs value from the end of sale process in the system the comp val will be set and agree with the BACs value. This will auto match the BACs records.

Update Matched Cheques

If everything looks ok and is as you require it you can click update.

This will then auto match the cheques downloaded against the statement you set up.

You can print off what you’ve done if you wish.

Click the Exit button to exit.

You will prompted to refresh the auto matched cheques. Click yes if you want to see what has been auto matched.

When you exit the auto match screen you will see the matched cheques in the reconciliation screen. If you want to add lodgements and reconcile the statement do so.

If you have updated the debits and credits as well you will see them waiting to be matched.

Update Not Found Cheques

Click add not found cheques to insert the records in the not found grid as manual entries that are note yet matched.

Update Other Debits and Credits

Click add other debits and credits to add these as manually entered records. Caution should be taken and you should not use this option if you have already manually entered debits and credits as you may duplicate them.

Near Match

Some banks add text to cheque numbers or drop leading zeros or don’t flag them with their usual cheque identifier in the download file so Newline does not find an exact match. A Near Match column has been added to the list of not found cheques and list of debits and credits. If a record is shown in here you may not wish to auto-import the new record as this may cause duplication and your unmatched total will be too high.

Click the record you do not want to import and press the delete key on the keyboard.

You will have to manually match the correct record in the main bank statement form.

BACs

The system can be set up to show BACs payment separately to cheques. This alters the filter options in the bank lists screen.

There is an options and view BACs menu which loads a BACs screen.

This screen shows the BACs records added by the end of sale process.

Double click a row t see the breakdown of BACs for each seller to make up a BACs total which will show on the bank statement.

This form can be filtered by unmatched and matched BACs. The lists can be exported or printed.

Tech

Sysinfo BANKRECAUTO will show Newline which users use auto matching and the keycode should show which bank format is used to read the file downloaded from the bank.

GROUPBACS used in EOSCAR to write away BACs data to bank rec.

New table def needed

CREATE TABLE bankbacspayments (

bankbacsid int(11) NOT NULL auto_increment,

bankid int(11) default '0',

bankrecid int(11) default '0',

lamsno varchar(10) default '',

saledate date default '1901-01-01',

bacsdate date default '1901-01-01',

amount varchar(20) default '',

saleno varchar(20) default '',

referenceno varchar(20) default '',

deleted char(1) default '',

PRIMARY KEY  (bankbacsid)

) TYPE=MyISAM;

To turn BACs on in BANKREC use config BANKCONTROLBACS. This must be done before end of sale run.