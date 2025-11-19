---
title: "Cash Posting Notes & Data Changing"
source: "CASH POSTING NOTES & DATA CHANGING.doc"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "CASH POSTING NOTES (ANM ONLY) The local servers at Caithness and Elgin are logged on, upon bootup, to the main NT server in Thainstone"
long_description: "The local servers at Caithness and Elgin are logged on, upon bootup, to the main NT server in Thainstone."
---



CASH POSTING NOTES  (ANM ONLY)

The local servers at Caithness and Elgin are logged on, upon bootup, to  the
main NT server in Thainstone.

There is a file called DEBTDIR on all PCs in  the  C:\  directory  (folder).
One of the purposes of this file is to tell the PC  in  question  where  the
debts (sales ledger) is on the system.

The only PC in the remote sites with DEBTDIR pointing at the  Thainstone  NT
server is the pseudo server (the big/main PC) at either site. Thus if it  is
necessary to post cash at either of these sites the poster MUST use  one  of
these main PCs. Posting on any other PC will loose the work.

ONLY when posting cash, it is also  vital  in  these  sites  to  choose  the
MARKET folder when asked which  market  to  run  today.  When  posting  cash
remotely do not choose “ELGIN” etc. Choose only MARKET.

CHANGING PEN NUMBERS ON PRE-BOOKED STOCK.

If animals are booked into Pen 230-235 it  is  extremely  difficult  to  pin
point them when they come for sale. In  this  instance  it  is  sensible  to
split them into pens 230, 231, 232 etc. once it becomes known exactly  where
they are in the mart.

Using eartag entry, 12. in the main on the day  menu,  simply  call  up  the
pen/s in question. The first prompt given  is  the  ability  to  choose  any
beast in the pen by reference number. This is the extreme left hand  number.
Once chosen, you are prompted to accept or change  each  data-field  in  the
record. To change the pen or any other field, simply type  in  the  one  you
want in place of the existing pen number, or in the case of DOB  etc.,  just
type in the new one.


CHANGING BEASTS FROM ONE RING TO THE OTHER


In Thainstone it is common practice to take  an  unsold  animal  to  another
ring. In order to deal with this in the computer it is necessary  to  change
the animal type. D4 animals are sold in ring 2 and W4 animals in ring 3.

The easiest way to do this is through lot edit. 10 in the main  on  the  day
menu. Simply enter the lot number 230-235 for instance, and all  the  beasts
in these pens will be shown with a reference number for each on the  extreme
left of the screen. Choose the one you wish to change and change the  animal
type. In the above example from W4 to D4. As soon as this is done the  beast
will be available to batch for sale in the other ring.

SELLING A SPECIFIC BEAST OR BEASTS THROUGH SELL PRE ENTERED LOTS.

This option should be unnecessary because all lots of this  type  should  be
sold through the Salering 2000 option. If an unforeseen circumstance  occurs
use the following routine.
The sell pre entered lots option 8. in the main on the day menu, now  allows
cattle to be sold by eartag. Reply [Y] to the automatically  sell  same  lot
number prompt and enter the pen range when asked for lot number. Follow  the
prompts as usual. In the case of a pen or group  of  pens  the  system  will
list all the earnumbers and allow you to pick one or more using a  reference
number.

Newline  14th September 2000

