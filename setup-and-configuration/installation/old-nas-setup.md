---
title: "Old Nas Setup"
source: "old - NAS SETUP.doc"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "NAS _SETUP SECTION 1 SERVER SETUP – MAIN MARKET • Make sure all sales closed"
long_description: "SECTION 1 SERVER SETUP – MAIN MARKET"
---


                                 NAS _SETUP

SECTION 1
SERVER SETUP – MAIN MARKET

    • Make sure all sales closed.
    • Create folder on c: of server called NLDATA and share it.
    • Map – N:\  nldata on server  (will change to Z: later on)
    • Copy all sale folders inside nldata, Find out which ones they still
      use for different markets or remote sales.
               ▪ delete old week numbers in all sale folders after copying
                     • Easy way is to create a batch file as follows. Edit
                       delwt.bat.
                    Del *.0??
                    Del *.1??
                    Del *.2??
                    Do this up to 9. then
                    Del *.ocx
                    Del *.dll
                       • Then in each sale folder run delwt

         o You need to edit repsdone in each sale folder. Check the week
           number for each sale, type\mon\date = 21.h. Then edit
           repsdone.21h, put more then 22 Y in.
    • Create NLPROGS folder (to go on C: and in nldata folder). Add programs
      into folders.
    • Create or copy ROOTOFF folder (debtdir,prodrive,counts2)
         o Add connect2
                 192.168.30.10
                 newlinesql
         o Add debtdir
                 Z:\MARKET\
                 Z:\MAFF\
                 Z:\FAXDIR\
                 Z:\
                 LAN
                 SPARELINE
                 Z:\ARCHIVE\
                 Z:\ZIPARC\
                 SPARELINE
                 UK
                 1
                 1001
                 Z:\UPLOAD\
                 Z:\DOWNLOAD\
                 Z:\WISDATA\
                 192.168.30.10 (or servername)
                 NEWLINESQL
                 192.168.30.10 (or servername)
                 NEWLINESQL
                 Z:\
                 Z:\MARKET\
                 C:\NLPROGS\


    • Create a folder on the C: called B4NASinstall.
               ▪ MOVE all sale folders, market folder and programs folder.
               ▪ This acts as backup and so people can’t go into old
                 system by mistake.
    • Create a ‘temp folder’ called MUSTHAVE.
         o Create a file called ‘ VBINPUT’ (edit vbinput) which contains
           the word YES (this is so Lots open in VB and not QB)
         o Create a file called ‘SALEFOLDER’ which contains the character =
            Y
      (might need LIVE in here)
         o Create a file called ‘CDB.INI’ which contains the character =  Y
         o Create file called ‘DATATRAN’ (replaces old datatran, must
           contain following)
                          o HEAD
                          o STATESEC
                          o COMFILE
                          o EXTRADED
                          o EXTRADES
                          o SHPSECT
                          o DATE
                          o DBREEDS
                          o CBREEDS
                          o COUNTS2.SAF
                          o MARKET


         o Create file called ‘PRODRIVE’ which contains
                          o C:\NLPROGS\
                          o C:\NLPROGS\
                          o C:\NLPROGS\


         o Run chkhold holdings exe in N:\market
               ▪ C:\rootoff, then z:\market then,
               ▪ In Dos = N:\market>\nlprogs\chkhold holdings (check case)


         o Remake index using VB version of VMAKIND.exe in market folder
           N:\market>\nlprogs\vmakind.exe n:\market\(NASBEND)c:\rootoff\


         o Copy from the MARKET folder to the MUSTHAVE folder
               ▪ N:\market (location)
                     • Copy ?. \musthave
                     • Copy ?BK. \musthave
                     • Copy P?. \musthave
                     • Copy ?.IND \musthave
               ▪ Copy counts1, counts1.saf, counts2, counts2.saf
                 (copy counts1 \musthave)


    • You cannot use the MARKET folder to run a market anymore as it’s the
      master folder only. Therefore you must copy the MARKET folder and call
      it another name to run it as a sale, in this example we call it
      ‘SAILSBURY’
    • Then tidy up the SAILSBURY folder so it doesn’t contain all the master
      bits like the 2004, 2005 and 2006 folders.
    • Therefore now in NLDATA we have a SAILSBURY folder and MARKET folder.
      You will also need to copy the MAFF and OCX folders to NLDATA.
    • Copy all the data in the MUSTHAVE folder to each of the sale folders &
      market folder. Also copy dobcheck to all livestock sale folders –
      Create file, edit dobcheck, file should contain info below.
                 29
                 31071996


    • If not already done - on server create C:\NLPROGS (and copy exes over)
    • Copy ARCHIVE to NLDATA
    • Create folder called ZIPOLD in NLDATA, then MOVE across 2006 files
      from old zipold folder.
   :
    • Add a shortcut to the desktop from NLPROGS for nas.exe
         o Change target –
         o c:\NLPROGS\nas.exe c:\ROOTOFF\(AUCTION)C:\ROOTOFF\
         o Start in – c:\NLPROGS
    • If in Scotland – Edit MARKNAME in the Market(master) folder and put an
      ‘S’ in position 21 (to send movements)
    • Now disconnect all mapping. Then map Z:\ NLDATA on server

    • From the Office make sure you have a fresh copy of
      d:\marprogs\mysqldef
         o Inside the folder open the centeraldbsql.txt
         o Open up MYSQL control center as well. In the centeraldbsql.txt
           find the sql to create these following tables and run it in
           control centre.
         o For example: (copy and paste in SQL CC)

CREATE TABLE UserAccessTypes (
  AccessTypeID int(11) NOT NULL auto_increment,
  TypeDes char(20) default '',
  AccessDes char(50) default '',
  Deleted char(1) default 'N',
  Primary Key (AccessTypeID)
) TYPE=MyISAM;


               • userdetails  (including the insert at the end – ONLY FOR
                 REMOTE SITES)
                     • in the table change the newline password = LETMEIN
                     • add a users for remote market, eg SHAFTS & LETMEIN
                     • accesstypeid = 1 (master)
                     • The RSID must be the same as the USERID
               • sysinfo
                     • Add\Amend row – CenteralDB,  Y  (case sensitive)
               • useraccesstypes
               • rsculog
               • In ‘Livesalecatinfo’ – Add - TBarea (char 3), FAssured
                 (char 1) FANo (Char 6) & Remarks (Char 30)
               • remote servers
                     • change names, same order as users. 1)Lan2)Kend3)Lap
               • debts
                     • this table will fill with data when you run the
                       schedule (see below – debts2mysql.exe)



               ▪ On the SERVER you need to install the debtstomysql script
                 which creates a rootdebts folder and runs debtstomysql.exe
                 as a service.
        OR
               ▪ On the SERVER you need to create a schedule (if the
                 market has more then one site)

         o Set the schedule to run daily around 5am, only takes few minutes
         o Get it to Run – debts2mysql.exe (c:\nlprogs)
         o You will need to enter the administrator username and password
         o In the Advanced menu –
               ▪ change the STARTIN – c:\rootoff
               ▪ Change the RUN – c:\nlprogs\debts2mysql.exe
                 c:\rooftoff\(DEBTS)c:\rootoff\


         o Check this is working – will fill the debts table in mysql
      If this doesn’t work then try emptying the ‘updatecontrol’ mysql
      table.
      (check no NULL values in updatecontrol – will not update if there is)


                             OPEN NAS on SERVER

    • Login, go to 9, then 3
         o Select the office on the left, check salename box, then in the
           combo box (folder name) choose the right sale folder, then add
           100 to the customers to setup box. Holding number should be same
           for market sales but not for remote sales. Make sure you click
           save each time.
   [pic]







    • TESTING CUSTOMER UPDATES
         o Main menu,  go to 1 (customer search). Search for e.g A1.
               ▪ Put some xxxxxxxxxxxx in an address field then click on
                 SAVE. This will then update every sale folder.
               ▪ See diagram- below

[pic]

         o To Test this go to DOS.
               ▪ Z:\MARKET, then edit /250 A
               ▪ Z:\CARPETS, then edit /250 A
         o Check the details in a few different sales


    • Then try entering a new customer and checking they show up in each
      folder



   ON EACH CLIENT MACHINE


      • Change the mapping to z:\nldata on server
      • Copy NLPROGS to c:\
      • Copy ROOTOFF to c:\
      • Add shortcut to desktop from nlprogs (with target changed)
C:\NLPROGS\NAS.EXE C:\ROOTOFF\(AUCTION)C:\ROOTOFF\











SECTION 2

REMOTE SERVER OR LAPTOP  SERVER
(example shaftesbury – Needs INTERNET CONNECTION)

    • Create folder in c:\
         o ROOTSHAFTS (ROOTKENDAL – other market sales)
         o ROOTOFF
         o ROOTREMOTE (LAPTOP SALES


    • Add to c:\nldata
         o OCX
         o SHAFTS, LFARM, LMACH (remote sale folder)
         o MASTER (Rename market folder to master, copied from server)
         o NLPROGS


Work Locally – Main Site

    • Create Icon (batch file) to run sales at main site (sailsbury -
      rootoff)
         o Type start.bat
               ▪ Net use z: /delete
               ▪ Net use r: /delete
               ▪ Net use z: \\server\nldata
               ▪ C:\nlprogs\nas.exe c:\rootoff\(AUCTION)c:\rootoff\


Working at Remote Market Site (with internet connection –shafts, Kendal
etc)

    • Create Icon (batch file) to run sales at remote site (shaftesbury –
      rootshafts)
         o Type start.bat
               ▪ Net use z: /delete
               ▪ Net use r: /delete
               ▪ Net use z: \\acer1\nldata
               ▪ C:\nlprogs\nas.exe c:\rootshafts\(AUCTION)c:\rootshafts\

[pic]







         o Change the debtdir in rootshafts / rootkendal folder – see next
           diagram
                       Z:\MASTER\
                       Z:\MAFF\
                       Z:\FAXDIR\
                       Z:\
                       LAN
                       SPARELINE
                       Z:\ARCHIVE\
                       Z:\ZIPARC\
                       SPARELINE
                       UK
                       1
                       1001
                       Z:\UPLOAD\
                       Z:\DOWNLOAD\
                       Z:\WISDATA\
                       192.168.52.10             (remote server IP)
                       NEWLINESQL
                       192.168.30.10
                       NEWLINESQL
                       \\192.168.30.10\NLDATA\
                       \\192.168.30.10\NLDATA\MARKET\
                       C:\NLPROGS\

 • Make sure ‘MARKNAME’ is in the MASTER folder on the laptop server. (if
   not copy from MARKET on main server.
      o In DOS in master folder – edit /255 markname
      o Delete all folder names (position 33) apart from sale at remote
        site, eg SHAFTS – see below


[pic]


 • Also Add MYSQL to laptop server and Control Center. Add to startup menu.
   Add newlinesql database but with no data in the tables (use
   centeralbdsql.txt to create tables)
 • Copy sysdate and sysinfo from server DB, edit sysinfo table – mainserver
   – N.

 • For the other machines on the remote network

      o Copy ROOTOFF and ROOTSHAFT (in this example) to the client machine
        (c:\) .
      o Use the same START.BAT to run NAS
      o Change debtdir (edit IP for mysql if needed)

SECTION 3

Working at Remote Farmsale (no internet – eg in a field)

    • Edit MYSQL database on laptop sysinfo – Mainserver - N
    • On the remote server laptop
         o Create a folder called ROOTOUT (c:\) and copy contents of
           ROOTOFF into it.
         o Edit connect2
                    10. - IP of office server not laptop server
           newlinesql
         o Edit the debtdir as follows
                       R:\MASTER\
                       R:\MAFF\
                       R:\FAXDIR\
                       R:\
                       LAN
                       NOLINK
                       R:\ARCHIVE\
                       R:\ZIPARC\
                       SPARELINE
                       UK
                       1
                       1001
                       R:\UPLOAD\
                       R:\DOWNLOAD\
                       R:\WISDATA\
                       LAPTOPSERVER
                       NEWLINESQL
                       MAINSERVER
                       NEWLINESQL
                       Z:\
                       Z:\MARKET\
                       C:\NLPROGS\

    • Inside nldata create the followings folders
               • Wisdata
               • Upload
               • Zipold
               • Ziparc
               • Download
               • Archive
         o Copy across the MASTER, NLPROGS and the sales folder, in this
           example its WESSEX and put into the nldata folder.















         o In DOS go to r:\master
               • edit /255 markname
               • Then as before only have the sale names which will be run
                 as remote sales. (Wessex as example)







































    • Copy the normal NAS icon on the desktop. Change the target to ROOTOUT
      rather the ROOTOFF. Change the colour of the Icon to red NAS.

For the client machines in the Remote Sale

    • Copy over the ROOTOUT folder from the server to the C:
    • Edit the debtdir for mysql so it points to server name ( e.g acer2)
      not localhost.
    • Edit the START.BAT file as below

REMOTE FARM SALE LAPTOP BATCHFILE
NET USE Z: /DELETE
NET USE R: /DELETE
NET USE Z: \\SERVER\NLDATA
NET USE R: \\LAPTOP4699\NLDATA
C:\NLPROGS\NAS.EXE C:\ROOTHOLS\(AUCTION)C:\ROOTHOLS\

MAIN SITE BATCH FILE
NET USE Z: /DELETE
NET USE R: /DELETE
NET USE Z: \\SERVER\NLDATA
C:\NLPROGS\NAS.EXE C:\ROOTOFF\(AUCTION)C:\ROOTOFF\

    • Then create shortcut to start.bat on desktop, rename – Remote Auction
      System. Change the colour to the red NAS. Also under properties change
      the cmdline and working to ROOTOUT, (C:\ROOTOUT\START.BAT)

                                    [pic]


    • Then you should have 3 different Icons, Main site, Remote Market and
      Farmsale.



EXTRA NOTES

    • Check other ICONS on server such as sage movements and bacs
