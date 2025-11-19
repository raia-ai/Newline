---
title: "Aphis Sheep Movements June 2013"
source: "Aphis Sheep Movements June 2013.docx"
tags: [Regional Operations]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Aphis Inferred Movements Rule Change: As of 10th June 2013 Aphis have implemented a rule change to the movement of sheep in Northern Ireland"
long_description: "Aphis Inferred Movements Rule Change:"
---

Aphis Inferred Movements Rule Change:

As of 10th June 2013 Aphis have implemented a rule change to the movement of sheep in Northern Ireland. Sheep with inferred movements will not be eligible for sale and will need to be sent home. This document explains the alterations to the Newline NAS software to handle the new rule changes.

Pre-enter the sheep as they will be sold:

You will need to pre-enter all sheep and scan the eartags before offering them for sale. You can do this in the normal way.

These settings should be ticked in NI for sheep entry.

Enter the lot number details as normal.

Scan the tags.

Send the in to market movement to Aphis.

Send the on-market movements before offering the sheep for sale. This is done through the menu options shown below.

Sheep that cannot be sold.

When you send the lots in to Aphis it will tell you if they can be sold or not and what the issue is.

Double clicking on the row with a status error will reveal the error code and description. The aphis requestid is a unique code used by Aphis for finding the sheep in question. Danny, Artie and co will be very pleased if you quote this for them.

In the options menu there is an option to view a list of sheep that cannot be sold.

You can print this list off and go and split these sheep out of their pen so they can be sent home and the other sheep in the pen sold.

Finding Sheep that cannot be sold in the pen

In the options menu click Find Aphis Rejected Sheep. When you scan the tag with the EID stick the light will go green if the sheep is rejected. It will go red if it is ok to sell.

Split the lots

Either using sell pre-booked lots or lot edit. If you split a lot that has already had the on market movement recorded by Aphis you will need to send the original lot with the new number of heads into Aphis again. (Tech note the movement flag on this lot with be 5 which tells the system to send an edit lot request to Aphis). Go into the movement reporting menu and into send sheep on movements and the system will know to send this lot again as an edit request to Aphis. It will also send the on-movement for the new split sub lot.

Note you must also reflect this in the pen reading software. Go into the pen reading software and double click the pen in question. Amend the pen no to the appropraite sub lot number, so the new split lot has the correct EID tags against it.

Movement Flags

Invoicing

If the sheep has not been checked with Aphis it cannot be sold. If the on-market movement has not been done (this might include split lots that will need to be sent again to Aphis) the user will be warned when trying to produce a licence.