---
title: "Bank Rec Auto Match Bank Reconciliation"
source: "Bank Rec Auto Match Bank Reconciliation.docx"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Auto Match Cheques There is a facility in NAS to auto match cheques using a bank statement file downloaded from the auction firms online banking w..."
long_description: "There is a facility in NAS to auto match cheques using a bank statement file downloaded from the auction firms online banking website. In 2018 Newline have added an auto match credits, debits and lodgements as well from the bank statement download."
---

Auto Match Cheques

There is a facility in NAS to auto match cheques using a bank statement file downloaded from the auction firms online banking website. In 2018 Newline have added an auto match credits, debits and lodgements as well from the bank statement download.

Bank Reconciliation

Select the correct bank account from the drop down list. Enter the statement date and statement number you want to auto reconcile and enter the opening and closing balance.

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

Tech

Sysinfo BANKRECAUTO will show Newline which users use auto matching and the keycode should show which bank format is used to read the file downloaded from the bank.