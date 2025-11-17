---
title: "Qms Spe 2016"
source: "QMS SPE 2016.docx"
tags: [Customer Documentation]
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

If there is a broadband or connectivity issue to QMS and the download fails or only part downloads NAS will recognise there are more records in NAS than in the download from QMS and warn the user there has been a possible download issue. It is best to not continue with the update and run the option from the start again.

When the download has completed successfully you click on Exit and then the program will update the information downloaded from QMS in to the system. When this has completed you will see a screen like this.

Lot Input.

Cattle

To use the QMS cattle (SPE) web service each terminal must have QMS Assurance Checking ticked under the options menu of lot input. Note the web service is only relevant to cattle.

During lot input the holding number in the seller account will be used to look up data from QMS.

If the sellers holding number is in the QMS download more than once the user will be prompted to select the correct QMS No.

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

Farm Assurance Flags \ Status –

Q	=	QMS

Y	=	Farm Assured

N	=	Non Assured

Ear Tag Input

There is a new menu option on the eartag input screen so the user can run the QMS PGI checker for any eartags that come back with a status of incomplete movement details.

This is under the options menu top left and runs the same checker as the normal input screen.

Sheep

The daily download populates the QMSData table with all QMS member data. When booking in sheep this table is checked and if the member is lamb assured or both beef and lamb assured the FA status will be Q.

When you select the seller and enter the item type and press enter the label around the seller name and address will go light blue if the seller is a QMS Member.

The farm assurance status will be marked as Q for QMS.

When you select the seller and enter the item type and press enter the label around the seller name and address will remain grey if the seller is not a QMS Member, and not farm assured.

The farm assured flag will be set to N.

Customer Edit

There is a new column called Member Name shown in the Farm Assurance Info tab. This information is pulled down from QMS.

It will show mulitple rows if more than one name associated with the holding on QMS.