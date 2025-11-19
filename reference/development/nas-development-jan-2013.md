---
title: "Nas Development Jan 2013"
source: "NAS Development Jan 2013.docx"
tags: [Development and Technical]
version: "1.0"
last_updated: "2025-11-17"
short_description: "NAS Updates January 2013 Customer Search Salering buyer search Salering New Display Layout Display Only unsolds Sale Weight Report Bank Recon..."
long_description: "The customer search has been tweaked so that a user can enter the surname followed by a # the initials or firstname followed by a # and part of the address to refine the search. E.g. JONES#SIMON#HILLTOP or the user can enter JONES##HILLTOP to just search by surname and address."
---

NAS Updates January 2013

Customer Search

Salering buyer search

Salering New Display Layout

Display Only unsolds

Sale Weight Report

Bank Reconciliation

Lotstore extra fields

Email BCMS Movements (UK)

Seller Transfer (IR)

Sold Subject Feature

NAS manual

Media Player

Customer Search

The customer search has been tweaked so that a user can enter the surname followed by a # the initials or firstname followed by a # and part of the address to refine the search. E.g. JONES#SIMON#HILLTOP or the user can enter JONES##HILLTOP to just search by surname and address.

Salering Buyer Search

The use of the # key to separate the surname from the # firstname # address line

Salering New Screen Layout

As hardware continues to improve and screen resolutions get higher and higher Newline needed to add more screen resizing code to the salering option and at the same time re-designed the layout slightly.

This mode puts the Next weight and lot number boxes at the top of the screen. The benefit to this is that the user can enter these details at any point and still click any other part of the screen (before if the next lot window was up the user had to enter the details before doing anything else). Now they can edit lot details already gone through the salering.

At the bottom right of the screen the user can see a grid with all the lots already offered for sale through the ring. Double click to edit previous lot details.

There is a new beta test option to display a bigger grid showing the animal details.

The grid has bigger text than the previous listbox and has clear column titles and shows clearly if an item has been placed on hold by double clicking.

The screen should resize and make more use of space whatever the windows screen resolution is. The mimic board has been made much bigger so auctioneers may be able to see it easier.

Display Only Unsolds

If display only used in salering it will set lot status to U for unsold so the lot will not need to be entered at a zero price in sell pre-booked lots.

Sale Weight Report

Clients using avery L336 weigh bridge scales that connect auto matically to NAS have a new report available to them which will show what the drover / clerk actually entered on the avery unit in terms of lot no, weight and no of heads. Sometimes the number of animals pre-booked into NAS are not the same as the no of animals that turn up on the weigh bridge for that lot (for a variety of reasons). This report compares both sets of data which may help resolve disputes with sellers or buyers.

In the example below the info all agrees and there are no differences bewteen the lot heads and scale heads. The other useful info is the time the animals went through the ring. This can be used to tie up with any digital video recording you may do for dispute purposes.

Bank Reconciliation

A completely new module has been written and gone live in 4 sites in January to enable total bank reconciliation of mulitple bank accounts. There is separate documentation on bank rec.

Lotstore

The lotstore functionality has been improved / bugs fixed with regards to transferring general lot remarks and rich text formatting bewteen sales and the store and back from the store to the sales.

Email BCMS (British Cattle Movement Service) UK only

This option has been completely re-written to a new format which has an auto email function. Separate document available.

Seller Transfer (Ireland only)

NAS used to prevent the transfer of seller’s lots when configured to use AIM. However if the cattle eartags have not been it is now possible to transfer seller’s lots, or if they have been scanned and accepted as ok by AIM it is possible to transfer them to the same herd number in case there is a father and son, or family account that has been entered incorrectly.

Sold Subject

The lot can be marked as sold subject to seller’s approval in the salering program or sell pre booked lots.

This will prevent the invoice from being produced until the seller has granted approval. The lot is marked in lot edit as SS in a column in the invoice program.

The user can clear this in lot edit or in the sellers cheques. It is possible to show SS on the buyers list. (Tech Note SoldSubject required in the tpl).

NAS Manual

The NAS Manual has bee updated (it is still work in progress but cover 80% of the system).

There is a navigation pain on the left of the screen (a right click option turns this on) to browse the manual.

Media Player

There have been improvements to the media player functionality to play videos and display messages on the Media Player TVs.

The user can set up a message to display and a date and time range to display it.


They can select a video to play  or powerpoint presentation.