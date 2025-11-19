---
title: "Aef Technical"
source: "AEF Technical.doc"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "There are 5 new tables used in the AEF add-on to NAS"
long_description: "There are 5 new tables used in the AEF add-on to NAS. The definitions are shown below."
---



There are 5 new tables used in the AEF add-on to NAS.  The  definitions  are
shown below.

#
CREATE TABLE `ahocentres` (
  `AHOCID` int(11) NOT NULL auto_increment,
  `Deleted` char(1) default 'N',
  `MarketNo` char(3) default '',
  `AHOID` int(11) default '0',
  PRIMARY KEY  (`AHOCID`),
  KEY `indMarketNo` (`MarketNo`),
  KEY `indAHOID` (`AHOID`)
) TYPE=MyISAM;

#
CREATE TABLE `ahocphxref` (
  `AHOCPHID` int(11) NOT NULL auto_increment,
  `AHOID` int(11) default '0',
  `CPH` char(2) default '',
  `DELETED` char(1) default '',
  PRIMARY KEY  (`AHOCPHID`)
) TYPE=MyISAM;

#
CREATE TABLE `ahodetails` (
  `AHOID` int(11) NOT NULL auto_increment,
  `Deleted` char(1) default 'N',
  `ContactName` char(40) default '',
  `AHOBranch` char(30) default '',
  `Add1` char(30) default '',
  `Add2` char(30) default '',
  `Add3` char(30) default '',
  `Town` char(30) default '',
  `County` char(30) default '',
  `PostCode` char(9) default '',
  `Phone` char(15) default '',
  `Fax` char(15) default '',
  `Mobile` char(15) default '',
  `EMail` char(100) default '',
  PRIMARY KEY  (`AHOID`)
) TYPE=MyISAM;

#
CREATE TABLE `exportbookings` (
  `ExBookID` int(11) NOT NULL auto_increment,
  `CollectionDate` date default '0000-00-00',
  `CollectionCentre` char(14) default '',
  `Deleted` char(1) default 'N',
  `LamsNo` char(6) default '',
  `Heads` char(4) default '',
  `Species` char(2) default '',
  `HoldingFrom` char(14) default '',
  `ClearedforExport` char(1) default '',
  `AHOEMailSent` int(11) default '0',
  `Moved` char(1) default '',
  PRIMARY KEY  (`ExBookID`),
  KEY `indAHOEMailSent` (`AHOEMailSent`),
  KEY `indCollectionCentre` (`CollectionCentre`),
  KEY `indLamsNo` (`LamsNo`),
  KEY `indClearedforExport` (`ClearedforExport`),
  KEY `indCollectionDate` (`CollectionDate`)
) TYPE=MyISAM;

#
CREATE TABLE `exporteartags` (
  `eartagID` int(11) NOT NULL auto_increment,
  `eartag` varchar(20) default '',
  `holding` varchar(20) default '',
  `exbookID` int(11) default '0',
  `CSC1no` varchar(100) default '',
  `CSC1orderNo` int(11) default '0',
  `AHOID` int(11) default '0',
  `clearedforexport` char(1) default '',
  `CSC1printed` char(1) default '',
  `LiveStockType` char(1) default '',
  `MovedtoNas` char(1) default '',
  PRIMARY KEY  (`eartagID`)
) TYPE=MyISAM;


The remoteservers table is important when setting up this software!
In our office details program is  location  text  box.  This  may  have  A-Z
entered into it.

[pic]

Each site needs a unique location letter in the markname file. This is  then
cross referenced with an entry in the remoteservers table.  This  should  be
set up something like the following:

[pic]
The rsid is used to cross reference with the username and  password  in  the
userdetails table. An rsid must be entered in the userdetails to  match  the
rsid in the remote  servers  table  to  cross  reference  the  user  to  the
location.

[pic]

See how Bristol’s rsID in the remoteservers table is 2, it must  also  be  2
in the userdetails table.

When a user logs into NAS the program checks the username and  password  and
checks what location the user is from. This location is written away to  the
4th line in the userinfo.ini file in the working  directory.  This  file  is
latter opened by NASBEND to know where the user is  from.  If  the  user  is
from a given location a remote centre then the options in  drop  down  lists
in the export bookings from are restricted to that  users  centres.  If  the
user has no location and the 4th line of  userinfo.ini  is  blank  then  the
user is an admin user or central office user and will see  all  the  centres
in the drop down box. This  same  concept  applies  to  the  export  report,
remote users only see their centres, central users see them all.

NB: AHO=(Area(or Animal) Health Office) CPH=County Parish Holding
# Table: 'ahocentres'
Is probably not needed at all. Was going to be used to cross  reference  AHO
branches to Collection centres, but in fact there is a need  to  x  ref  AHO
branches to CPHs.

# Table: 'ahocphxref'
This table is used to x ref AHO branches with CPHs.

# Table: 'ahodetails'
This table stores contact details and address details of the AHO branches.

# Table: 'exportbookings'
This table stores the  collection  date,  collection  centre,  section(field
name species), and lamsno for a booking.

# Table: 'exporteartags'
This tables stores the individual animal details for each booking, i.e.  the
eartag details, and holding details. As various reports are printed such  as
the CSC1 then flags are set to Y (e.g. field CSC1Printed),  when  then  CSC1
is returned from the AHO with each animal either marked as  passed  fit  for
export or not the passedforexport field is set as Y if it  is  passed.  When
the user moves the  mySQL  booking  into  the  flat  transaction  files  the
movedtoNAS field is marked as Y.

When the booking is made a sub runs to check the holding number and  does  a
lookup on the ahocphxref table to work out which AHO  these  animals  should
be reported to via the CSC1. The ahoid is written away to the  exporteartags
so that each CSC1 may be printed with only animals to be passed by one  AHO.
When a CSC1 is printed a unique number is assigned to that CSC1 this  number
is stored in the SYSINFO table. The keyname = CSC1no and  the  keycode=  the
number e.g . 1458 (if this does not exist the s/w should  make  it  starting
at 1. When the CSC1  is  printed  this  number  is  written  away  to  table
exporteartags. Each CSC1 has 25 rows of animals on it. Each  animal  has  an
row number next to it on the form. In order  to  keep  the  animals  in  the
order  they  where  originally  printed  we  write  away  a  CSC1OrderNo  to
exporteartags.

CSC1’s.
These are printed with 25 animals per CSC1. If the booking has  30  animals,
but 10 are from 1 AHO area then they will be printed  out  on  1  CSC1  only
showing 10 animals with 15 blank rows. If another 15 are  from  a  different
AHO area these will be printed out on another CSC1.  If  the  remainder  are
from a different AHO area these will be printed out on  a third one.

EXEs affected:

NAS
NASBEND
ALINPUT

New EXEs:
AEFREPS
AHOSETUP

You can pick up these exes at  present  in  \\newlined\vb\UK\AEF\AEFEXES  if
you want to try any of this. The program works out of NAS on an AEF  command
line.

C:\NLPROGS\nas.exe c:\ROOTOFF\(AEF)C:\ROOTOFF\



