---
title: "New Haulier History Search"
source: "New Haulier History Search.doc"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "New Haulier History Search / Amend If we add the following options to the history search menu in Nasbend"
long_description: "New Haulier History Search / Amend"
---


New Haulier History Search / Amend

If we add the following options to the history search menu in Nasbend.

4. View movements with no Haulier details.

If we also add an option to View Purchaser Cheque Details to the first
history analysis screen as option 9 and move the current option 9 down one
as these are only displayed depending upon the country code.

This should only appear if the sale is not FURN.

If this option is selected we need to run a query to display all invoices
in the system that have either a BLP in the species field that we do not
have haulier details for. This needs to check for the vehicle reg number.
If we can display the following details in the grid.

Sale Date
Customer Number
Customer Name
Customer Address
Invoice / Unsold Pass Number
Moved Off Date
Moved to Details (Holding Number of Herd Number depending upon which
country we are in)
Haulier Name
Haulier Address
Reg Number

If we set the grid up originally as being not amendable but with the
buttons to Amend / Save / Print / Exit

If the user clicks on Amend then we should allow them to update the grid
with the details they have. The only details they can alter are the Haulier
details. Once they have entered something in the grid we need to set a flag
so that the system knows they have entered something and we can then prompt
them to save if they click on Exit. The Save option should update the
haulier details to the haulier table so that these records will no longer
appear in this list the next time this option is run.

Screen with full lot details on.
If we can look at moving the current details around slightly we should then
be able to get the additional information in that we need.

If we move the item type code and description over to the left slightly we
should then be able to get the breed on the same line.

I think we can remove the sale des that is being displayed after the total
price as this is in the list of sale description frame.

Move the Luck to the frame that has the animal movements in it as this is
only really livestock that this is for.

Move the lot status to the same line as the lot price and move the rep
number and name to the line where the status is.

After the remarks field if there is an extra lot description in the MYSQL
for this record then display a button ‘View Extra Description’. This then
needs to display the details as per the view additional lot description in
alinput. (Need to check what we need to search for in the MYSQL to display
the correct additional lot description for this lot)

This should mean that we have more room under these text boxes so we can
move the current frames up more so we can add more things to these.

We then need to add the following to the frames.
MC2 Number to the frame with the cheque and invoice number in. This should
only be visible if the country code is NI and item type is a B.

Need to add a new field for sale number to this frame.

Do not need the Cid/CCD field in the animal frame as this is no longer
valid. Need to add 2 extra fields for Tb test date and Bruc test date to
this frame and only display these if there is a date entered.

I think we also need a Movement Flag text box to display the BCMS movement
flag status.

I think we should move the weight ref number to the animal details frame so
that this will give us more room in the holding details frame. We then need
to add the following to the holding details frame.
Haulier Name
Haulier Address 1
Haulier Address 2
Haulier Address 3
Vehicle Reg Number

We need to check the number of 1st type and number of 2nd type and if these
have data in them then we need to display this as well as the current
Number of Heads. If might be possible to do this is just 2 text boxes after
the number of heads and in place of the weight as these items will not be
sold by weight.

In the main body of the transaction details I think we need to look at
adding a profit field so that we can display any profit on this
transaction. (We will need to look at endmar20 and how we update this at
the end of the sale to the MYSQL. I don’t think currently we are doing
anything with these files.)




New Profit Table.
CREATE TABLE Profit (
  ProfitID int(11) NOT NULL auto_increment,
  Deleted char(1) default 'N',
  TransactionID int(11) default 0,
  Value char(10) default '',
  LamsNo char(6) default '',
  PRIMARY KEY (ProfitID),
  KEY indLamsNo (LamsNo),
  KEY indTransactionID (TransactionID)
) TYPE=MyISAM;

New Purchaser Cheque Details table.
CREATE TABLE PurChequeDetails (
  PurChqID int(11) NOT NULL auto_increment,
  Deleted char(1) default 'N',
  LamsNo char(6) default '',
  ChequeNo char(6) default '',
  ChequeAmt char(10) default '',
  SortCode char(8) default '',
  AccNo char(15) default '',
  LastPayee char(90) default '',
  Drawer char(90) default '',
  Dateof date default '0000-00-00',
  SaleNo char(4) default '',
  PRIMARY KEY (PurChqID),
  KEY indLamsNo (LamsNo),
  KEY indDateOf (DateOf),
  KEY indSaleNo (SaleNO)
) TYPE=MyISAM;

New AIM movements table.
    CREATE TABLE AIMInfo (
     AIMid int(11) NOT NULL auto_increment,
     inWardMovementRefID char(25) default '',
     Eartag char(20) default '',
     movementAnimalId char(25) default '',
     Deleted char(1) default 'N',
     TransactionID int(11) default 0,
     onWardMovementId char(12) default '',
     fromHerdNo char(15) default '',
     fromTPHerdNo char(15) default '',
     tbDate char(10) default '',
     brDate char(10) default '',
     animalStatus char(1) default '',
     fileName char(30) default '',
     OfffileName char(30) default '',
     ToHerdNo char(15) default '',
     ToTPHerdNo char(15) default '',
     offAnimalId char(25) default '',
     PRIMARY KEY  (AIMid),
     KEY indTransactionID (TransactionID),
     KEY indEarTag (EarTag)
     ) TYPE=MyISAM;

If we add up all the profit found for the transaction on screen and give
the user the option to be able to double click on this box to view the
actual person that was paid the profit. If there are more than one profit
record for this transaction then total all the values up and display this
in the one field. The double click should then list all the separate profit
details and who was paid the profit.

We need to add a View Aim details in the Holding details frame so that we
can display all the details relating to AIM on the screen. We will
therefore need a new form that will display all the fields from the AIMInfo
table apart from deleted and transactionid fields. If we display these in
the following order

     AIMid have this in form caption.
     Eartag
     LotID = inWardMovementRefID
     AnimalID = movementAnimalId
     fileName
     fromHerdNo
     fromTPHerdNo
     tbDate
     brDate
     animalStatus
     Off LotID  =   onWardMovementID
     Off AnimalID = offAnimalId
     OfffileName
     ToHerdNo
     ToTPHerdNo


Endmar20 alterations to update these new tables.
We need a new sub to update the purchaser cheque details to the new table.
This needs to look at the file CHQPAID.week number and update the new
table.

We also need to update the AIM table and profit tables as we update the
transactions to MYSQL. As we update each transaction we need to search the
PROFIT.Week number file for any records with the current transaction number
and if we find one update the Profit table with the profit details and the
transactionID from the transaction update. We also need to do a query on
the AIMID + year + week number table and search for the transaction number
of the transaction we have just updated. When we find a match then update
the new AIMInfo table with the details including the transaction ID of the
new MYSQL transaction record.






