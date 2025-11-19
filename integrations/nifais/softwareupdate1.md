---
title: "Softwareupdate1"
source: "SoftwareUpdate1.doc"
tags: [NIFAIS Integration]
version: "1.0"
last_updated: "2025-11-17"
short_description: "NEWLINE SOFTWARE UPDATE 1 & BUG FIXES To Install from the CD Put the CD in the CDROM drive"
long_description: "NEWLINE SOFTWARE UPDATE 1 & BUG FIXES"
---


NEWLINE SOFTWARE UPDATE 1 & BUG FIXES

To Install from the CD
Put the CD in the CDROM drive. It should auto run. Click the “Start  Update”
button.
You should then see messages about files being copied and it will  tell  you
that it has completed and press any key to exit.

F8
F8 is being introduced into more Menus as the exit option.  The  After  Sale
Menu and Customer Edit are examples of this.

F5
F5 is increasing being used to save changes.

F4
F4 is used when completing pre-booked lots and shows any unsold lots in  the
section.

Sheep Movement Licence
An  additional  line  of  text  at  bottom  of  licence  mentioning  trading
standards and a place to date it have been added to the licence.

Holding Number Changes
Dealer A has a number 1 account that is always for job B.  If  you  put  B’s
holding number in A’s customer details and put  an  N  in  the  Holding  Add
(Address) field, when the bill is  printed  out  it  will  put  the  holding
number and address of B on the bill.

The holding number changes have been done so that the  same  holding  number
can be entered on different accounts. However if the address on the  account
is not the address for that  holding  number  then  the  holding  add  field
should have a N in it. There should therefore  not  be  2  accounts  on  the
system with the same holding number and with a Y or a space in  the  holding
add field. The system works on the basis that if there is a  holding  number
on an account and the holding address  is  Y  or  blank  then  this  is  the
address for that holding number. Users MUST enter a N in this field for  all
accounts where the address is not the address for that Holding Number

The customer edit amendment of holding numbers was  not  properly  reflected
in bill program, but this release of the software fixes this bug.

Valid Eartag Formats
|UK123456789012                  |All numeric tag has no spaces in|
|                                |it.                             |
|UK A1234 12345                  |Herd Numbers with 1 alpha letter|
|                                |have a space between UK and the |
|                                |herd number and a space before  |
|                                |the tag number                  |
|UKAB1234 12345                  |Herd Numbers with 2 alpha letter|
|                                |do not have a space between the |
|                                |UK and herd number, but do have |
|                                |a space between the herd number |
|                                |and tag number.                 |


Emailing DEFRA/BCMS
There is now a folder within the MAFF folder with  the  year  name.  Newline
have added this to keep things tidy in the New Year.

The email file name has also  been  changed  to  a  week  number  day  month
format.If you realise there is a problem  with  the  market  and  that  some
animals have not been included in the email file you can make a  second  one
in the format week number day month a. E.G. 36W1710a.txt  and  36W1710b.txt.
If you still have a problem you can do it again and  have  36W1710c.txt  and
so on.

Printing the email file sometimes took a very  long  time.  This  should  be
much improved as the sorting method has been changed  and  should  ensure  a
quicker result.

Market Totals
Shows number of animals booked in and sold.

Market Reports
Shows numbers of animals unsold or sold, does not include animals that  were
booked in and not unsold at £0 price, or sold.

Lot deletion Bug
If deleting a lot no. batch and the first lot was unsold and  the  remaining
were sold, the transaction no's for the sold lots would still remain in  the
interim file but would have a journal marker in the transactions.  Hence  if
the lots were entered again you would get the duplicate lot problem.

Cows and Calves Bug
If entering cow & calves and you returned to No of 1st  Heads  and  returned
to No of 2nd Heads then when at the eartag entry prompt  the  program  would
go into a loop and freeze.

Now checks that the value of 1st and 2nd types are valid.

Print Sale Sheets – Whilst booking in.
Altered to print DOB,CID and eartag if Y to print sale sheets  selected.  It
will print the remarks and then the ear tag so it will print  out  correctly
for 40 char remarks.

Cancel Invoice Bug.
Sometimes a user cannot cancel an invoice  due  to  a  bug.  This  has  been
fixed.
