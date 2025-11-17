---
title: "Manual Instructions On Updating Clients To New Lams No And App Instructions"
source: "Manual Instructions on Updating Clients to New Lams No and App instructions.doc"
tags: [Overview and Introduction]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Instructions on Updating Clients to New Lams No"
long_description: "Instructions on Updating Clients to New Lams No. format."
---


Instructions on Updating Clients to New Lams No. format.

    • Make sure all sales are closed including sales on laptop servers.
    • Take a note of the latest Sales Ledger figure and Outstanding Cheque
      figure from current system.
    • Take a safe copy of the Master and Nlprogs folder into a safe folder
      (PreNewLamsNo)
    • Delete all Exe’s from the Nlprogs folder. On Main Servers this will be
      on the Z: and C: drive, Laptop Servers generally R: & C: drive and the
      C: drive on thick client PC’s.
    • Once deleted check that there are no exes in this folder so that we
      know there were no programs loaded in memory etc and could not be
      deleted. This would therefore not get updated.
    • Send up the new Lams No. exe apps (currently residing on the VB drive
      VB\NASPROGS\QB\NLPROGS) and copy into the Nlprogs folder above.
    • Copy the latest NLDBDEF.TXT file into the debtdir folder – don’t
      forget laptop server as well.
    • Add a new file “NEWVB18” to the debtdir folder on the main server.
    • Add the following to Sysinfo with a “Y” if not already there.
      RECONMENU1, SLEDGER1 & SLEDGER5.
    • If running Debts2mysql then this needs to be stopped and INSTSRV.EXE &
      SRVANY.EXE copied back into C:\NLPROGS on the main server from backup
      folder in the Nlprogs folder from bullet point 3.
    • Run the new system and check that the Sales Ledger & Outstanding
      cheques match from bullet point 2.
   NAS upgrade to version 7 app.


   DO NOT DELETE THE EXES IN C:\NLPROGS on the server the app  expects  them
   to be there.


   Make sure supporttool.exe is not running.


   Copy the app and folder (nas7upgrade)  to  the  users  desktop.  Run  the
   NAS7.exe. The folder contains the latest NAS exes  which  must  be  in  a
   folder called NAS7. It also contains the latest nldbdef file, sysinfo.ini
   file, salefile.ini and newvb18 file. These files will be copied into  the
   master folder by the app. The exes inside the NAS7 folder will be  copied
   to the nldata\nlprogs folder by the app.


   [pic]


   When you load the upgrade util app it will remind you to check  that  all
   sales are closed. You need to ask the user and check this out.  You  also
   need to note the sales ledger figure before you run the upgrade.


   [pic]


   The app auto defaults to our most common settings.  Amend  these  if  you
   need to. Click the Run Upgrade button.


   What the app does:


Takes a safe copy of the debtdir (market/master) folder and  puts  it  in  a
new folder within nldata prenewlamsnom\master
Takes a safe copy of nlprogs and puts it in prenewlamsno\exes
The app deletes all exes from c:\nlprogs and the nldata\nlprogs

These files (nldbdef,newvb18,sysinfo.ini) are  copied  from  app.path  (i.e.
from within the desktop folder you copied onto  their  PC)  to  the  debtdir
folder.

NASDEBTS is stopped by the app if it is running

The app uses app.path to copy the exes from nas7 to nldata\nlprogs

IMPORTANT!!
The user needs to  run  the  NAS  icon  to  copy  these  programs  from  the
nldata\nlprogs folder to the c:\nlprogs folder this then triggers the  table
def checker. Then close NAS before doing the next part of the update.

Run the ledger updater button to convert the ledger and cheque rec

[pic]

[pic]

The app can clear all old week number files. It will take  a  safe  copy  of
sroll*.* and put it in a sroll folder within the salefolder.
It will take a safe copy of copy invoice andcopy cheque files and  place  in
a COPIES folder within the sale folder.

[pic]

Additional Options

[pic]

Convert Markname to Office table does what it says  on  the  tin,  it  loops
through the markname file and converts the records into the  offices  table.
This process is necessary for the new auto sale number system. It will  only
convert the data once, and warn if there are already records in the  offices
table so you can’t run it twice and duplicate the data.

[pic]

The Setup Sale Nos populates a new table with sale  suffixes  A-Z  and  1-9.
There are 35 possible sale/week number suffixes. Each suffix may be  used  a
maximum of twice so there are more than enough to cover the  50  records  in
markname. This table contains the next sale number  available  for  a  given
suffix, the suffix and the year. Again there is a safety feature to stop  it
being run twice by mistake.

[pic]
