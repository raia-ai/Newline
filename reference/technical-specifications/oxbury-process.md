---
title: "Oxbury Process"
source: "Oxbury Process.pdf"
tags: [Overview and Introduction]
version: "1.0"
last_updated: "2025-11-17"
short_description: "New Oxbury System and Report"
long_description: "New Oxbury System and Report. Overview This is a process where the auc on company has an agreement with a ﬁnance company to sign buyers up to the ﬁnance company and then transfer any unpaid invoices to the ﬁnance company so they pay the market and run a normal credit agreement with the customer. The auc on company will add any buyers signed up to this scheme with a par cular customer group and then whenever they buy and get an unpaid invoice these details are updated to a report. Then before ..."
---

                             New Oxbury System and Report.
Overview
This is a process where the auc on company has an agreement with a ﬁnance company to sign buyers
up to the ﬁnance company and then transfer any unpaid invoices to the ﬁnance company so they pay
the market and run a normal credit agreement with the customer. The auc on company will add any
buyers signed up to this scheme with a par cular customer group and then whenever they buy and
get an unpaid invoice these details are updated to a report. Then before the sale is closed the mart
user generates a CSV ﬁle with the individual lot details for any invoices in the sale along with a PDF ﬁle
of a copy of the invoice. These are updated to a folder called OXBURY on the main data drive of the
server.

The mart user will then copy these ﬁles to a secure loca on on their network and transfer these ﬁles
to Oxbury.

When each ﬁle is generated the system will update the records to say they have been processed and
send to a CSV ﬁle and it will log the name of the CSV they were entered in.

Programs Needed
        Nasbend 16.0.180
        Eoscar 16.0.244
        Invoices 16.0.509

System Se ngs
        Sysinfo Key - OXBURY_CUSTOMER_GROUP


Sale Transfer XML File Changes
        Add the following to the saletransfertables XML ﬁle.

  <Table TableName="OxburyData" WhereClause="saledate='@@SALEDATE@@' and
saleno='@@SALENO@@' and deleted=0">

   <PreInsertCommand>UPDATE OxburyData Set Deleted=1 WHERE saledate='@@SALEDATE@@'
and saleno='@@SALENO@@' and deleted=0</PreInsertCommand>

  </Table>

Set-Up
         Need to get the user to set up a Customer Group in the Contact management menu op on
         number 3. Once this customer group code has been set up then this will need to be added to
         the above Sysinfo Key so the system know which customer group is being used to iden fy
         customers signed up to the Oxbury Scheme.

         Next any customers signed up to the scheme will need to be added to that customer group.
         You do this in customer edit and select the customer required. Then in the Mailing Info tab
         select the customer group from the list of the le and click the arrow poin ng to the right to
         move the group to the right grid. Save this.
Invoices
When prin ng the invoices there is no change to this process the system will just automa cally add
the invoice details to the new OxburyData table when the invoice is produced.



Sale Transfer
The invoice details should be automa cally updated back to HQ when the sale is sent back if the XML
ﬁle has had the altera on made.

New Oxbury Report
If the user is on the main HQ server and there is the new sysinfo key on the system there is a new
op on on the main NAS menu under Add-Ins Oxbury Invoice Report.




This op on will load the below screen.




The default view is to view all records not already exported. The user should therefore just need to
press RETURN or click Con nue to get a list of all invoices not included in a CSV ﬁle.
This shows all the records in the grid with the op on for the user to select the rows in the grid to
update.

Once all the records have been selected to update the user clicks on File at the top of the screen and
then Export To CSV.

The system will then generate a PDF ﬁle for all the invoices in the grid and update the PDF ﬁle names
to the grid and then generate a CSV ﬁle with all of the records for the diﬀerent PDF ﬁles. These details
are saved in the OXBURY folder on the main data drive.

The view all op on will give the user the ability to view all invoices for Oxbury customers between a
par cular date range. This will show all of the above informa on along with the name of the ﬁle that
the record was updated in.

There is no selec on op on on this view.
