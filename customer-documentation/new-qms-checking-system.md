---
title: "New Qms Checking System"
source: "New QMS Checking System.doc"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "New QMS Checking System"
long_description: "Main Screen. If you click on the Menu option you will see the following screen."
---


New QMS Checking System.

Main Screen.
If you click on the Menu option you will see the following screen.


[pic]

If you select the Download QMSData option you then get the following screen
and this will connect you to the QMS database and download the update QMS
membership details. You do need to make sure that you have the QMS file
type selected. The username and password will be automatically filled in
for you and it will be possible to set this up as a scheduled task so that
it can update automatically when required.

[pic]

Once the updates have been downloaded the program will automatically update
your database with the up to date membership details. It also records the
date that the last update was done so if you try to run the update again on
the same day the system will inform you that an update has already been run
today.

The Update Customer records option will update your Newline Master customer
database with QMS membership numbers. The system uses the Holding number to
match the QMS data with the Newline Data so it is important that you have
as many holding numbers on your database as possible.

The Search option allows you to find a QMS customer by entering their QMS
number of Holding Number. You get the following screen appear.

[pic]

You can scan in a holding number off of a cattle passport in the holding
number field and it will search using this.

The SetUp option allows you to specifiy the location of the QMS programs,
where you want to store the QMS data file, how you connect to the internet
and if you are a Newline Market customer.


Checking QMS Status while loading transactions.

If you pre-enter the lots as normal until you get to the Farm Assured
prompt. This prompt will not appear if the vendor is not Farm Assured (does
not have a farm assured number on their account or one has not been entered
when the vendor was selected). Then at this prompt if you want to check to
see if the holding that the animal has come from is QMS approved then press
the * key. This then loads the following screen.

[pic]
If you then scan the holding numbers from the passports the system will
look these up in the database and display if this holding number is QMS
approved. If the holding number is not found then it will display Not QMS.
Once the system finds a holding number that is not QMS approved then this
cannot be altered to QMS approved by scanning in the next holding number
because of the rules of the scheme. If the system finds a holding number
that has dropped out of the scheme then it will beep at you and tell you to
check the movement dates to make sure that the animal movement happened
before the farmer dropped out of the scheme. Once you have scanned all
holding numbers in from the passport pressing RETURN takes you back to the
normal input program and you enter the required farm assurance satus. This
has defaulted to Q for QMS because you have loaded the QMS checker.

If the animal is not from a QMS holding it may well still be farm assured
so if this is the case then you will need to enter Y in the Farm Assured
prompt and if it is neither then enter N.

If you use the Ear Tag entry option to enter the ear tag details then again
entering an * at the farm assured prompt will run the QMS checking program.

