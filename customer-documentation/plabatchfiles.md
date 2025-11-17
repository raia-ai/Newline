---
title: "Plabatchfiles"
source: "PLAbatchfiles.doc"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "PREMIER LIVESTOCK ISDN BATCH FILES YEOVIL Icons at Yeovil 2CHIP.BAT [pic] 2FROME.BAT [pic] The batch files at Yeovil exist in C:\\DATATRAN"
long_description: "PREMIER LIVESTOCK ISDN BATCH FILES"
---


PREMIER LIVESTOCK ISDN BATCH FILES


YEOVIL


Icons at Yeovil

2CHIP.BAT [pic]

2FROME.BAT [pic]

The batch files at Yeovil  exist  in  C:\DATATRAN.  The  above  batch  files
deletes ???. & ?. & count*.*  from the  master  directory  and  then  copies
???. & ?. & count*.* from the market directory to the master  directory  and
then zips the information into a file called MAST.ZIP.  This  file  is  then
copied  from  Yeovil  to  a  master  directory  at  the  remote  site  (i.e.
Chippenham or Frome) over the ISDN link.

GETCHIP.BAT [pic]

GETWIN.BAT [pic]

GETFROME.BAT [pic]

The above batch files  unzip  the  information  in  the  relevant  directory
market directory, i.e. Chip, Winford, or Frome.


CHIPPENHAM OR FROME


FROMCHIP.BAT  [pic]

FROMFROME.BAT  [pic]

FROMWIN.BAT [pic]

The above batch files zip  all  the  information  (*.*)  from  either  Chip,
Winford or Frome into a file called MAST2.ZIP and copy it  into  the  Master
directory.  At  Chippenham  these  batch  files  are  in   the   C:\DATATRAN
directory. This file is then copied across the ISDN line back to  the  Chip,
Winford or Frome folder.

FROMYEOVIL.BAT [pic]

The above batch file copies MAST.ZIP into a  directory  called  CHIPMARK  at
Chippenham & unzips it. Chipmark is the debtdir directory at  Chippenham.  A
similar directory exists at Frome called FROMMAR.

Icons @ Chippenham inside Datatransfer folder on desktop



FROME


Icons & batch files at Frome
Icons @ Frome inside Datatransfer folder on desktop

 FromYeovil.bat [pic]

FromFrome.bat  [pic]

Copbatf.bat [pic]

Copbaty.bat [pic]

The copbat files copy debtdir  &  run  multi,  so  that  either  debtdir  is
locally pointing to Frome, or looking down the ISDN line to  Yeovil  to  let
Frome post debts.

FromeYeovil.bat works the same as at Chippenham, & so does FromFrome.bat  in
relation to FromChip.bat.
