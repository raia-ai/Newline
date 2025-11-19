---
title: "Qms Spe 2016"
source: "QMS SPE 2016.docx"
tags: [Regional Operations]
version: "1.0"
last_updated: "2025-11-17"
short_description: "QMS (Quality Meat Scotland) PGI System"
long_description: "QMS (Quality Meat Scotland) PGI System."
---

QMS (Quality Meat Scotland) PGI System.

What is PGI?

http://www.qmscotland.co.uk/campaigns/scotch-beef-pgi

Scotch Beef PGI is whole chain assured beef from Scotland. In a nutshell, Scotch Beef PGI is from specific animals that are sourced from selected Scottish farms, adopting best practice including animal welfare and natural production methods. The PGI (Protected Geographical Indication) is the legal protection system to guarantee a genuinely authentic product.

PGI in NAS

There is a check in the NAS when the user selects the sale they want to use to see if the QMS update has been run recently. This is only on servers that are set up to use the new QMS Web Service DLL. If this is set and the update has never been run on the server or the update has not been run in the last 6 days then the user will see either of these messages.

The message above shows the last time the update was run and prompts the user to update it. Click yes to update if you wish to do so.

The message above shows the update has never been run. Prompts the user to run it for the first time.

If the user answers Yes then the system will load the QMS Download screen see below.

You then need to click on Menu and the Download QMS Data option.

The system will then check to see if a download has already been run today and if it has display the following.

If you say Yes to download you will get this screen.

You then click on Download.

When the download has completed you click on Exit and then the program will update the information downloaded from QMS in to the system. When this has completed you will see a screen like this.

Lot Input.

During lot input the holding number in the seller account will be used to look up data from QMS.

If the holding number search during the customer \ seller search returns more than one QMS number result the user will see a choice and be prompted to select the one, they wish to use by double clicking the seller of their choice.

If the holding number is not found in the QMSData table then the system will search our farm assured table for the farm assurance details and update the above form with the details.

When the eartag number and date of birth have been entered in to the input grid the system will display the status received back from the PGI web service. See below.

FA status Q and QMS status SPE (Scotch Potential Eligible) means the web service has confirmed this animal is a QMS animal.

FA status N means the web service does not have the animal as being QMS. This may however be due to incomplete movement details (see QMS status reply) and the user may wish to use the PGI checker to see if it shows a different result.

If the reply says incomplete movement record then you should be able to check the holding numbers from the passport to see if they are all QMS members. To do this you need to go to the Options menu at the top of this screen and select the QMS PGI Checker.

If the QMS status is just NA then this means that this animal is not assured so the flag should be left as N.

This will load the QMS program and you will need to select the Search Option.

If you enter the holding number in to the search box and press RETURN the system will look this up in the QMS Data downloaded earlier and display the following details.

If a record is shown with a joined date and no left date the holding is currently QMS assured. The user may decide to change the FA status flag against the lot.

When you double click on the F/A cell and it is selected the QMS status changes to User Override. This is recorded in a system audit. The user may change this to a Y or Q.

Once you have completed the required searches you can them amend the status of the animal to what you require based on the information found following the holding number search.

Note the auction user has the ability to override the status as they choose. The responsibility for making the correct selection is that of the auction staff. The NAS system provides flexibility for the user and accepts no responsibility for the user’s final choice.

Farm Assurance Flags \ Status –

Q	=	QMS

Y	=	Farm Assured

N	=	Non Assured

It is important to record the FA \ QMS scheme numbers against the sellers’ accounts so they show on the buyers’ invoices.

QMS Membership Flags

L	=	Lamb assured			A	=	Auction?

B	= 	Beef assured			F	=	Feed?

J	=	Joint lamb and beef		0	=	Pigs?

These may be viewed in the customer edit screen under the farm assurance info tab.

http://www.qmscotland.co.uk/assurance-and-licensing

Ear Tag Input

There is a new menu option on the eartag input screen so the user can run the QMS PGI checker for any eartags that come back with a status of incomplete movement details.

This is under the options menu top left and runs the same checker as the normal input screen.

SPEC Replies

When an eartag is scanned or eartag and DOB typed into NAS it calls the SPE web service which will give a reply on the status for that animal. See some of the statuses above. NAS allows the user to override the status if the web service replies the status is unknown the user may decide to use the PGI checker and amend the status as they choose. The auction firm is ultimately responsible for any override they deem appropriate.