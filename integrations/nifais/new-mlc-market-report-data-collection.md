---
title: "New Mlc Market Report Data Collection"
source: "New MLC Market Report Data Collection.doc"
tags: [NIFAIS Integration]
version: "1.0"
last_updated: "2025-11-17"
short_description: "New MLC Market Report Data Collection"
long_description: "New MLC Market Report Data Collection."
---


New MLC Market Report Data Collection.

1. Run program update on all workstations.

2. Go into Installation menu Option 2 and set  up  the  section  type  (This
needs to be done in each sale/market folder you run). This has replaced  the
new Prime / Store option. Any non livestock section needs to  be  set  to  O
for Other and also any livestock section that does not want to  be  sent  to
the MLC should be set to O for Other. E.G. any  resale  sections.  You  will
need to make sure that the Cull/Killing Ewe section will need to be  set  to
Prime so that the report separates Store Ewes from Cull/Killing Ewes.

[pic]

3. Check that you have the correct MLC  number  in  the  MLC  centre  number
under the Company Settings menu option.  (This needs  to  be  done  in  each
sale/market folder you run).

[pic]

4. Go into Option 7 of the installation Menu and make  sure  that  Send  MLC
Sale Report option is set to Y for all markets that would send sale  reports
data to the MLC. This option only needs to be done in the MARKET folder.

[pic]

5. Next run the sale as normal and then before closing  down  the  sale  run
option 15 in the market reports option. The first time this program  is  run
it will display the following screen.


[pic]

This screen is used to match up the markets animal types with  the  standard
MLC report types. Once these have been matched this screen will  not  appear
again until it finds new animal types that do not match a valid  MLC  report
Code. To match items you double click on the MLC report  code  that  matches
the market code on the left. This will remove the market code from the  left
list and take the user to the next market code. The user can  only  continue
when all market codes have been matched against a valid MLC report code.  If
you click on cancel it will take the user back to the  market  report  menu.
Once all type codes have been matched the system will display a Next  button
and if this is clicked the program will go and create the MLC  report  file.
If there is an animal type in the market list (left list box) that  they  do
not want to report to the MLC then if they  click  on  this  item  and  then
press DELETE this will flag this itemtype with a description  of  NOREP  and
these types will not be sent to the MLC and this item will be  removed  from
the list. You can select NSL (New Season Lamb) for  store  lambs  and  Prime
Lambs as they will be split out with different sale types in  the  file.  It
will use the Section setting from option 2 to split out store and prime.

The  file  is  created  in  a  year  folder   (Usually   c:\market\2004   or
z:\market\2004.) The file is called MLC + sale day &  month  &  week  number
.CSV. The program will tell the user where the file is being created and  if
the year file does not exist then it will create this.

The program will flag all the transactions that it includes in the  file  or
that does not want to be included in the file and the end of market  program
will check that all records have been flagged before allowing  the  user  to
close the sale down.

If there are new transactions added to the sale  after  the  file  has  been
created and the program is run again it will add these new  transactions  to
the original file.

The MLC email address to send the file to is:

auctionmarkets@mlc.org.uk


