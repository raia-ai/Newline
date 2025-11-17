---
title: "New Rep Commission System In Lams"
source: "New Rep Commission system in LAMS.doc"
tags: [Regional Operations]
version: "1.0"
last_updated: "2025-11-17"
short_description: "New Rep Commission system in LAMS There is a file in the master folder called CHANNEL and this has the commission & split for the vendor for each ..."
long_description: "New Rep Commission system in LAMS"
---


New Rep Commission system in LAMS

There is a file in the master folder called CHANNEL and this has the
commission & split for the vendor for each channel. I have made alterations
to the setup new sale program so that when a sale is set up there is a new
field on the screen for default vendor commission % split. The screen looks
like this.

[pic]

The program fills this new field in when the user has selected the saleyard
number. The program does this by picking up the channel code from the
markname file for the saleyard number selected, looks for this channel code
in the CHANNEL file and uses the commission % split figure. The user then
has the option to override this amount when they set up the sale.

This % split is then written away to the Sale Number + Date file which is
copied to the remote server for the sale so the remote user will pick up
the default vendor split for the sale.

















I have also altered the Rep Report program so if the user selects the List
lots to amend button from the first screen (see below)

[pic]

The following screen appears

[pic]

I have added a new column to the system after the V-Rep column called %
Split. This will then display the standard vendor commission % set up for
that sale. If the default needs to be altered then if the user double
clicks on the required cell they can enter a different vendor commission &
split and this will be written away to the lot transaction. Therefore once
they have altered any transactions from the default % split these
alterations are written away on the specific transactions that they relate
to. Any transaction without a % rate on is at the standard rate.

I am now looking at the reports that you sent over so that I can try and
get these looking as required and just have a couple of questions re the
rep revenue report.

[pic]

I need to add a column to the report for Channel, not sure what you call
Ref but I have put in the sale number. I need to add the Comm % and I have
a column total Value. Do you need this one? I then have Rep Com and then
Total Com. The total comm. Is your comm$ I presume but not sure about the
other columns you have. Do you need these or do I just need to add a Rebate
Com column which is the difference between the Total Comm and the Rep Comm?

I need to sort out the totals at the bottom as these are from a screen
prior to the one here.


