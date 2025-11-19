---
title: "Bank Reconciliation"
source: "Bank Reconciliation.docx"
tags: [Overview and Introduction]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Bank Reconciliation Bank reconciliation is the process of a user double checking that what they have paid into (lodged) in the bank, either by tak..."
long_description: "Bank reconciliation is the process of a user double checking that what they have paid into (lodged) in the bank, either by taking cheques and cash from the buyers and paying them into the bank with a paying in slip or direct payments online into the bank and what they have paid out of the bank (i.e. cheques to sellers or BACs to sellers) agree with the bank statement and the computer system. It checks that nothing has been missed or mistakes have been made by the bank or the mart user."
---

Bank Reconciliation

Bank reconciliation is the process of a user double checking that what they have paid into (lodged) in the bank, either by taking cheques and cash from the buyers and paying them into the bank with a paying in slip or direct payments online into the bank and what they have paid out of the bank (i.e. cheques to sellers or BACs to sellers) agree with the bank statement and the computer system. It checks that nothing has been missed or mistakes have been made by the bank or the mart user.

Option 6 in the NAS main menu is Bank Reconciliation (tech note SYSINFO BANKREC. Must also be sent out with nasbend version 7.0.203 or higher and eoscar version 8.0.17 or higher and the latest nldbdef run)

The first time this option is run it will convert the old cheque reconciliation data into the new bank reconciliation format. The system will display a counting message.

Once the data is converted the bank reconciliation screen will load.

Reconcile bank statements

To reconcile a bank statement select the bank account from the drop down list and enter the statement date.

Enter the statement sheet number and the opening balance / balance brought forward

Click the continue button.

Enter the closing balance / balance carried forward and click ok.

The user will then see 3 grids next to each other. The first grid on the left shows all payments out of the account selected. Some clients refer to this as the debits.

The middle grid shows the payments into the account. Also known as the credits.

The last grid on the right shows any matched details.

Nothing has been matched yet in the example above.

At the bottom of the screen the user can see the closing balance and running total (which changes as items are matched and should finally agree with the closing balance).

The user double clicks on either the debit or credit grids to match the figures and the details are taken out of the grid being clicked and put in the matched grid.

Or the user can type the cheque no (ref no) into the Ref No text box and press the enter key. If a match is found the system will match the cheque and put it in the matched grid (if it was the wrong one you could double click it to unmatch it).

Note ID 2 has moved from the Debit grid to the matched grid. This column is normally hidden to the user but is used for clarity in this example. The running total shows a payment out and has reduced the amout in the bank.

Find a reference (cheque / lodgement / debit / credit)

The user can right click on the grid to search for either a reference number or value in the grid.

If a match is found it will be made the top row and highlighted.

When everything is matched the matched grid looks something like this

The user will get this message on screen.

Menu Options

At the top left of the screen is a File Menu and Options Menu with options.

Add Bank Records

This option lets the user add adjustments or lodgements to the system.

Select the bank account and type of input from the drop down combos. Enter the date, reference number if required (i.e. lodgement number or cheque number), the value and click save.

A list of what has been entered and saved appears on the right of the screen.

View Bank Accounts

The user can set up their different bank accounts in this option.

A list of all bank accounts is shown on the right of the screen.

Bank accounts in the grid can be editted by double clicking the row and then amending the details in the textbox and clicking the edit button to save.

Bank In Out Types:  Credits and Debits

There will be some system defaults for descriptions of credits and debits but the user can add to these if they require.

A list of those already set up is shown on the right of the screen and can be filtered by type

View Bank Lists

This option let the user view unmatched cheques or matched cheques. Tick the approriate option button, select the date range and click the continue button.

These lists can be viewed by a variety of different dates.

The Date entered is the date the cheque was issued by the auction firm.

The date matched is the date the cheque was matched of the bank statement (if it has been)

The date banked is the date shown on the bank statement when the cheque was cleared through the bank.

The date on system is the date the information was added onto the computer system.

The user will see a list of bank accounts and the cheques issues from them.

Double click the row to drill down to the cheque details.

There are options in the file menu to print or save the data to csv format.

Bank Control Account

The user selects the bank account and enters the period from and to date. Enters the opening balance (i.e. the last closing balance on the last period) and clicks the save button. The system then auto calculates all the appropriate figures and displays the results.

Note: The Balance Carried Forward figure (which becomes next periods Opening Balance) is the worst case scenario for the auction firm. It shows what the auctions exposure is should all the cheques it has issued suddenly be banked and cleared. The balance C/F + all cheques that have not yet cleared should bring the user to the actual bank statement balance.

The user can print the results in the file print menu (top left).

The user is prompted to reconcile the period. If they are happy it is correct they click yes.

The user can double click on these rows to drill down to get the details of what makes up these totals.

Find

Select how you want to find something, i.e. by reference number, value/amount or customer account number. Enter the search criteria and press enter.

Results will be shown in the grid on the right of the screen.

Double click the grid to edit info. (Different chq shown in edit screen in this example below)

There is a facility in NAS to auto match cheques using a bank statement file downloaded from the auction firms online banking website.

Select the correct bank account from the drop down list. Enter the statement date and statement number you want to auto reconcile and enter the opening and closing balance.

Select auto match statement.

Browse to the file you have downloaded from the bank website and click the open button.

The user is warned if they have tried to import the file already.

The system will show the user which cheques it can auto match. Any differences are highlighted with a red background. The bank value is data from the bank the comp value is the data in NAS. These should be the same but if they are different you need to work out why. You may need to talk to your bank.

The system will through up a warning message if you have matched some of these cheques before or have bank differences.

There is also a list of cheques not found. These have gone through the bank but may not be in your system. You may need to add these manually to the system and then match them.

If everything looks ok and is as you require it you can click update.

This will then auto match the cheques downloaded against the statement you set up.

You can print off what you’ve done if you wish.

Click the Exit button to exit.

You will be prompted to refresh the auto matched cheques. Click yes if you want to see what has been auto matched.

When you exit the auto match screen you will see the matched cheques in the reconciliation screen. If you want to add lodgements and reconcile the statement do so.