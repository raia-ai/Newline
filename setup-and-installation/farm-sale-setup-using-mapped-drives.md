---
title: "Farm Sale Setup Using Mapped Drives"
source: "Farm Sale Setup Using Mapped Drives.doc"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Farm Sale Setup Using Mapped Drives On the USB memory sticks there is a folder called \\Farm Sale Setup\\REMOTE Make folders on the Market server a..."
long_description: "Farm Sale Setup Using Mapped Drives"
---


Farm Sale Setup Using Mapped Drives

On the USB memory sticks there is a folder called
\Farm Sale Setup\REMOTE

Make folders on the Market server and call them FARM1,  FARM2  for  example.
They can be called anything as long as the  folder  name  does  not  already
exist. Copy the contents of one of the existing MARKET folders into it,  but
delete newcust and newback files in the new folder.

There are batch files on the memory stick in a folder called
Farm Sale Setup\DATATRAN
These can be edited to reflect the drive letters and folder  names  used  on
any given site, but the idea behind them is that they copy  sales  from  the
server to the laptop and back again, before and after the farm sales occur.

Inside the remote folder is a debtdir that points to the data on the  server
laptop (the folder that debtdir points to must exist, it can be  a  copy  of
MARKET from the server, renamed appropriately) and a  prodrive  that  points
to the programs and a multi to run the market. There are  also  batch  files
that map to the specified server and run the market.

There should be no permanently mapped drives except for normal market  days,
as the batch files take care of this.

In the copy batch files there should also be a line to copy MARKET\*.*  into
the debtdir folder on the laptop, e.g. REMOTE as this will ensure they  have
the latest debts when out at farmsales.


