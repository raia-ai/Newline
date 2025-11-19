---
title: "Lotimport"
source: "LotImport.pdf"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "New Auto Lot Input from Internet Selling Systems"
long_description: "New Auto Lot Input from Internet Selling Systems."
---

    New Auto Lot Input from Internet Selling Systems.

Nasbend Alterations.
If sale set up as a FURN sale then amend the caption for option 7 to Import Data from Internet Sale.
This will need to be made visible if FURN sale and leave as EID option for Livestock sale.

If sale is Livestock sale and not NI then we should amend the caption for option 8 to the same Import
Data from Internet Sale so we have this option for both types of sale. We will need to amend the
current number 8 option for auto booking lots.




Alinput Alterations.
Setup Utility & New Tables
We need a couple of new tables so that we can store the different on-line auction companies and
the format of the different file downloads that the program will be working with. We will need to
store the following details.

CREATE TABLE InternetSaleFiles (
  InetSFID int(11) NOT NULL auto_increment,
  InetSFTypeID int(11) default 0,
  FieldName char(50) NOT NULL default '',
  FieldNo char(3) NOT NULL default '',
  MergeWithCol char(3) NOT NULL default '',
  PRIMARY KEY (InetSFID)
) TYPE=MyISAM;

I think we need to have a list of standard field names for the update to this table so the user is just
selecting which column goes with which fieldname. We can then look for specific fieldnames in the
program to do certain things. We will need the following set FieldNames I think.
LOTNO
VENDORNO
LOTDESC
RESERVE
PRICE GUIDE
PRICE
PADDLENO
BUYERNO



There might be a few more but we can add these later as we come across them.
CREATE TABLE InternetSaleFileTypes (
  InetSFTypeID int(11) NOT NULL auto_increment,
  InternetCompanyName char(50) NOT NULL default '',
  FileDes char(50) NOT NULL default '',
  NasOption char(1) NOT NULL default '',
  FileExt char(3) NOT NULL default '',
  FileDelimiter char(3) NOT NULL default '',
  Deleted char(1) NOT NULL default 'N',
  SkipFirstLine char(1) NOT NULL default 'Y',
  PRIMARY KEY (InetSFTypeID)
) TYPE=MyISAM;

We will need a utility program to allow the user to enter these details. An option on the main auto
lot import screen I think for System Utilities.

This will need to display all the details from the Intersalefiletypes table so the user can select a file to
amend. There will also need to be an option to add a new filetype.

If the user selects a filetype to amend we then need to bring back all the fields for that filetype from
the salefiles table so the user can view these and amend if needed.

File Import Routine.


We need a menu option on the first screen with the following options.

    1. Import Lot Details
    2. Import Buyer Name and Address Details
    3. Import Prices and Buyers

The first thing any of these options needs to do is to display a list of the different internet filetypes
that match the option selected so the user can select which file they are importing in to the system.
The program will need to check the option against the Nasoption in the table.

Option 1.
This option need to run through the file and get all the lot details from the file and display these in a
grid on the screen so the user can view the details to make sure all lots are imported correctly. We
will need to create a column in the grid for each field in the file so we know we have all the
information correct. If there is a value in the MergeWithCol then we need to add this field to the
field in this column. (This will enable the system to deal with price ranges that are in two different
fields in the export file.)

Once the user is happy that everything is ok they can click on the update button. If one of the cols
for this file layout has a Y in the vendor col field then we use this as the vendor but if there is no Y in
any of the fields we will need to prompt the user to enter a Vendor Number to import the lots to.

Option 2.
This option will run through the file and check the buyer e-mail address and see if this e-mail is
already in Newline. If it is then do not add a new account but if not then add the buyer on to system
as new customer. Store the bidspotter ID and paddle number against this Newline Account number
for this import. Show all the buyers loaded on to the system in an itgrid so the user can see all the
customers entered. I think it would be useful to show which customers are NEW and also a total of
how many new customers have been loaded. These customers I think need to be loaded as
permanent customers.

Option 3.
This option will run through the file and look up the lot number from the prelot file. It will then look
up the buyer from the customers using the paddle number and display the lot number, lot
description, price and buyer details in a grid for the user to check everything is ok. They then click
the update button and the lots are sold on the system.

If a lot is not found from the prelot files then I think we should create a new transaction in the
system and display the details in the grid.

If a buyer is not found for the buyer number then we need to display the buyer number in the grid
and customer not found in NAS for the buyer name and address details. This will mean that if the
user selects option 3 before option 2 they can escape out and run the options in the correct order.
