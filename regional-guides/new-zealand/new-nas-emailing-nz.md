---
title: "New Nas Emailing Nz"
source: "New NAS Emailing NZ.pdf"
tags: [Regional Operations]
version: "1.0"
last_updated: "2025-11-17"
short_description: "New NAS E-Mail Process Overview The Nas e-mail operation will consist of a service that runs on the HQ Nas server that is checking a table in the l..."
long_description: "New NAS E-Mail Process Overview The Nas e-mail operation will consist of a service that runs on the HQ Nas server that is checking a table in the local MYSQL to see if anyone wants to send an e-mail from NAS. If it find a new record in the table then the service will try and send the e-mail to the required address."
---

                                 New NAS E-Mail Process
Overview
The Nas e-mail operation will consist of a service that runs on the HQ Nas server that is checking a
table in the local MYSQL to see if anyone wants to send an e-mail from NAS. If it find a new record in
the table then the service will try and send the e-mail to the required address.

There will be a new NAS E-Mail user configuration program that will enable HQ to maintain
usernames and passwords for the e-mail system. You will also be able to set up signatures for each
user along with any standard company e-mail disclaimer.

There will be a new E-Mail status program that will allow HQ high level NAS users to view the status
of any e-mails sent on a daily basis.

There will be a new standard e-mail form that will allow the user to select the required e-mail address
to send the e-mail to or enter a new email address and subject and header.

The form will be similar to this one but with the option to attach other files, select/unselect company
standard terms and conditions jpg for sending with e-mail, tickbox to say if you want to include
signature and it will show the signature on screen. It will also show the default reply address.




There will need to be alteration made to the following programs. Account sale,invoice,customer look
up and sale balance to deal with this new e-mail process. When printing an invoice or an account sale
if the e-mail flag on the customer record is set then the program will not produce a printed copy of
the document but it will update the new E-Mail tables. If the server is connected to the PGGW LAN
then this will update the tables on the HQ server but if running without a connection to the LAN then
it will populate these tables locally and the information updated once they have a connection.

Program Alterations / New Programs and Services
There will be a new service to install on the HQ Nas server called NasEmailing. This will be the
program that does all of the e-mailing.

There will be a new program to enable HQ to setup the following details for each user that will be e-
mail from NAS.

Userid (The ID of the NAS user used to log in to NAS)
Username
Password
From Name
Reply Address
Signature Document Name
Bcc Copy Email Address
The password would be encrypted using 3dessha1 encryption.
There would be a userid of zero which the system would use if there were no email details setup for
a particular user. This would be the default account to use for all NAS programs.
The bcc copy email address would be the senders email address if they wanted all emails sent from
NAS to appear in their main email system.
The Signature document name would be the file name for a specific e-mail signature with company
e-mail policy etc. on so the e-mail being sent looks a lot like a normal e-mail.
All of these details will be stored in a table just on the HQ server called NASEMailUsers.

There will be a new program so a HQ user with the required access level will be able to view the details
of all e-mails sent from NAS. I was thinking of creating a report by date so you would initially see the
date, number of e-mails sent, number of errors. You would then be able to double click on a particular
date and view all the email details so you would get the following information.
UserID
UserName
SaleNo
SaleDescription
Lams Number
Customer Name
E-Mail Address
E-Mail Subject
E-Mail Body
Attachments (This would just be the number of attachments on this screen with the option to
double click in this cell to view all attachment details)
Status

Invoice / Account Sale Programs
The Invoice Program and Account Sale Programs will need to be altered so they check for a new flag
on the customer screen (**details and questions below) and if this flag is set to Y then instead of
printing the document it will update the below tables with the following information.

Table EmailDetails
UserID
DateOf
SaleNo
LamsNo
Email Address
Email Subject
Email Message
UseSignature
ReplyAddress
SendStandardTerms

Table EmailAttachments
DocumentLocation

It will be possible to have multi attachments on the one e-mail.

The List of Invoices and List of Account Sales will show if the document was emailed.
There will be another alteration that will need to be added to these program to deal with the remote
sales processed without any connection to the HQ server. When the server is brought back from the
remote sale and plugged in to the PGGW LAN and the user goes in to the invoice or account sale
options then the program will check the local database to see if there are any email records created
for that sale that have not been sent to HQ. These details will then be updated to HQ so all pending
emails will be sent without having to wait for the sale to be sent back to HQ.

If the user is printing off a single invoice or account sale for a customer then they will be prompted to
E-Mail so even if the customer is set up for e-mail the user can still say No for any particular customer.

Customer Lookup Screen.
**
What I was thinking here Ian is to have a flag against each of the e-mail addresses to indicate what
they can be used for. This would give us a bit more flexibility going forward than just a single flag that
says e-mail my documents.




On the above screen there would be an two extra columns one that would allow you to enter I if you
want to use this e-mail address for Invoices and an A if you want to e-mail account sale notes to this
address. If you had IA in there then it would use that address for both. The other field would be for
Copy so you could also enter another e-mail address on to the account for the person that you want
to automatically e-mail a copy of the Invoice or Account Sale. So you would enter I or A or IA and then
Y in the Copy column.

This would mean you could have 3 e-mail addresses in the system and have 1 of them with I against
it, 1 with A and one with IA. Then when you ran the invoice run the system would send the two email
addresses with an I an e-mail of the invoice.

Sale Balance Program.
There will need to be a check added to the sale balance program to check to see if there are any e-
mails records stored locally that have not been updated to HQ. If there are then these will be updated
when the sale is sent back.
