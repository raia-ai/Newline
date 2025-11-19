---
title: "Nz List Of Things To Do And Test"
source: "NZ List of things to do and test.docx"
tags: [Regional Operations]
version: "1.0"
last_updated: "2025-11-17"
short_description: "NZ List of things to do and test"
long_description: "NZ List of things to do and test."
---

NZ List of things to do and test.

Update installer with a system for installing standard master files, jpegs, mysql table data etc so when the server installer is run all of these things are set up automatically on the saleyard server and nothing has to be copied over after.

Set up e-mailing in NAS so system can e-mail directly.

Set up central folder so all e-mails sent from the system have copies saved for viewing later.

Complete the new input program for option 2 and 4 in the new system.

Complete the selling of lots option 3 in the new system.

Complete the new Total Tally Input program for the new system option 1.

Work out what is involved time and program wise for a new report to view tally entered on the transactions against total tally entered in new option 1 program.

Add new customer files to the customer name search in customer edit and also buyer reg option 15 so temp customers show up in these options.

Check that the customer alterations made at HQ are updating the newamendedcustomers table correctly so that the remote saleyards can download them on demand.

Add new option to the EID import in to NAS so when we read the file downloaded from the reader the first thing we do is add up all the records by the different reading dates. We will then need to display on screen a total number against each date and give the user the option to select the required dates that they want to import. This will help to stop any old tags from being imported from previous sales that have not been cleared from the reader. There might be a requirement for EID tags to be read the day before a sale or the day after the sale so we cannot just use the sale date for work out which reads we need. Also the date in the reader might not be set correctly so this will give us a stop gap to deal with incorrect dates on the reader.

Need to amend nasbend so new sales can be set up.

Need to amend nasbend so archived sales can be viewed.

Need to check and do some more testing with balance and lot edit as there might be some data that is not coming through to the list of lots in option 19 correctly. Also need to look at altering the middle textbox at the bottom of the screen to show rep details instead of some of the current UK settings.

Add TearOffWording table to the nldbdef for NZ.

Option 7 and Option 8 on the Utility Menu do not load.

Need to amend the sending of the sales back to HQ and add the eid tags for that sale and the NAIT ID’s used in this sale.

Aleis Meeting With Brian 25th April.

Have an option in setup to say how many readers you are connected to in a fixed reader setup.

Go through each reader setup and do below.

Send reader unit i returns the reader Id if no Id then try a few times to see if there. If no reply then move on to next one.

Send vr 1

Before sending auth 4500 which will reply with OK.

Sae will download all sessions with START and END at the bottom of the download.

The file downloaded from datalink will default to my documents and the files named by date and time.

Need to check the session header for the different types of headers so we deal with the possibility of the data being entered in different formats or different types of file so one could be by pen number and the next session could be from NAIT ID and to NAIT ID.

Files will be in txt extension but CSV delimited.

Brian to send over how we can program the 4 different data headers so we can make these as standard.

If we have some records in a session without some of the fields required then use the information  from any of the other records in the same session.

Field names

Ven

Pur

Qty

Com

Or

Pen

Not used

Qty

Com

On the top format there might be data in both fields for private sale record.

On the copy screen if there is no delivery docket printed for a customer then do not show the copy document button on the copy screen.

Hide the amend movement button for now until we know what the NAIT position is on this if the movement details have been sent to NAIT.

Cheque program can you amend the vat column header to gst no.

Remove the auto print BACS option.

Change the auto print option to auto print account sales and remove all the other auto print buttons.

Do we show in the main customer list if the customer has had their account sale emailed to them?

Add an option for export list of customers on the cheque and invoice screen.

List of invoices first row in grid has bad forecolour on the fixed column.

New Total Tally Input option as option1 and then move all other options down 1 and remove option 6. Have this as a new command line option to just allow the user to select the customer and enter a total tally and species. This then updates a new table for checking later.

Change option 10 to Vendor Account Sales.

When selecting the sale if dated in the future then display a warning to the user that it is dated in the future. Also show this message if the user selects option 1,2,15 then display message also and if they select option 4 or 5 then display this message and then stop them for going any further.

Change option 9 to old option 10 from after sale menu and amend to access level 2.

Change wording on 11 to match option old 9.

Utility menu

No access to option 1 or 2 or 3 or 6 if not hq user and only access level 2 or above.

New option for commission variance report for all sales over a selected period. Needs to update this when the sale is transferred to jde. Have the option to filter by auction channel or all channels.

Add vendor rep and buyer number to list of lot details if ticked in configuration. Change cheque no to account sale no.

Have an option for email invoice and account sales.

Change contacts to notes.

Change registered to account opened.

Change registered to opened by.

NAIT info grid to have NAIT I'd, last used, where used, and off or on and Salerno.

Need to add Newcust file search to name search in alinput.

Invoice address and payment address only needs to print if Y to auto print copy is set. Remove the address on statement option from both options and just have one tab option. Use the details entered here on both invoice and account sales. Need to always produce the original to the main name and address and then print a copy with these details on. The copy needs to have the word copy on it.

need to have an option for email address on the copy extra address screen so that the copy could be sent via email instead of printing.

These details will only be setup at HQ and the sale yards will not have access to amend these. Only level 1 and 2 access levels to be able to amend these details.

need a report to view all customers amendments between a date range entered.

Check the phone number search and exiting without selecting a customer. It seems to be exiting the extended customer search that is the problem.

Selective invoice/delivery docket option comes up with error re new customers. Not sure if this is to do with my data or not.

might need to remove the print vendor name. From options menu in invoice program.

invoice list of deductions screen has the labels overlapping the scroll bars on the list of charges.

Looking at doing away with the option for A and D on the deductions so the user can just enter the value of the charge. Would need to add a warning message to get the user to check if they have entered a + value to a seller or a - value to a buyer.

In the customer name search if on main server then always default the area search to ALL areas when the program loads but allow the user to amend for their session.

make the main lot list box 1 cm and make the rem box at the bottom 1 cm.

Change the word Av wt to wt.

NAIT numbers are only needed to be entered for cattle.

need to pick up carrier from the carrier selected at reg time. Details will be in pbuy file.

What are the autosave records in the download from the reader?

Need to set up the amendment level table with all the access levels being setup so remote users cannot amend a number of fields.

Have a field on the new customer edit screen to store in a customer wants to have the other party printed out on their account sales and invoices. Just main user setting field. Option for A,I or B to say which ones to print on.

Do we need the option to print out lot details when loading?

If option to enter rep number when loading is set then stop at rep number prompt otherwise just to item type.

Need option for Tb Status.

There is an option to enter grade with the grades shown in a list as per item types.

In the new account sale program have the option to apply a change to the charges on a lot to all lots for that customer.

NAIT Private Sales.

Have an option for someone to go out and read on farm and enter from NAIT ID,to NAIT ID,move date and tally in the 4 fields on the handheld reader. Download this into LAMS and as part of the download from the reader we send the details off to NAIT. If everything updates NAIT successfully we then send this to HQ for storage so that this information can be viewed later and match up with the private sale entry form when they come in.

Need to amend the vortex clearing to work on decimal as well as hex as currently it has to be in hex.

Late Sale Sheet Register

If private sale transaction is an adjustment record then do not update the late sale sheet register.

Add a new table called InternalAccounts and if the LAMS account number entered as the buyer on the private sale record then again do not update the late sale sheet register. Need to add an option to view account numbers entered and add or delete records from the table.

Can you enter details in to a session after the session has started reading.

Need to check in Morinsville operation what do we do if we have Eid tag in a sale twice with an in and no out. Need to see if we can do something with times.

Need to check with Brian how the 4 cables from the readers will connect to the laptop for downloading Eid details. Need to look at getting the cable extended to the PGGW office so they can download directly in to their system without having to take laptop over to sale ring.

Reading in and out need to be able to enter a temp ID and then need an option to be able to amend the NAIT ID later.

Have an option to print out list of Eid tags once the tags have been read into the system. Will need an option on the customer edit screen to say if the customer wants Eid tags sending to them.

On the new input screen in the yellow frame have the following details.

Rep Number

Rep Name

From NAIT ID

Total Tally

Need a new program to allow the user to amend the payment terms file. PTC.TXT. This is 66 chars long. Need to add this to the new menus but it does not need to be in the sale menus it can be on the main menu.

Setup MYSQL username and password for SA on the mysql and then have a different username and password for the application to use. (Need to get details of exactly what is required from SB)

Need to add SQLTearoffMessage to sysinfo in the installer.

Need to check that all the sale reports load and do as required.

Need to add the conjunction sales option to the cheque program so that we have all of this producing documents in the same format. (See written notes on this)

Add an option to the new customer edit screen to allow the user to view the e-mail log for a customer.

Have a new option so that the user can view all e-mails sent between a date range and then by either saleyard number or all.

Need to complete the setting up of new sales.

Need to get the option for sending sale data back to HQ completed and also the downloading of sales to the remote servers completed. There are a lot of new tables that need to be included in the sale transfer.

Need to add the updating of users to the customer update so when each saleyard does a customer update they will also download a new list of users so if any new user is added at HQ then this will automatically be transferred to each remote saleyard server so any new member of staff will be able to log in using their own details.

Need to look at creating the copy invoices and account sales in jpgs so they can be updated to the JDE copy system in their original format. Will need to come up with an indexing system for this so that the copies are easily found. (Frances will look in to this and see what is required)

Amend the NAIT EID tag import option so we read the header record looking for the specified column names and use these to pick up the correct data. This will allow for different setups even though we have specified a standard approach. If they use different headers however then we will need to warn the user.

Need to amend chargerep to new screen colours and improve the overall look and feel of the program. Need to look at the conjunction commission figures on this report as currently they are not shown on this.

On the customer name search in customer edit and buyer reg when the user goes in to the program default the area search to all areas but let them amend this to what they want for their search but then do not save this to the file as this effects all other users.

If it is a forward sale then it does not write away the salelist number to the date file. This does not put in the commission split either. This should always be 50/50.

Need to add an option to enter base interest rate.

Need to add an option to enter Shadow Credit Limit. This needs to be to at least 2 decimal places.

Need an option to allow the user to amend the details in the date file for a sale already setup. This should only be possible if no lots have been entered.

Need to test the transfer options in both invoice and cheque programs as not done a lot of this yet.

Need to change sundries and other livestock to item types instead of sections. Change sections to item types so these are shown as sep sections. This is for KPI.

Add new columns per section for buyer comm in, buyer comm out and total comm. This is for KPI.

Late Sale Sheet Register.

Add initials to buyer name on report. Done Show the sale yard number from the date file in the report. Done Altered to now delete record if amending a private sale record. Done

Amend search and invoice program to use new account type of 23.

Drafting fees.

On drafting fee report have another option at the top for INVALID. This will show just the records flagged as invalid. Need to add a field to the table for INVALID. Need to add a right click option to report to flag a record as invalid. Prompt for password and then flag record as INVALID. If running INVALID report then do the same but remove INVALID flag.

Add location column to grid for the supplier district.

When doing a filter by district prompt after the selection 'Include NC records' If this is Yes then show all records where rep number is 323 and supplier district is the same as the district selected.

Fieldrep file

On the view field reps add a manager name field to the grid and edit screen to show manager name.

On the export change branch code to branch name.

Add a new column to show initials and surname.

Add manager name to export.

Look at option for regional manager in Fieldrep file.

Customer edit to have 4 lines of address and 5th line will be temp name.

Need to add Newcust file search to name search in alinput.

Invoice address and payment address only needs to print if Y to auto print copy is set. Remove the address on statement option from both options and just have one tab option. Use the details entered here on both invoice and account sales. Need to always produce the original to the main name and address and then print a copy with these details on. The copy needs to have the word copy on it.

need to have an option for email address on the copy extra address screen so that the copy could be sent via email instead of printing.

These details will only be setup at HQ and the sale yards will not have access to amend these. Only level 1 and 2 access levels to be able to amend these details.

need a report to view all customers amendments between a date range entered.

Check the phone number search and exiting without selecting a customer. It seems to be exiting the extended customer search that is the problem.

Selective invoice/delivery docket option comes up with error re new customers. Not sure if this is to do with my data or not.

might need to remove the print vendor name. From options menu in invoice program.

invoice list of deductions screen has the labels overlapping the scroll bars on the list of charges.

Looking at doing away with the option for A and D on the deductions so the user can just enter the value of the charge. Would need to add a warning message to get the user to check if they have entered a + value to a seller or a - value to a buyer.

In the customer name search if on main server then always default the area search to ALL areas when the program loads but allow the user to amend for their session.

make the main lot list box 1 cm and make the rem box at the bottom 1 cm.

Change the word Av wt to wt.

NAIT numbers are only needed to be entered for cattle.

need to pick up carrier from the carrier selected at reg time. Details will be in pbuy file.

What are the autosave records in the download from the reader?

Need to set up the amendment level table with all the access levels being setup so remote users cannot amend a number of fields.

Have a field on the new customer edit screen to store in a customer wants to have the other party printed out on their account sales and invoices. Just main user setting field. Option for A,I or B to say which ones to print on.

On invoices print temp name (address line 5) under postcode.

Conjunction commission program is giving gst on the charges even if customer is not gst registered.

New Ovation Finishing Scheme.

have a new client type for Finisher report. If buyer has a client type above then when entering lots in the private sale system prompt to enter finishing name. This then needs to update a new table finisher reports with the following info.

Salerno

Acc period

Accyear

Transaction no

Finisher name

Sale date

Invoice number

Tally

Item type

item description

Deleted

Buyer lamsno

Buyer jdeno

Buyer name and initials

If the channel is A,B or S then if buyer has this client type prompt user to enter temp name when printing invoice. Need to add this rule to the auto pre invoice run so user knows to print these invoices in single option.

We need to print the finisher name against each lot on the invoice and update the record with the invoice number.

On the report need to have the option to view by Accyear and accperiod. From period to period. Also have an invoice number search.

Supply profit and loss report kill version to show all records not grouped by supplyinid.

Deferred interest table needs to have the record number of the transaction created so when we print the invoice we can update the record with the invoice number.

Late sale sheet register to have the same option.

If charge code 40 used on the buyer then print out a different interest message. Message to follow,

In invoice program when the user enters a manager name for override they must enter 5 chars or more with a space in the 5 chars and not at the end. If less than this then prompt ' Please enter initials and surname' and amend the wording on screen to says this.

Raw data report to show 1 record per transaction.

When setting up a sale have a prompt for adjustment sale. If this is set then auto tick adjustment tick box in private sale lot entry.

Rework report needs an option to delete a record. This will need a password setting.