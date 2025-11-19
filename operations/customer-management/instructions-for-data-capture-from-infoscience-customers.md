---
title: "Instructions For Data Capture From Infoscience Customers"
source: "Instructions for data capture from InfoScience Customers.doc"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Instructions for data capture from InfoScience Customers"
long_description: "Instructions for data capture from InfoScience Customers."
---


Instructions for data capture from InfoScience Customers.

The first thing we need to do is to capture the customer details from the
InfoScience computer. We need to print the report List of Clients which has
their computer number, name and address and Herd number on it.

Once we have captured this data in to a file we can run our conversion
program. The first screen looks like this.

This is run with the following command line : "d:\naas\(INFO)c:\NAASROOT\"
This can be the same as the command line for NAS apart from you need the
INFO in the ().

Before running the conversion program we do need to set up the Markname
file so that we have all the markets for the new company set up so when we
come to convert the debts we can allocate the debts to the correct market.
If no market is selected you will get a message to inform you to select
one.

[pic]


Once a market has been selected from the drop down list the you click on
the Read in Department file. This is on the basis that we have managed to
get data from the department for the markets required.

This will take to you a windows common dialog screen and allow you to
browse for the required file. Once you have found the file and selected
this for import you will see the following screen.

[pic]

You can then check that the import is correct and make any amendments
necessary. You will see from this list that the first 2 rows do not look
correct so you can amend this at this point. See Below.

[pic]

Once we are happy that the customer details look correct click Update. You
will then get a prompt Create 100 Blank accounts at the start of each
letter. Answer this as required and this will create a Newline Customer
record for each of these people.

You will need to do this for each of the files sent over from the
department.

The next thing to do is to import the customer details captured from the
print routine mentioned earlier. To do this you will need to click on the
Read in InfoScience Customers button. This will read in this file and
display the details on the screen as follows.

This will only update customers with Herd numbers so if there are customers
on the printout without herd numbers these accounts will not be updated.
The screen will display the list of customers found in the captured file as
below. You will see from this screen that there are customers listed more
than once in the list. These would be customers that have multi accounts in
the InfoScience system but because they have the same Herd number the
import program treats these as duplicates and does not load them on again.
These will have to be loaded manually if they are required.

[pic]

If you scroll down through this list you will find any customers in the
captured file that were not part of the data sent from the department
showing up in the N’s with the word NEW in the Lams No column. If you then
click on Update this will update the existing customer in the system with
the InfoScience number so that we can import the debt details later and it
has the potential to allow us to search on their old numbers if required.
The program will create an index file called INFONO + Market Number + .IND.
This will be in the debtdir folder.

Once this has completed you can then look at running the debt update.
Normally this will be done as a separate operation as it will need to be
run just prior to going live. Once you click on the Read in InfoScience
Debts button you will get the following screen appear.

[pic]

If you scroll down through the list you should see that each customer has a
Newline number against them. If not then it will say NEW and this could be
because they have loaded a new customer on to the system after we captured
the original customer details. This should not be a problem as the program
should load on the new customer before loading the debt details. The
customer details might need to be expanded as the details on this report
are less than would be on the main customer report.

Once you are happy with the information in the list click on the Update
button and the debts will be added to our sales ledger files.

MAKE SURE THAT YOU HAVE SELECTED THE CORRECT MARKET IN THE DROP DOWN LIST
FOR THE DEBTS BEING LOADED.




