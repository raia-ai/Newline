---
title: "Interest Ledger Charges"
source: "Interest Ledger Charges.docx"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Intro Auctions that provide credit for buyers may wish to charge interest on outstanding debts"
long_description: "Auctions that provide credit for buyers may wish to charge interest on outstanding debts. It is possible to do this in NAS."
---

Intro

Auctions that provide credit for buyers may wish to charge interest on outstanding debts. It is possible to do this in NAS.

Setup Interest Period

Setup the interest period in the aged list of debtors option. Go into the sales ledger menu.

Select the aged list of debtors.

You may be prompted.

Say yes if you wish to automatically tidy transactions balances on accounts with credits and debits which match off to zero.

First Run

Select the settings and interest menu option. On the first run you will see this message.

Click ok to proceed.

Fill in the date(s) and variable settings on the form to meet your requirement and click the calculate interest button.

Subsequent runs

On subsequently going into the interest menu you will be asked to view current period. Click yes to view current period or no to set up a new interest period. If you click yes the period variables auto-populate.

This form has been updated in Dec 2017.

Date Run.

This field is auto-populated by the system date. Today’s date.

Days Grace.

This field is user determined. If set to 7 and the invoice date is within the last 7 days interest will not be charged. The number of days credit you offer your customers before interest is due.

Base Rate %

The user enters the base interest rate they wish to charge.

Charge From

Enter the period date you are running the interest calculation on. Often auctions apply interest at monthly intervals.

Charge To

Enter the period date you are running the calculation to. When the user presses the enter key in this box the no of days to charge interest on will be set. The difference in days between the charge from and charge to dates sets the number of days debt override. This number is used in the interest formula calculations.

Ignore Old Debts

Set a date to ignore old debts before that date. Best to set to the oldest debt on your system. It is important when doing individual debtors to ensure account is on a zero balance at this date.

The system processes all debts from the ignore pre-date – oldest debt date. It applies the number of debt days based on the from and to date to debts since the oldest date.

Help Form

In the menu there is a help and info option. The form gives the user some helpful information.

No of days to charge interest

Used in the interest calculation for number of days debt.

The debt may be 200 days old, but if the override is set as above to 31, the formula calculation will use 31.

Customer Groups

You can choice to apply interest to certain customer groups only if you wish.

Calculate Interest

Click the calc button to calculate the interest based upon the criteria you have chosen.

Results

A grid appears with the buyer details and the interest amount you wish to charge them.

You can delete buyers from this list if you do not wish to charge them interest. By clicking on them and pressing the delete key.

You can also delete low values in one go.

Enter the value and press enter.

Interest Calculation Detail

You can double click a row to see exactly how the interest total is made up.

Note – if the debt is part paid and you are viewing outstanding only the calculation is made using the outstanding transaction balance rather than the full invoice total.

If outstanding only is unticked. All the debts are calculated on the total value and all the payments calculated as credits and the difference is netted off.

Interest Formula

The interest formula is given below. If a number of day override is used the no of debt days is replaced by the override in the calculation.

Post to the ledger

When you have the figures as you want them click the post to ledger button. This will add these interest charges to the ledger.

If you want to add a particular market against interest tick the one in the list

It can be called whatever you like, but INTEREST is a good name for it.

Add for statements

When you have the interest figures you want you may decide to click the add for statements button. This will store the figures for this period. These may then be used in a statement run. The idea is that statements are sent out with interest added but the interest is not posted to the ledger at this point. This can save time for buyers that do not pay interest but will pay their balance when shown an interest charge on their statement.

Individual Buyer – Add Interest

You may not wish to apply interest to everybody with outstanding debts, you may prefer to calculate the interest on an individual basis. This is possible in the see buyers record option.

Search for the buyer.

In the options menu there is a calculate interest label.

If the interest period has not been setup the user will be warned. Go to the aged list of debtors option to configure. Explained at top of this document.

If a period is setup the user will see this message.

Click ok to load the interest form and pre-populate with the current interest period variables. The user may override the period interest variables for specific customers without changing the period variables for other customers.

In the example below the period number or ID is 61.

This period covered the 1st Feb 2017 to the 14th Feb 2017. You can select your own desired period range.

Statements

Once the interest has been posted to the ledger you may wish to send out statements to the buyers. This can be done in the simple list of debtors.

In the file menu there is an option to print statements. Either all statements or ones you have selected.

Select buyers by ticking the tick box on the right.

You can choose to send out statements with interest to selected debtors or to all debtors. Click the appropriate menu option.

View Period Archive

Each period is stored and can be viewed in the archive option. This stores the period interest rate and all the variables that were used to calculate that periods interest charges. The user can go back to the archive and view what variables were used and what the amount of interest charged was and how the interest was calculated. The workings that made up the sum.

Double click and drill down to view details. The screen shows the period id for which period you are viewing.

Period Interest Rates Over Base

If interest rates begin to move quickly again at some point users may wish to adjust the interest rate or add a percentage over base within a current period. They can do this by adding the new rate (top up over base) and the new start date and click save. The grid above shows the rate date starts 17th March 2017. It will continue until the next new rate is added.