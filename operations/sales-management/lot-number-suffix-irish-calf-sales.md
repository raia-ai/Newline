---
title: "Lot Number Suffix Irish Calf Sales"
source: "Lot Number Suffix - Irish Calf Sales.docx"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Lot Number suffix Intro AIM does not allow the same lot number to be used on the same day for lots in different sections"
long_description: "AIM does not allow the same lot number to be used on the same day for lots in different sections. i.e. you can’t have a lot 200 in the heifers and a lot 200 in the calves. To get around this many auctions suffix the lot number for the calves with a letter. E.g. 200K or 200V. Any letter agreed with the mart."
---

Lot Number suffix

Intro

AIM does not allow the same lot number to be used on the same day for lots in different sections. i.e. you can’t have a lot 200 in the heifers and a lot 200 in the calves. To get around this many auctions suffix the lot number for the calves with a letter. E.g. 200K or 200V. Any letter agreed with the mart.

Newline can configure the system to suffix lot numbers with a dedicated letter behind the scenes.

Pre-Booking

The user can pre-book lots 300V to 310V in one easy step. In the lot number field type 300/310 and press the enter key.

This will load 11 calves for this seller suffixed with a defined letter. In our example V.

Selling

If using this method, the user may just type the lot number in the salering and the software will add the suffix automatically.

The user may hit F12 and add more lots to the first one in the batch.

Last Bid

If a lot did not sell the first time it was presented in the ring but the last big was recorded and the animal is represented later the user now sees a last bid column on the right hand-side of the lot details grid.

Setup

It is a sale setting and can be setup in the setup menu within each sale.

Select the section. Enter a lot no Suffix. Just one character long and click save.

Tech

Setup ALPHSECT file in sale folder.

This file is 12 rows long, each row equals a sale section

If section 3 is calves, enter the letter the auction wants to use on the 3rd line of the file.

Changes to amend sale settings

There is a box to input a character for the lot suffix, it can only have 1 letter in it and only accepts letters to be put in it. The text box is disabled until a section, e.g. bullocks, cows, etc, is chosen.

The enter button has been put into the code so that it doesn’t prompt an error message, also clicking save having deleted what was in the textbox doesn’t prompt an error message either.