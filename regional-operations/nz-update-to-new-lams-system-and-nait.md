---
title: "Nz Update To New Lams System And Nait"
source: "NZ Update to New Lams system and NAIT.docx"
tags: [Regional Operations]
version: "1.0"
last_updated: "2025-11-17"
short_description: "NZ Update to New Lams System and NAIT"
long_description: "NZ Update to New Lams System and NAIT."
---

NZ Update to New Lams System and NAIT.

I have set up the new Lams system on the test server at Dunedin and put the new programs in nlprogs. Ian has seen this and run a few of the menu options so that he is familiar with this a bit but we have not run any sales through this yet. We have copied a few old sales over so we can test invoice and account sale printing but have not done anything more than this currently. This is mainly due to the fact that there is still a lot of work to do before we can run full tests before starting to roll the new system out to the saleyards. The initial plan is to update Invercargill first I think as this is fairly local to Dunedin and they sell a number of different types of stock so will be a good test for the new system. I think we need to be looking at doing this the week beginning 14th May if we have everything completed that we need by then. If this goes ok we can then work out a roll out with Ian as to how we get this around to all the saleyards so they are all ready for when NAIT starts on the 1st July. NAIT starts on the 1st July no matter what according to NAIT so we must be ready for this. The other companies are looking at what they need to do to be able to deal with NAIT and we cannot be left behind here.

Requirements for the 14th May.

Installer

We need a fully working and robust installer that will install the MYSQL, all the OCX and DLL controls the system needs. We also need to get the installer to run the MYSQL table creator so we have all the required tables set up from the outset and a configuration user set up so the person installing the system can then log in to run other updaters. (I was not able to run the latest version that Ritchie did after I was there as the first installer did not work 100% and the new MYSQL tabledef checker did not run correctly either.)

We need to amend Nas so that if the user logging in uses this installer username the program knows this is the first run and it therefore needs to update a number of things from HQ. We need to update to the remote server the following details.

Customer Database needs to be update.

This needs to update the flat files also leaving the first 100 customers as they are because they are different in each saleyard.

Update headers.ini and all tpl files from the main server.

Update the users table to the remote server so they have all the users that have access to the system.

Update any other tables like TearOffWording. It might be useful to have a list of tables that need updating in the installer that we can easily update if we find more that need adding.

All the latest programs need to be copied over to the server.

Data Transfer Between Saleyard Server and HQ Server.

We need a transfer option in place so we can copy the current sale files from HQ server to remote server, Old Sale files from HQ server to remote server and sale files from the remote server back to HQ server.

This needs to copy the flat files for that sale along with the new MYSQL table data for the current sale. It needs to check prior to the copy that the data being over written is not newer than the data being copied. Once the transfer has completed it needs to check that the data on the server matches the data on the remote server so we know that all data has transferred back successfully and we then need to create the file that tells the HQ server that the sale has been sent back and is ready to be updated to JDE.

I would like to see this running using new technology and services on the server doing a lot of this but not sure if we have the time to get this done this was or not.

Remote Server Update Alterations.

This needs to be altered so that not only does this update the new and amended customers altered since the last update but also some of the critical tables that NAS needs to run. I would like this to update the users, tearoffwording tables and others as they are added.

NAS Program Alterations.

On the sale selection menu we need an option to Download a New Sale and Download Closed Sale. We will also need an option to Access Current Sale and Access Old Sale as they have currently. This keeps the list of sales to select from down to a minimum.

We need to get Alinput altered so that we can use this to pre enter lots and do full lot and price input so I think if we are getting both of these options altered we should look at sell pre entered lots also so we do not have one old QB program running with these other two in VB. We need to amend the other two as we need to be able to enter the from NAIT ID number in to the system when entering the lots.

I need to do some further testing of the new customer edit screen as it gives errors from time to time if you search by different options. Ian wants to stop any remote user from being able to amend any details on a customer record. If they want to amended anything then they will call HQ who will make the alteration and then the remote user will do a customer update. Currently we let them make minor alterations at the saleyard and these alterations get sent back to HQ but they do not update JDE so the two systems are different. This way if any details need to be updated on an account they will get HQ to make them and they will get the necessary alterations made in JDE so the accounts will match.

I think the invoice program is looking fairly good and very near completion but there are a few alterations needed for this and the onesided invoice program.

The vendor account sale program is progressing but I think there are still a lot of alterations needed before this is ready to run for real as I did not have a lot of time to test this when over there.

I have altered lot edit and sale totals to run using balance but I think the lot edit option needs some further detailed testing and the view all lots option in balance needs checking as some of the fields do not look like they are coming out in the report. Also need to check some of the column widths and also the lot details textbox at the bottom of the screen as they need some different information appearing here.

There is a request for a new option to enter a total tally for a customer from the AHD document and then a report to check this total tally against the tally on each of the lots entered for a customer. This is a new request and as such will need to be priced and cost agreed with them but needs to be taken it to account now when designing the new input screens and menus.

Requirements for 11th June.

We should have access to the NAIT test system to report movement details by the end of May so I think we need to have this completed before the 11th June so we have everything in place we need to get this update out to all users before the 1st July which is when NAIT goes live. They will need training on this so we need to give the user as much notice on this as possible.

We need to make some alterations to the EID update from the Aleis software so that we check the session column headers for the required information in case the user has set up the reader differently than expected and the lot number or Nait ID’s are in different columns.

We also need to look at being able to talk to the Aleis readers directly from our software so that this process is a lot smoother and easier for the user than using CSV files from datalink. We will also be dealing with handheld readers so these will be plugged in to a laptop on the PGGW network so it make it easier to download the data from these readers directly without having to use datalink to save to CSV, browse to the CSV and import this in to Newline. I demonstrated to Doug and Andrew Clark(Livestock Project Manager) how we talk directly to the Aleis reader over here and how much easier this would make the process and they seemed ok to look in to this. I need to work out what we can do any how much it will cost as this is different than the initial pilot process and therefore has not been priced as they wanted to go down this CSV file import option as suggested by Aleis.

They also want to look at how they can use NAIT to improve their bobby calf sale process. Currently when the calves are unloaded at the market they tag the calf with a PGGW tag. They record this tag number against the person that has brought the calf to the market. The calves are then sorted in to size, breed and sex and penned so one pen of calves could come from a number of different sellers. The calves are then prebooked in to LAMS using the tag number as the lot number.

When the calves are sold the buyer can select how many of the calves in the pen they want and the ear tag numbers of each calf recorded with the price and buyer. This information is then taken to the office and each calf sold individually by ear tag number.

New Calf System Using NAIT ID

Calves come in to sale yard and are unloaded by the seller. Calves are scanned to record Eid tag numbers and either NAIT or AHD number entered into scanner to identify seller.

As calves are scanned the Eid tag number and vendor identifier and possible sex are sent to office server via wi-fi and details stored in a new table. Point 1.

There will be a new option that will be used in the office instead of prebooking the lots. This will be to view all the NAIT / AHD numbers and tallies and enter the Lams number for these people in to the new table.

Calves are then sorted in to breed,sex and quality and penned so one pen could have any number of different vendors.

When the calves are sold the tags are scanned in again and the lot number entered. The Eid number when scanned is then looked up in the new table at point 1 and the seller LAMS number found. If no LAMS number found then the system will use the default calf account for that sale yard.

When the seller number has been found then the system will automatically create a LAMS transaction with the seller,lot number,item type and tag number ready for the sale sheet to come back to the office and the price and buyer entered.

This new process will have all the calves sold together with the same lot number so when selling the calves all calves in the same lot can be sold in go thereby speeding up the selling process.

I have sent this process to Doug and Ian and they seem fairly keen for this but have since spoken to IT who do not know if they will be able to get Wi-Fi out to the required saleyards before the 1st July as they are currently looking in to Wi-Fi security before they are happy for this to go out to the saleyards. I will check back with Doug later once we have progressed further with the other alterations required and see if he wants to progress this further and then at this point will work out a cost for this and hardware requirements.