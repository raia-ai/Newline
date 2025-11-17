---
title: "Mc2 Numbering System Tables"
source: "MC2 Numbering System Tables.doc"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "New MC2 Numbering System"
long_description: "All if these alterations should only happen if the country code in debtdir is set to NI."
---


New MC2 Numbering System.

All if these alterations should only happen if the country code in debtdir
is set to NI.

Nasbend
On the Add-ins menu have the option to download MC2 Numbers. This needs to
do the following.

   1. Display a web page with the Aphis Log on screen so that the user can
      download the required XML file from Aphis.
   2.  When the web page form has unloaded we need to give them the option
      to select the file that they have just downloaded.
   3. If they select a file then this needs update the new table
      MC2NumberRanges. This table will just store the number range that the
      mart was allocated and when they were allocated it.
   4. We then need to update the table MC2Numbers. This table will have each
      unique number in it and the sale number and date that the MC2 number
      was used. When we update this update we just update the MC2 numbers so
      that we have a list of numbers that the mart can use. We will only
      update the other fields as we use the MC2 numbers.

See tables below.

Create Table MC2NumberRanges (
  MC2ID int(11) NOT NULL auto_increment,
  StartNo char(10) default '',
  EndNo char(10) default '',
  RequestDate date default '0000-00-00'
) TYPE=MyISAM;


Create Table MC2Numbers (
  MC2NoID int(11) NOT NULL auto_increment,
  MC2Number char(10) default '',
  SaleNo char(4) default '',
  DateOf date default '0000-00-00',
  Primary Key (MC2NoID)
) TYPE=MyISAM;

Setting Up New Sale.
When a new sale is set up we should check how many MC2 numbers we have in
the MC2Numbers table that do not have a sale no and date of filled in. If
this is less than 50 I think we should display a message on the screen to
inform the user how many they have left to use and prompt them Download
more MC2 numbers Y/N. If they say Yes then we should run the option from
the Add-ins menu and get the user to download more MC2 numbers.


Invoices.
Movement Details Screen.

[pic]

This form need a new Frame for Destination Address as above and this needs
to be populated with the details for the Herd Number entered in the frame3.
If this is the same as the purchaser Herd Number then we can populate this
with the address of the purchaser otherwise we need to look this up using
the HerdNo index. If we do not have a matching record in our system for
this Herd number then the user MUST enter the address details in before
they can continue. All the frames will need to be renumbered and all the
code that these numbers relate to altered. This new frame should only
appear if in NI mode and IR mode does not display frame 4 so this must be
altered to match this. The address details entered here must be stored in
the movement details and printed out on the MC2 document in the destination
details part.

When an invoice is printed that has cattle on it with a flag of Y we need
to do the following. If there are no records with a Y in the Newpassport
field on the transaction then we do not need to print out an MC2.

   1. Lock the MC2Numbers Table for read and write.
   2. Select the lowest MC2Number from the MC2Numbers table that does not
      have a sale number or sale date entered.
   3. Store the ID number returned by this query so that we know the record
      number that we have just updated.
   4. Update the MC2Number table for this ID with the sale number and the
      sale date as this is the number that we will print on the MC2
      document.
   5. Unlock the MC2Numbers Table.
   6. Print the MC2 document with this number at the top of all pages.
   7. Update the new MC2Details table (see below) with the following
      details. Tran Number, MC2Number, Sale No,Date of,UserID and Customer
      Number. There will be a record in this table for each transaction
      printed out on the MC2.
   8. Update the flag on the transaction to a 2 as we do currently.

Create Table MC2Details (
  MC2DID int(11) NOT NULL auto_increment,
  MC2Number char(10) default '',
  Cancelled char(1) default 'N',
  TranNo char(6) default '',
  SaleNo char(4) default '',
  DateOf date default '0000-00-00',
  TransactionId int(11) default 0,
  LamsNo char(6) default '',
  UserId int(11) default 0,
  Deleted char(1) default 'N',
  Updated char(1) default '',
  Primary Key (MC2DID),
  KEY indSaleNo (SaleNo),
  KEY indTranNo (TranNo),
  KEY indMC2Number (MC2Number),
  KEY TransactionID (TransactionID),
  KEY indUpdated (Updated)
) TYPE=MyISAM;

Transfers.
We will need to stop any purchaser transfers for lots that have a 2 in the
new passport field. If we do the following.
   1. Declare a new variable called MC2Active at the same place as we do the
      Actionable currently.
   2. Set this to false in the GetDetails Function next to the Actionable
      one.
   3. In GetDetails after we get the transaction record check to see if
      newpassport =’Y’ and if it does set MC2Active to true
   4. In the frmdetails.txtinputaction_keypress if we check to see if
      MC2Active=false then we cannot transfer any lots as all lots are
      currently printed out on an active MC2 document.
   5. We then need to add code to FilterPurTrxArr to check the status of the
      transactions and only display lots with newpassport set to Y.
   6. We need to add a check to the current condition in this option to
      check                (IF debtdir.countrycode=”NI” and  filteristatus
      and old(set(oldindex).trx.newpassport<>”Y” then) okaytomove=false
      elseIf filterIStatus And oldSet(oldIndex).purInt.InvOrList = "I" Then
      okaytomove=false

Cancel Invoice Option.
Once the user has selected the invoice to cancel and clicked on OK to
confirm we need to do the following.
                             [pic]

   1. Display another message box prompting Cancel MC2 Y/N.
   2. If the user selects Y to this then in the NewCancelInvoice routine
      where we currently set the newpassport field to Y we need to only do
      this if the MC2 is cancelled.
   3. If the MC2 is cancelled then after setting the Newpassport field back
      to Y we need to set the cancelled flag on the MC2Details table for
      each transaction to Y.


Copy Invoice Routine.
We need to give the user the option to be able to print out a copy MC2
Document. We therefore need a button in the copy invoice screen that says
Copy MC2. This can go in the place of the Amend Movement button that is on
the screen currently as I don’t think we should allow the user to amend the
movement details of where the animals have gone to in NI as this will then
not match the MC2 document. This will need to do the following.
   1. Run a query on the MC2Details table and bring back all the matching
      records for this Lams Number. These will need to be grouped by MC2
      Number.
   2. List the details on the screen for the user to select the required MC2
      if there are more than one for this customer. This needs to display
      Customer Number, MC2 Number, Number of animals (This will be the
      number of records in the table as all cattle are single heads). If
      there is just the one MC2 then use this MC2 number as the selected
      one.
   3. Look through the MC2 copy file for this customer number and MC2 number
      and display the details on the screen as per the copy invoice with the
      option to be able to print a copy.





Unsold Passouts
We need to make the same alterations to the movement form in the unsold
passout option as we have made in the invoice program. We then need to do
the following. This needs to go in to the
frmdetail.txtinputactionpassout_Keypress function just before we create the
CreateMC2LicenceForVendor.

   1. Lock the MC2Numbers Table for read and write.
   2. Select the lowest MC2Number from the MC2Numbers table that does not
      have a sale number or sale date entered.
   3. Store the ID number returned by this query so that we know the record
      number that we have just updated.
   4. Update the MC2Number table for this ID with the sale number and the
      sale date as this is the number that we will print on the MC2
      document.
   5. Unlock the MC2Numbers Table.
   6. Print the MC2 document with this number at the top of all pages.
   7. Update the new MC2Details table with the following details. Tran
      Number, MC2Number, Sale No,Date of,UserID and Customer Number. There
      will be a record in this table for each transaction printed out on the
      MC2.
   8. Update the flag on the transaction to a 2 as we do currently.


Vendor Transfer - Cheques
When doing a vendor transfer when we create the new transaction on the
system we need to check to see if the old transaction number is in the
MC2Details table and update this. We therefore need to do the following.

   1. First check to see the status of the lot. If A then do the transfer as
      normal. If U then check to make sure that the newpassport field is set
      to Y. If not then cannot be transferred.
   2. In the DoVendorTransfer function if it is not sameFile then we need to
      check if there is cattleinvolved and countrycode=”NI” then check to
      see if we have original transaction number in MC2Details table.
   3. If we find this number in the table then make a note of the id number.
   4. Once we have created the new transaction and we have the new record
      number update the MC2Details table with the new record number.

Vendor Transfer – Balance



Balance

Sale Closing

