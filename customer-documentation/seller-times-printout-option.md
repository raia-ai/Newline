---
title: "Seller Times Printout Option"
source: "Seller Times Printout Option.pdf"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "New Seller Times Printout Option This new option will work out when a lot is likely to be sold based on the start selling time set up in Alinput a..."
long_description: "New Seller Times Printout Option"
---

                           New Seller Times Printout Option

This new option will work out when a lot is likely to be sold based on the start selling time set up in
Alinput along with the lot number range for each section and the number of lots sold per hour. To
use this new option you first need to set up selling times per section and to do this you will need to
go in to Pre Book Lots and select the below option.




If you select this option you will get the screen below.
To print the receipt for the seller when pre entering their lots in to the sale you need to tick the
following option.




This will look for a setting in Sysinfo to map the printer port LPT2: to a printer. The sysinfo key is
INTAKEPRINTER. If there is no record in sysinfo for this then the computer will default to
127.0.0.1\starIntake so the Star printer will need to be shared as StarIntake for this to work.

Once this is all set up you are ready to pre enter lots in to the sale. You enter the lots on to the sale
as normal but then when all lots have been entered for the seller and you press F1 to change seller
or will get the below screen.
The user has the option to amend any of the selling times displayed in the above grid prior to
printing. If everything is ok then the user can click on the print button and the details will be printed
out on the till receipt printer.

The printout will print the Market Name, Sale Date, Seller name and address and then each Lot
Number, Number of Heads and Approx Selling Time.

When all the details are printed the information is updated to the LotSellingTimes table so we have
an audit of what was printed and if the selling times were altered by the user and if so by which user.



The Section Lot Number Ranges, Selling Start Times etc are all stored in the table SectionLotNos and
the Starting Lot Number is also stored in the current file we use in the NI Aphis download option.
