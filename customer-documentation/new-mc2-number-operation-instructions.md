---
title: "New Mc2 Number Operation Instructions"
source: "New MC2 Number Operation Instructions.doc"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "New MC2 Number Operation"
long_description: "For this new system to operate in the NI markets we need to update them with the following programs"
---


New MC2 Number Operation.

For this new system to operate in the NI markets we need to update them
with the following programs

Cheques
Balance
Nasbend
Invoices
Endmar20
Enttype

We also need to send out the file nldbdef.txt and put this in the master
folder on all servers. This will automatically create the new required
tables for the MC2 number system.

The system operates in the following way.

When the user does a program update once the new programs are copied to the
server the Nasbend program will automatically do a database check and
create the new required tables.

When the user selects the sale required the program will check to see how
many MC2 numbers it has for this mart number and if there is less than 100
it will display the following message.

[pic]

If the user answers Y to this prompt they will see the following screen.

[pic]

The user should log on to Ahpis in the normal way using the correct details
and then select the following.


      Requesting Document Numbers


A new option, ‘Market Documents - Request Market Documents’ has been added
to menu on eLivestock, as shown on Figure 1.

                       [pic]
         Figure 1: ELA Menu options

Upon selection of this option, the Request Market Documents form will be
displayed (Figure 2).  Markets will be required to input a value between 1
and 1000. The upper limit of 1000 is held as a parameter and can be changed
if required.

[pic]
                                                        Figure 2: Request
Form

When the Order button is pressed on the Request form, the number of
requested documents will be validated to ensure that it is a numeric value
between 1 and specified maximum.  If a valid number has been requested the
appropriate number of documents will be created and allocated to the signed
on market.


Request Confirmation


Once all the document numbers have been successfully allocated a
confirmation screen will be displayed (Figure 3).  This will list the range
of ‘M’ document numbers that has been allocated to the signed on market.


                    [pic]

                                                   Figure 3: Request
Confirmation

Pressing the ‘Download XML’ button will prompt the market to download the
allocated ‘M’ document number range. The format of the download XML is
shown in Figure 4 and it is important the file is downloaded at this stage
as there will be no other opportunity to do so.

   <VMLMessage Type="TAG-ALLOCATION-RESULTS">
   <uploadFileName>tagallocation.xml</uploadFileName>
   <allocation>
          <requestDate>14/01/2008</requestDate>
      <startDocument>S400000965</startDocument>
      <endDocument>S400000965</endDocument>
   </allocation>
   </VMLMessage>

Figure 4: Tag allocation XML


Once this file has been downloaded and the user has exited from Aphis on
Line the computer will then display the following screen.

[pic]

Select the file that you have just created from Aphis on line and the
system will update the system with this MC2 number range. If you select a
download file that has already been processed by the system you will see
the following message and will need to select another file to update.

[pic]


There is also an option to download more MC2 numbers from the set up menu
option 7.

[pic]

If you select this option it will take you to the Aphis on Line screen.

These downloaded MC2 numbers are used when printing the MC2 licences in the
invoice program or unsold pass outs in the cheque program.

Invoice Program.
Printing Invoice.

When printing an invoice after the payment type has been selected the
movement screen is displayed. This now has the Destination address for the
Herd number that the animals are being moved to. If a Herd Number is
entered in field 3 the system will look this Herd Number up on the system
and display the address details. If the Herd Number is not found in the
system then the user will have to enter the destination address for the
herd number to be able to print the MC2 Permit. There is also an option to
not print an MC2 permit and this will automatically be set to N if an MC2
permit has already been printed and not cancelled when the original invoice
was cancelled.

[pic]

When printing invoices the program will need to get new MC2 numbers for
each permit required and if all the MC2 numbers downloaded have been used
you will see the following message.

[pic]

If this message appears then the user will need to go to option 26 Set Up
Menu and download so more MC2 numbers using option 7.




Cancel Invoice Option.
When an invoice is cancelled and an MC2 has been produced for the animals
on the invoice the system will display the following message.

[pic]

If the invoice is being cancelled so that lots can be transferred to a
different customer or the animals are moving to a different Herd Number
then you need to answer Y to this prompt. If the invoice is being cancelled
for a different reason then this prompt can be answered as required. If the
MC2 is not cancelled then the animals on this invoice will not be able to
be transferred to a different customer. You do need to have the original
MC2 permit as the new MC2 permit will have a different number on it and it
will cause problems if the original MC2 permit is sent back to the
department.

Purchaser Transfer Option.

If an invoice and MC2 permit have been produced then no lots for that
purchaser can be transferred to another person. If the invoice has been
cancelled but the MC2 permit has not then you still cannot transfer any of
the transactions to another purchaser. You will see the following message.
[pic]

If a purchaser transfer is required then you will need to cancel the
invoice and the MC2 permit before being able to continue.



Copy MC2 Permits.
If a copy of the MC2 permit is required then this option is available in
the copy invoice option. If you select the required customer in the normal
way and then on the invoice details screen select Y for copy you will see
the copy invoice screen with the following options at the top right.

[pic]

If you select the MC2 Movement Licence option you will get a copy of the
MC2 licence on the screen and then if you select Print the system will
print out the copy MC2 permit.

Unsold Passouts
When printing an unsold passout the user will see the same movement screen
as at the time of printing out the purchaser invoice. The same rules and
operation applies to the printing of unsold passes.

Vendor Transfers
It is not possible to transfer an unsold lot from one vendor to another if
the unsold passout has been printed. If a transfer is required then you
need to cancel the unsold passout and MC2 permit. To cancel an Unsold
passout you need to go in to the cheque program and then select the Options
menu at the top left of the screen. This will display the following
[pic]
If you select the List passouts option you will get a list of all the
passouts produced. Select the passout that you need to cancel and then
enter A to cancel passout. When you have entered A to cancel you will get
the following option to cancel the MC2.

[pic]

Again you MUST have the original before canceling this so that the original
cannot be sent to Aphis to confirm the onward movement.

Creating XML movement file for Aphis.
All movement details are sent to Aphis using the same option as before. The
only difference in this operation is that you can only send details to
Aphis if they have an MC2 number allocated to them. This number is
allocated at the time of printing the invoices or unsold passouts. If a
transaction has not been printed on an invoice or passout and therefore
does not have an MC2 number then this row in the grid will not be ticked.

[pic]

At the bottom of the screen is a total of the number of animals selected to
send and you can deselect any of the selected rows in the grid if you want
to send the onward movement details to Aphis in batches. Once the details
have been sent to Aphis they will not appear in the list of animals to send
so once everything has been sent to Aphis there should be no records in the
grid to send.

If all the required transactions are selected on screen then click on the
Create XML File button and the system will create the XML file as it used
to. The file is uploaded to Aphis in the same way as before but now once
the file has been uploaded there is no option now to process Aphis Reply.





