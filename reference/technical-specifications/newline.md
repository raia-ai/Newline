---
title: "Newline"
source: "Newline.pdf"
tags: [Overview and Introduction]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Connect Wise remote support 23 February 2023 12:23 If you need to connect to a clients Computer that isnt on Connect wise send them the..."
long_description: "Connect Wise remote support 23 February 2023 12:23"
---

Connect Wise remote support
23 February 2023    12:23

        If you need to connect to a clients Computer that isnt on Connect wise send them the below link.
        https://connect.newlineasp.com/




        To create the session go to ConnectWise and select the Support Tab and click create.
        Then give the client the session code shown on the right side.




        Alternatively, when they are on the connect.newlineasp.com page ask them to click START for a new
        session. They can then put their name in to the session dialogue so you know who they are.




                                          Newline Page 1
NAS Icon path
14 February 2024   10:52



C:\NLProgs\Nas.exe C:\RootOff\(AUCTION)C:\RootOff\


Vdpool - 0



C:\NLProgs\Nas.exe Z:\USERS\%USERNAME%\ROOTOFF\(AUCTION)Z:\USERS\%USERNAME%\ROOTOFF\




                                                        C:\NLProgs\Nas.exe C:\Roottfa\(AUCTION)C:\Roottfa\




                                       Newline Page 2
No Internet
20 February 2024   10:00




                           Newline Page 3
Changing lot number ranges
29 February 2024   14:44




                           Newline Page 4
Shearwell sticks
12 March 2024    17:23



   https://vimeo.com/910137522/3a4463390a?share=copy



   Know issues. On the laptop HP ProBook 455 15.6 inch G9 Notebook PC
   The best driver is




   When updating to a later driver you cannot use two Shearwell 400 sticks at the same time.




   SDL Connect is the software program for connecting your stick reader to your computer. It allows
   you to retrieve data from your stick reader


   https://media.shearwell.com/Content/Global/Downloads/Distributions/SDLConnect/V-
   Latest/SDLConnectSetup.exe



   Used to send configuration to stick. St to Decimal.




                                           Newline Page 5
Editing BACS Date
21 March 2024   09:29




                        It is a simple task to edit the BACS date, there are a few steps though
                        �
                            1. In the sale � Click about at the top of the screen




                          2. Note the sale directory
                             In the case Z:\WED\
                          3. Browse to the z drive from the file explorer




                          4. Browse to the directory (based on the about tab in the sale)
                          5. Locate the �Date� file
                          6. Open this in Notepad
                          7. IMPORTANT � Only EDIT the bottom Date line and needs to be entered as per below
                             DDMMYY




                                     Newline Page 6
 8. Once edited choose File > Save then close the file
 9. To check you have edited correctly in the market system go to OPTION 25




10. Then Alter Sale Settings




            Newline Page 7
11. This will now show the corrected BACS date




           Newline Page 8
Customer updates error
03 May 2024    15:34




       Check logs for customer update. And check date.

       Also change initial sync to n and try again.




                                            Newline Page 9
Change EID scan date
23 September 2024       10:20




Nigel ran this to change date and now tags showing.

From <https://help.newlineasp.com/agent/newline/newline-asp/tickets/details/107541000022505364>




#UPDATE eidmarketmovements
#SET saledate = '2025-10-10',
  #ondate = '2025-10-10',
# saleno = '04F'
#WHERE saledate = '2025-10-13'
 #AND saleno = '41E';


SELECT * FROM eidmarketmovements
WHERE saledate = '2025-10-10' AND saleno = '04F'




                                               Newline Page 10
NAS Cloud RDP Error
25 September 2024     09:29



                        If you get this error when running NAS Cloud




                    Edit the below regfile and change value to 0




                                          Newline Page 11
Customer Update Error
01 October 2024     15:34




   Some times on laptop servers you get the below. Error.
   Check nas customer service logs.
   Open mysqlcc and change Customer update intialSync Done to N
   Then check the logs




    ERR Error Processing Customer Details From HQ.MySqlConnector.MySqlException
   (0x80004005): Table 'newlinesql.vetattinfo' doesn't exist




   # Host: localhost
   # Database: newlinesql
   # Table: 'vetattinfo'
   #
   CREATE TABLE `vetattinfo` (
     `VAID` int(11) NOT NULL AUTO_INCREMENT,
     `LamsNo` varchar(7) NOT NULL DEFAULT '',
     `Deleted` char(1) NOT NULL DEFAULT 'N',
     `Van` varchar(24) NOT NULL DEFAULT '',
     `Expiry` varchar(4) NOT NULL DEFAULT '',
     PRIMARY KEY (`VAID`)
   ) ENGINE=InnoDB AUTO_INCREMENT=73 DEFAULT CHARSET=latin1;


   Set the below to start the sync.




                                      Newline Page 12
Nas server install.
21 June 2023    10:49




Copy data from old server from:
Rootoff                                                                                                                                            NAS Server Install – Laptop Swap
Nldata                                                                                                                                             Date: 21 June 2023
mysql                                                                                                                                              Engineer: [Name]

Use robo copy to copy nldata
Example*                                                                                                                                           1. Data Copy from Old Server
robocopy \\laptop16759\nldata c:\nldata /mir /xd nasdatahost cleanup "$recycle.bin" "system volume information" /xf *.log /w:5 /r:5                Copy the following directories from the old server to the new laptop:
                                                                                                                                                     • RootOff
robocopy \\martserver\nldata c:\nldata /mir /xd nasdatahost cleanup "$recycle.bin" "system volume information" /xf *.log /w:5 /r:5                   • NLData
                                                                                                                                                     • MySQL
robocopy \\martserver\nldata c:\NLData /mir /xd nasdatahost cleanup "$recycle.bin" "system volume information" /xf *.log /w:5 /r:577               Example Robocopy Command
robocopy "\\laptop15749\nldata" "C:\NLData" /MIR /XD "nasdatahost" "cleanup" "$recycle.bin" "system volume information" /XF *.log /W:5 /R:5        robocopy \\laptop16759\nldata c:\NLData /mir /xd nasdatahost cleanup "$recycle.bin" "system volume
                                                                                                                                                   information" /xf *.log /w:5 /r:5
                                                                                                                                                   For martserver copy:
[15:34] Andrzej Siemieniago
                                                                                                                                                   robocopy \\martserver\nldata c:\NLData /mir /xd nasdatahost cleanup "$recycle.bin" "system volume
need to export mysql
                                                                                                                                                   information" /xf *.log /w:5 /r:5
                                                                                                                                                   2. MySQL Migration
[15:34] Andrzej Siemieniago
                                                                                                                                                   Export (Old Laptop)
in tool \ newline tools \dbdump.scapp                                                                                                                1. Launch: \Newline Tools\dbdump.scapp
                                                                                                                                                     2. Connect to Newline SQL
                                                                                                                                                     3. Tick Export Stored Procs
                                                                                                                                                     4. Export database to file




Click connect and selecet newline sql


                                                                                                                                                   3. SQL Import (New Laptop)
                                                                                                                                                     1. Enable SQL service on new laptop.



                                                                                                                                              1.




                                                                                                                                                     1. Create and import database:

                                                                                                                                                          create database newlinesql;
                                                                                                                                                          use newlinesql;
                                                                                                                                                          source C:/NLData/Exports/MySQL/newlinesql.sql;

                                                                                                                                                     2.




Copy vba setting from




                                                                                                                                                                                                                                                        Step 1 – Check the
                                                                                                                                                                                                                                                        attributes
                                                                                                                                                                                                                                                        Run this in Command
                                                                                                                                                                                                                                                        Prompt (as admin):

                                                                                                                                                                                                                                                        attrib C:\NLData
                                                                                                                                                                                                                                                        If you see H (Hidden) or S
                                                                                                                                                                                                                                                                    x           ’
                                                                                                                                                   4. VBA Settings                                                                                             ’ v
                                                                                                                                                      • Copy VBA settings from old laptop (registry or config file as appropriate).
                                                                                                                                                                                                                                                        Step 2 – Remove
                                                                                                                                                                                                                                                        the hidden/system
                                                                                                                                                                                                                                                        attributes
                                                                                                                                                                                                                                                        Run:

                                                                                                                                                                                                                                                        attrib -h -s C:\NLData /s /d
                                                                                                                                                                                                                                                           • -h → removes hidden
                                                                                                                                                                                                                                                               attribute
                                                                                                                                                                                                                                                           • -s → removes system
                                                                                                                                                                                                                                                               attribute
                                                                                                                                                                                                                                                           • /s → apply to all files
                                                                                                                                                                                                                                                               inside
Enable sql service on new laptop                                                                                                                                                                                                                           • /d → apply to
                                                                                                                                                                                                                                                               directories
                                                                                                                                              •
                                                                                                                                                                                                                                                        Step 3 – Refresh
                                                                                                                                                                                                                                                        Explorer
                                                                                                                                                                                                                                                           • Press F5 in the
                                                                                                                                                                                                                                                             window, or
                                                                                                                                                                                                                                                             close/reopen Explorer.
                                                                                                                                                                                                                                                           • You should now see
                                                                                                                                                                                                                                                             the folder normally.




                                                                                                                                                   5. Stop Old Services (Old Laptop)
                                                                                                                                                   Before decommissioning the old laptop, stop and disable NAS services:

                                                                                                                                                   Get-Service -Name nas* | Set-Service -StartupType Disabled
                                                                                                                                                   Get-Service -Name centralink | Set-Service -StartupType Disabled
                                                                                                                                                   Get-Service -Name mysql | Set-Service -StartupType Disabled
Open below
                                                                                                                                                   6. Export/Import CentralLink

                                          Newline Page 13
                                                                            5. Stop Old Services (Old Laptop)
                                                                            Before decommissioning the old laptop, stop and disable NAS services:

                                                                            Get-Service -Name nas* | Set-Service -StartupType Disabled
                                                                            Get-Service -Name centralink | Set-Service -StartupType Disabled
                                                                            Get-Service -Name mysql | Set-Service -StartupType Disabled
Open below
                                                                            6. Export/Import CentralLink
                                                                              1. Export registry key from old laptop:

                                                                                 Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\centrallink
                                                                              2. Import into new laptop server.



                                                                            7. Domain & Connectivity Setup
                                                                               • Create domain account on laptop
                                                                               • Add \\martserver link to HQ
                                                                               • Add credentials for both IP and DNS



                                                                            8. Register DLLs Standard DLLs
                                                                            regasm NasPrinting.dll /c /t
                                                                            regasm Nas.Email.Composer.dll /c /t
                                                                            regasm NasDataTransfer.dll /c /t
                                                                            regasm NasWebServices.dll /c /t
                                                                            regasm NASGemDoc.dll /c /t
                                                                            regasm NasCommon.dll /c /t
                                                                            Canada Only
                                                                            regasm NASResources.dll /c /t
                                                                            regasm NASCharges.dll /c /t



                                                                            9. NAS Data Host Setup
                                                                              1. Configure NAS Data Host (Run as Admin):

                                                                                 "C:\NLData\NLProgs\ConfigureNasDataHost.exe"
                                                                                    ○ Click Save first, then Install
                                                                              2. Auto-update NAS Data Host:

create database newlinesql;                                                      "C:\NLData\NLProgs\AutoUpdateNasDataHost.exe"
use newlinesql;                                                               3. Install NAS Server (installer .txt found in Newline installers folder)

Source C:\Newline\Exports\newlinesql.sql;
C:/NLData/Exports/MySQL/newlinesql.sql;
                                                                            9. Install NAS Services

When SQL installed on new Laptop remember to RUN the below.
Only if clean laptop and not sent from Newline




                                                                            12. Final Tasks
                                                                               •   Run .NET Framework script
                                                                               •   Import/export printers
                                                                               •   Migrate Datto RMM to new laptop (remove from old)
                                                                               •   Confirm Debt Dir → update Share Name and Server ID
From <https://teams.microsoft.com/v2/>                                         •   Toolbox → Newline Tools → Hide Accounts 64


                                                                            13. Troubleshooting
Stop all nas servers on old laptop                                             • SMS report not loading:
                                                                                   ○ Check NAS Data Host ports in DB match configuration
                                                                               • Ensure NAS services all running
                                                                               • Test client connections


                                                                            7. Final Steps
                                                                               •   Confirm NAS services are running on new laptop.
                                                                               •   Validate SQL connectivity and database access.
                                                                               •   Check CentralLink service is registered and functioning.
                                                                               •   Perform test connections from client machine(s).
                                                                               •   Decommission old laptop once testing is complete.




Stop and disable mysql




Get-Service -Name nas* | set-Service -StartupType Disabled
get-service -name centralink -StartupType Disabled
get-service -name mysql -StartupType Disabled




Export centrallink from old laptop server

Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\centrallink




                                            Newline Page 14
Import into new laptop server




                                Newline Page 15
Inport vba settings


Create domain account from laptop and add \\martserver link to HQ




Add creads for both ip and dns




                          Newline Page 16
regasm NasPrinting.dll /c /t
regasm Nas.Email.Composer.dll /c /t
regasm NasDataTransfer.dll /c /t
Regasm naswebservices.dll /c /t
Regasm NASGemDoc.dll /c /t
Regasm Nascommon.dll /c /t

c:\nlprogs\regasm NasPrinting.dll /c /t
c:\nlprogs\regasm Nas.Email.Composer.dll /c /t
c:\nlprogs\regasm NasDataTransfer.dll /c /t
c:\nlprogs\Regasm naswebservices.dll /c /t
c:\nlprogs\Regasm NASGemDoc.dll /c /t
c:\nlprogs\Regasm Nascommon.dll /c /t



Canada only
NASresources.dll
NAS Charges.dll




Share name and server ID need to be changed in




Debt dir


Toolbox - newline Tools - Hide accounts 64




Confguiure nas data hosr run as admin




                          Newline Page 17
Click save first then install

"C:\NLData\NLProgs\ConfigureNasDataHost.exe"


Auto update nsa data host
"C:\NLData\NLProgs\AutoUpdateNasDataHost.exe"


Install nasserver . Txt file found new newline installers.




$path="Z:\Services"

if (-not (Test-Path $path)) {
   if (Test-Path 'C:\NLData\Services') {
       $path='C:\NLData\Services'
   } else {
       $path = $null
   }
}

if ($path -ne $null) {
   $NASServices = Get-ChildItem (Join-Path $path "NAS.*") -Directory
   foreach ($NASService in $NASServices) {
     if ((Get-Service $NASService.Name -ea Ignore) -eq $null) {
         $exe = Join-Path $NASService.FullName "$($NASService.Name).exe"
         New-Service -Name $($NASService.Name) -BinaryPathName $exe -StartupType Automatic -Verbose
     } else {
         Write-Output "Service $($NASService.Name) is already installed"
     }
   }
}
Start-Service -Name nas* -verbose
Pause




Run dot fram work script.


Import and export printers.

Datto rmm on new laptop remove from old.




                                                                                               4XDKJ -HCX7W-4MHXG-7J6PD-64VXZ




         If it is the first laptop server on site. Follow this. Also.

         Setting up NasDataHost

         From <https://help.newlineasp.com/support/newline/ShowHomePage.do?
         insideReactApp=true&articlestatus=latest&rootcategoryId=107541000000150202&categoryId=107541000005612949
         #Solutions/dv/107541000005614284/en>

         INSERT INTO SysInfo (KeyName,KeyCode) VALUES ('CustomerUpdate_Enabled','Y');INSERT INTO SysInfo
         (KeyName,KeyCode) VALUES ('DebtlistSync_Enabled','Y');INSERT INTO SysInfo (KeyName,KeyCode)
         VALUES ('NasDataHostAddress','net.tcp://martserver:52351');INSERT INTO SysInfo (KeyName,KeyCode)
         VALUES ('CustomerUpdate_FileUpdateType','1');INSERT INTO SysInfo (KeyName,KeyCode) VALUES
         ('DataReplicationSimple_Enabled','Y');INSERT INTO SysInfo (KeyName,KeyCode) VALUES
         ('DataReplicationSimple_HQListen','http://martserver:52352');INSERT INTO SysInfo (KeyName,KeyCode)
         VALUES ('DataReplicationSimple_EndPoint','http://martserver:52352');INSERT INTO SysInfo
         (KeyName,KeyCode) VALUES ('NEWSALETRANSFER','Y');INSERT INTO SysInfo (KeyName,KeyCode)




                                Newline Page 18
(KeyName,KeyCode) VALUES ('NEWSALETRANSFER','Y');INSERT INTO SysInfo (KeyName,KeyCode)
VALUES ('NASDATATRANSFERSERVER','http://martserver:2012/NasDataTransfer/mex')




SELECT *
FROM `sysinfo`
where keyname in
('CustomerUpdate_Enabled','DebtlistSync_Enabled','NasDataHostAddress','USENEWEMAILSERVICE','USINGN
EWEMAILSERVICE','CustomerUpdate_FileUpdateType','DataReplicationSimple_Enabled','DataReplicationSim
ple_HQListen','DataReplicationSimple_EndPoint','NEWSALETRANSFER','NASDATATRANSFERSERVER','ServerID
')




                                                                                                      $path="Z:\Services"

                                                                                                      if (-not (Test-Path $path)) {
                                                                                                         if (Test-Path 'C:\NLData\Services') {
                                                                                                             $path='C:\NLData\Services'
                                                                                                         } else {
                                                                                                             $path = $null
                                                                                                         }
                                                                                                      }

                                                                                                      if ($path -ne $null) {
                                                                                                         $NASServices = Get-ChildItem (Join-Path $path "NAS.*") -Directory
                                                                                                         foreach ($NASService in $NASServices) {
                                                                                                           if ((Get-Service $NASService.Name -ea Ignore) -ne $null) {
                                                                                                               Stop-Service $NASService.Name -Verbose
                                                                                                               Remove-Service -Name $NASService.Name -Verbose
                                                                                                               Write-Output "Service $($NASService.Name) has been removed"
                      SMS report not loading with this error.                                              } else {
                                                                                                               Write-Output "Service $($NASService.Name) is not installed"
                          ’          v              k                                                      }
                                                                                                         }
                                                                                                      }
                                                                                                      Pause




                 Newline Page 19
Race reader
07 February 2024   11:23




                           How to install Download only.




                           Install MySQL-x64 using below
                           Toolbox , newline tools, Installers, Mysql-x64




                                     Newline Page 20
C:\ProgramData\MySQL\MySQL Server 5.1\data




                   C:\NLProgs\sheeppeneid.exe (PENREADING)C:\ROOTOFF\




         Newline Page 21
         C:\NLProgs\sheeppeneid.exe (RACEREADING)C:\ROOTOFF\
         C:\NLProgs\sheeppeneid.exe (PENREADING)C:\ROOTOFF\




                     eidsql                       https://newlinemail-my.sharepoint.com/personal/steven_newlineasp_com/Documents/Steven%20@%
                                                  20Work%20-%20Linked%20Files/how%20to%20setup%20sheep%20eid.mp4




                      Aten adapter driver
                      Prolific driver,




         (ONLINE) C:\NLProgs\sheeppeneid.exe (PENREADING)C:\ROOTOFF\
         (OFFLINE) C:\NLProgs\sheeppeneid.exe




Newline Page 22
Bacs file reset delete
05 November 2024    15:02



   Sometimes users will want a BACs files deleted.




   Remove the file in the shown location.

   Then go to server and run the below sql
   Remember to change the sale and date.

   query for recreating bacsfile
   UPDATE salecheques
   set inbacsfile = 'N'
   where weekno = '44S' and dateof = '2024-11-02' and inbacsfile = 'Y'


   How to check if it worked.
   Go into the sale.

   11 Seller reports menu

   11 Create BACS

   Check both match.




                                                                         query for recreating bacsfile

                                            Newline Page 23
                  query for recreating bacsfile
                  UPDATE salecheques
                  set inbacsfile = 'N'
                  where weekno = '27T' and dateof = '2025-07-03' and inbacsfile = 'Y'




Newline Page 24
Anti-Virus - AV Exceptions required for NAS
11 November 2024   09:02



              [Workstation]

              C:\nlprogs\*
              C:\rootoff\*
              Z:\*                         (mapped drive to the NAS server)
              R:\*                         (mapped drive to the remote NAS server)
              \\[server hostname]\nldata\*               (i.e. \\martserver\nldata\*)
              \\[server fqdn]\nldata\*               (i.e. \\martserver.nas.local\nldata\*)
              \\[server ip address]\nldata\*            (i.e. \\192.168.1.53\nldata\*)
              outbound traffic to port 3306/tcp on the Newline Auction System server.
              outbound traffic to ports 52351-52352/tcp* on the Newline Auction System server
              * - these ports are configurable, so please check that they are in use in your environment.
              [Newline Auction System Server]

              C:\nlprogs\*
              C:\Newline\*
              Z:\*
              R:\*
              C:\nldata\*
              C:\programdata\mysql\mysql 5.1\*
              \\localhost\nldata\*
              \\[server hostname]\nldata\*             (i.e. \\martserver\nldata\*)
              \\[server fqdn]\nldata\*             (i.e. \\martserver.nas.local\nldata\*)
              \\[server ip address]\nldata\*          (i.e. \\192.168.1.53\nldata\*)
              C:\Program Files\Newline ASP\*
              C:\Program Files (x86)\Newline ASP\*
              inbound traffic from local network to port 3306/tcp

              inbound traffic from local network to ports 52351-52352/tcp*
              * - these ports are configurable, so please check that they are in use in your environment.




                                         Newline Page 25
How to change sale Name
12 November 2024    09:52




Enter sale.

Option 25




Option 6




Then change name.




                            Newline Page 26
Newline Page 27
Close unwanted Sale.
12 November 2024   09:54



GO to SALE and Use code NL98




                               Newline Page 28
Disable payment links
12 November 2024   11:25



                             Add the payment link record or change to 99999 to disable,




                           PAYMENTLINKS_PROMPT_THRESHOLD




                            Newline Page 29
Change Sale date
19 November 2024      12:07




  1.   On the NAS server, open NAS as NL.
  2.   Select the sale.
  3.   Type 997 in the selection box and enter
  4.   Choose 15. Editor
  5.   Select 'change sale date'
  6.   Use the dropdown calendar to select the new date.
  7.   Select OK and wait for confirmation, then exit out.




                                           Newline Page 30
                  Bart and I have made the below progress today.

                  VM Creation:
                  Two new VMs have been created and added to the cluster.
                    • WebServer2024
                    • WebData2024

                  Software Installation:
                     • ConnectWise Software
                     • Action1
                     • Bitdefender
                     • Datto RMM

                  Webserver2024 Setup:
                    • Installed IIS (Internet Information Services)
                    • Windows Updates

                  WebData2024 Setup:
                    •




Newline Page 31
How to send bulk emails for unpaid invoices.
09 December 2024        16:54




TE


From <https://help.newlineasp.com/agent/newline/newline/tickets/details/107541000024411158>




                                               Newline Page 32
Sale Transfer done but not Showing at HQ
17 January 2025    09:28



Be sure to Check the REPSDONE.xxx file in the sale folder at HQ.
Delete this file and it will work




                                                    https://help.newlineasp.com/agent/newline/newline/tickets/details/107541000025082001




                                          Newline Page 33
Wyse terminal
27 January 2025   12:01

                  Authentication certificate error.
                  Check Account password
                  Then check date and time in the control panel settings. To resolve.




                                        Newline Page 34
Phone System
10 February 2025     15:32




Just FYI.
Luke and Gary both have mentioned that we are getting a scamy phone calls from "British Gas"
asking for unnecessary details and saying that payment need to be amended etc (the usual)
I have setup blocked callers rule in Teams now to block anonymous calls as they all appear from
them.
The details on how to set them up is here:
Block inbound calls in Microsoft Teams - Microsoft Teams | Microsoft Learn

and the rule looks like this:




Just FYI in case it needs to be changed/removed

Learn how to use PowerShell to manage inbound call blocking.

Block inbound calls in Microsoft Teams - Microsoft Teams | Microsoft Learn




                                         Newline Page 35
Common NAS issues
14 March 2025       15:48




just a note to everyone here - These are solutions i have in my list i thought i would share the
knowledge on

(2) #75234 - Missing Item code                   In ticket
Newline
#75365 -        Website - Events list not        In ticket
Newline         showing all instances
#75393 -        Calvat - Flat rate topup         Calvat file has 4.8 & 0.3 in file and AlterCalVat25 in
Newline                                          sysinfo
#75412 -        Error connecting to NAS          Sign into the NAS main program first
Newline         Cloud Explorer
                Customer locked in invoices      Clear lock file by clicking ok then typing 999 into the
                but no account on it             box the system goes into
#75479 -        Heads split across 2 totals      Replace the & sign in item type editor to a +
Newline
#75585 -        Payment on invoice needs         Notes in ticket
Newline         removing
#75721 -        Account with no invoice          Notes in ticket
Newline         appearing in list
#75743 -        Historical debt list showing     Go into ledger - option 9 - click options - go historical -
Newline         wrong figure                     set date range - go for the one at the end of the day
                                                 not first thing in the morning
(2) #76284 - Onward movement not send In ticket
Newline      (ICE)
#76379 -        NL98d the wrong sale             Clear repsdone in the sale folder
Newline
#77134 -        Database lockup                  Kill the longest task in DB
Newline
(1) #77241 - Unable to do movement as            In ticket
Newline      herd closed but were open
             during sale
#77830 -        Recreate BACS File               In ticket
Newline
(1) #76588 - NasDisplaySystem setup              In ticket is the registry path
Newline




                                               Newline Page 36
Register DLLS
17 March 2025    09:59



c:\nlprogs\regasm NasPrinting.dll /c /t
c:\nlprogs\regasm Nas.Email.Composer.dll /c /t
c:\nlprogs\regasm NasDataTransfer.dll /c /t
c:\nlprogs\Regasm naswebservices.dll /c /t
c:\nlprogs\Regasm NASGemDoc.dll /c /t
c:\nlprogs\Regasm Nascommon.dll /c /t

c:\nlprogs\Regasm NasCharges.dll /c /t




                                         Newline Page 37
Cow and calf display
20 March 2025     14:45




Luke Taylor
.
Private
.
11 Feb 04:29 PM
Read the ticket and understood so spoken to Debbie. She said thank you and she is going to check what they would like it to
be and will change accordingly



Nigel Adams
.
Private
.
11 Feb 11:12 AM
Check over ticket and get back to Debbie explaining why.



Nigel Adams
.
Private
.
11 Feb 11:11 AM




Cow is over 4 years old




For 'Had a Calf' to be added to the remarks this will need to be changed to 49




Luke Taylor
.
Private
.
11 Feb 10:54 AM
.
Edited
Lot number with the issue: 562

Last weeks sale 05/02/25 Sale number: 046




                                            Newline Page 38
Nigel Adams
.
Private
.
11 Feb 09:58 AM
Luke can you call Debbie and advise that this may relate to DOB as didn't happen on all Cows. If you don't understand I can
explain in more detail.

Find out the lot no. in question.



Nigel Adams
.
Private
.
11 Feb 09:55 AM
.
Edited
Gary Bell as always we need more details to investigate this.

What was the sale day and what was the lot no.




I suspect that this wasn't happening on all Cows else Debbie would have said. More than likely the Cow was over 36 months
old which is why it didn't display had a calf.

This is why it's so important to get as much info as possible. Need to know the DOB of animal.




DE

Debbie
.
11 Feb 09:41 AM
( 37 days ago )
from
"Debbie"
Last week they had a Cow that had had a calf but the system did not show that it had had a calf is there a way for the system
to display this on the TV screen.

From <https://help.newlineasp.com/agent/newline/newline/tickets/details/107541000025776016>




                                                                            In a sale,
                                                                            1 pre sale entry
                                                                            Options , animal data checks.




                                               Newline Page 39
Newline Page 40
                                                               #79648
BACS issue
27 March 2025         11:14



AC

Alex Courlander-Whelan
.
Private
.
11:10 AM
Mart advised and file uploaded to the bank
Alex to demo to Bart and Gary.
Huw to demo to Luke and Steven.
AC

Alex Courlander-Whelan
.
Private
.
11:09 AM
Alex notes on this.

from the BACS file you can see the amount - 9329.23
using this go to option 11 and report 7 "List statements / Cheques". Using the amount find out the accounts number

In the account check to see that "Address on Statement Y" is blank

Once this is done manually adjust the BACS File which is stored in Z:\BACSPayments\2025.
Find the record for the sale ed 14W and add the name in after ",," two comma in all capitals same as other records.



Nigel Adams
.
Private
.
10:29 AM
.
Edited
Missing name




                                             Newline Page 41
need to take this Y out of the account and add K.EDWARDS to the BACS file.




BE

Beverley
.
10:20 AM
( 50 minutes ago )
Bev has an issue with the BACS file below- she doesnt know why the top detail has the Barbers name on it and when she
goes to export to the bank it responds with invalid file format?




                                          Newline Page 42
From <https://help.newlineasp.com/agent/newline/newline/tickets/details/107541000027129152>




                                               Newline Page 43
Nas Email error
24 April 2025   11:22




                                –
    Date: 24 April 2025
    Time: 11:22
    Issue:
    Error message on client machine:
    "Error connecting to database. Would you like to retry?"



                                                                                 When sending email and you get this.
                                                                                 Check IPV6 is disabled.




    ✅ Steps to Resolve:
      1. Re-register the required DLLs:

         c:\nlprogs\regasm Nas.Email.Composer.dll /c /t
         c:\nlprogs\regasm NasPrinting.dll /c /t
      2. Verify Registry Setting:
            ○ Ensure EmailComposerV2 is set to Y in the relevant config.



○




      1. If still not working:
             ○ Disable IPv6 on the network adapter of the Laptop Server.
             ○ Confirm the firewall allows TCP port 3306 (MySQL default port).


          Test Network Connectivity from Remote Client:
    Use the following PowerShell commands to test connectivity:

    Test-NetConnection LAPTOP19054 -RemotePort 52352
    Test-NetConnection LAPTOP19054 -RemotePort 52351
    Test-NetConnection LAPTOP19054 -RemotePort 3306


    Test-NetConnection MARTSERVER -RemotePort 3306




                                          Newline Page 44
Nas Slow. SIMPLE Counts2 error
13 May 2025       09:54




See below. #82256

09:52 AM




killed all process trying to access the file:




working now


Andrzej Siemieniago
.
Private
.
09:47 AM




                                                Newline Page 45
PH

Phil
.
09:38 AM
( 15 minutes ago )
.
.

From
"Phil"
All users are experiencing a slow Nas Phil has been waiting 10 minutes for customer details to save




another user keeps getting the following when trying to bring up a customer




                                            Newline Page 46
From <https://help.newlineasp.com/agent/newline/newline/tickets/details/107541000028314118>




                                               Newline Page 47
NewlineToolBox URL
18 July 2025   08:38




        [{"toplevel_name":"Newline
        ToolBox"},{"url":"sway.cloud.microsoft/ZfnBn5PGBbGfCogp","name":"Newline
        ToolBox"},{"name":"Customer Services","children":[{"url":"help.newlineasp.com/","name":"Zoho
        Desk"},{"url":"connect.newlineasp.com","name":"ScreenConnect"},{"url":"admin.auctionmarts.com/","n
        ame":"Auctionmarts Config
        Portal"},{"url":"mms.pay.auctionmarts.com/admin/login.php","name":"Payment Portal"},{"url":"crm-
        admin.newlineasp.com/#/","name":"CRM Admin Portal"},{"url":"cloud.newlineasp.com","name":"NAS
        Cloud"},{"url":"streaming.newlineasp.com/","name":"Streaming Control
        Centre"},{"url":"keepersecurity.eu/vault/#","name":"Keeper Password
        Manager"}]},{"name":"Professional Services","children":[{"url":"projects.zoho.eu/portal/newlineasp1
        #allprojects/175916000000486049/","name":"Backlog (outstanding
        orders)"},{"url":"projects.zoho.eu/portal/newlineasp1#mywork","name":"Your tasks
        (home)"},{"url":"projects.zoho.eu/portal/newlineasp1
        #zp/projects/175916000002264017/tasks/custom-view/175916000000336003/list?
        group_by=tasklist","name":"Project X"},{"url":"projects.zoho.eu/portal/newlineasp1
        #allprojects/175916000001215137/","name":"New Customers
        Projects"},{"url":"projects.zoho.eu/portal/newlineasp1#allprojects/175916000001816061/","name":"IT
        Maintenance Projects"},{"url":"projects.zoho.eu/portal/newlineasp1
        #allprojects/175916000001048455/","name":"Main Projects
        Group"},{"url":"backup.management/","name":"Cove
        Backup"},{"url":"auth.datto.com/login","name":"Datto"},{"url":"cp.rackspace.com","name":"Rackspace"
        },{"url":"app.sendgrid.com/","name":"SendGrid"},{"url":"app.valimail.com","name":"ValiMail"},{"url":"m
        xtoolbox.com","name":"MX
        Toolbox"},{"url":"cp.appriver.com/PP/Default.aspx","name":"AppRiver"},{"url":"unifi.newlineasp.com:84
        43","name":"WiFi - UniFi"},{"url":"unifi.ui.com/","name":"CCTV/WiFi -
        UniFi"},{"url":"app.eu.action1.com/login/","name":"Action1"},{"url":"gravityzone.bitdefender.com/","na
        me":"BitDefender"},{"url":"portal.threatlocker.com/","name":"ThreatLocker"},{"url":"newlinemail.share
        point.com/sites/clients","name":"Clients' sites photos & docs"}]},{"name":"Professional
        Services","children":[{"url":"dev.azure.com/Newline-ASP","name":"Azure
        DevOps"},{"url":"projects.zoho.eu/portal/newlineasp1
        #allprojects/175916000002364033/","name":"R&D Timesheets"}]},{"name":"Sale &
        Marketing","children":[{"url":"crm.zoho.eu/","name":"Zoho CRM - All
        Customers"},{"url":"books.zoho.eu/","name":"Zoho Books and
        Pipeline"},{"url":"survey.zoho.eu/","name":"Zoho
        Survey"},{"url":"campaigns.zoho.eu/campaigns/org20083037119/home.do#dashboard","name":"Zoho
        Campaigns"}]},{"name":"Data Analysis & Reports","children":[{"url":"analytics.zoho.eu/","name":"Zoho
        Analytics"},{"url":"newlinemail.sharepoint.com/sites/WeeklyReport-TeamEffort/Shared%
        20Documents/Forms/AllItems.aspx","name":"Weekly
        Report"},{"url":"analytics.zoho.eu/workspace/155474000000004002/view/155474000002849689","na
        me":"Tickets vs Maintenance"},{"url":"analytics.zoho.eu/open-
        view/155474000003928577","name":"Ticket
        Dashboard"},{"url":"analytics.zoho.eu/workspace/155474000000004002/view/155474000003035847","
        name":"QSR Dashboard"},{"url":"analytics.zoho.eu/open-view/155474000001644023","name":"PC
        Dashboard"}]},{"name":"Jonas","children":[{"url":"jonasbenefits.flexgenius.co.uk/","name":"Flex
        Genius - Benefits"},{"url":"jonassoftware.zendesk.com/","name":"HR
        Zone"},{"url":"wd3.myworkday.com/wday/authgwy/talentmanagementsolution/login.htmld?
        redirect=n","name":"Workday"},{"url":"www.concursolutions.com/","name":"Concour - Expenses"}]}]




                                         Newline Page 48
Nas Install workstation Non newline device
29 July 2025   09:15




NAS (New Line Auction System) – Install Guide (Non-Newline
Laptop)
1. Prep Device
   • Device: Surface19421
   • Domain Account: Domain\19421
2. Enable .NET 3.5
Run in elevated Command Prompt:

Dism.exe /online /enable-feature /featurename:netfx3 /all
   Do this

3. Install NAS Client
   • Download installer:
     http://www.newlineasp.com/installers/nasclient.exe
   • Install only after .NET 3.5 is enabled.

4. Install .NET Runtimes
   • Run bundled installer (example shown in your first screenshot: installdotnet56789.exe).
   • This will install required versions of .NET Hosting & Runtime 5, 6, 7, 8, 9.

5. Join Domain
   • Add device to domain: WHARFDALE
   • User account: 19421

6. Connect to Martserver Shares
Add server via hostname and IP:

\\martserver\NLData
\\192.168.xx.xxx\NLData
Verify access with your domain credentials.
                                                                                                                     Get-ChildItem "C:\NLProgs" -Recurse | Unblock-File
7. Copy Required Folders
   • From \\martserver\NLData\NLprogs → copy to C:\NLProgs
   • Copy RootOff folder → C:\RootOff

8. Firewall Rule for MySQL
   • Ensure inbound firewall rule is added for:

MySQL – TCP 3306

#!ps
#timeout=-1
New-NetFirewallRule -DisplayName "MySQL – TCP 3306" `
  -Direction Inbound `
  -Protocol TCP `
  -LocalPort 3306 `
  -Action Allow `
  -Profile Any `
  -Description "Allow inbound MySQL connections on TCP port 3306"



9. Copy Icons
   • Copy Newline and EID icons from the old desktop to the new device.

10. (For EID Tablet Installs Only)
   • Install MySQL and local EID database (eidsql).
   • Use the Make NAS Server package (from ConnectWise toolbox).

11. Make NAS Server Package Contents
Includes:
   • Install .net (13 KB EXE)
   • Make-NASServer.txt (script notes)
   • my.ini (MySQL config)
   • mysqlcc.zip (MySQL Control Center)
   • mysql-x64.msi (MySQL installer)
   • nasclient.exe (silent NAS client installer)
   • users.txt (MySQL users import)
   • powershell -ExecutionPolicy Bypass -File .\Make-NASServer.ps1

      Clear-Host
      Start-Transcript -Path "$env:Temp\Setup-NasServer.log" -Force

      Write-Host "Enable .NET 3.5"
      Dism.exe /online /enable-feature /featurename:netfx3 /all

      Write-Host "Install MySQL"
      Start-Process -FilePath "${env:windir}\system32\msiexec.exe" -ArgumentList ('/i mysql-x64.msi', '/qn') -Wait

      Write-Host "Configure MySQL"


                                          Newline Page 49
Write-Host "Configure MySQL"
Start-Process -FilePath "${env:ProgramFiles}\MySQL\MySQL Server 5.1\bin\MySQLInstanceConfig.exe" -
ArgumentList ('-i -q "-lc:mysql_config_log.log" ServerType=DEVELOPMENT DatabaseType=MIXED
ConnectionUsage=OLTP Port=3306 RootPassword=') -Wait

Start-Process -FilePath "${env:ProgramFiles}\MySQL\MySQL Server 5.1\bin\mysql" -ArgumentList ('-uroot -e "use
MySQL; source users.txt;"') -wait
Remove-Item "users.txt" -Force -ea SilentlyContinue

Stop-Service -Name mysql -Force
Copy-Item my.ini "${env:ProgramFiles}\MySQL\MySQL Server 5.1\my.ini" -Force
Remove-Item "${env:ProgramData}\MySQL\MySQL Server 5.1\Data\ib_logfile*" -Force
Remove-Item "${env:ProgramData}\MySQL\MySQL Server 5.1\Data\*.err" -Force
Start-Service -Name mysql -verbose

Write-Host "Install NAS Client"
Start-Process -FilePath 'nasclient.exe' -ArgumentList ('/verysilent') -Wait
Remove-Item C:\Rootoff -Force -Recurse -ErrorAction SilentlyContinue

Write-Host "Install MySQLCC"
Expand-Archive 'mysqlcc.zip' -DestinationPath "${env:ProgramFiles(x86)}" -Force
Copy-Item "${env:ProgramFiles(x86)}\mysqlcc\MySQL Control Center.lnk" -Destination "$env:PUBLIC\Desktop" -
Force

Write-Host "Download & Install dbForge"
Start-BitsTransfer -Source 'https://www.devart.com/dbforge/mysql/studio/dbforgemysql.exe' -Destination
"${env:temp}\dbforgemysql.exe" -ErrorAction SilentlyContinue;
& "${env:temp}\dbforgemysql.exe" /verysilent

Stop-Transcript




13. Application Shortcuts & Icons
    Main NAS Application
   • Shortcut target:

C:\NLProgs\Nas.exe C:\RootOff\ (AUCTION)C:\RootOff\
    EID Applications
   • Race Reading:

C:\NLProgs\sheeppeneid.exe (RACEREADING)C:\ROOTOFF\
   • Pen Reading:

C:\NLProgs\sheeppeneid.exe (PENREADING)C:\ROOTOFF\
M k                                    ’    k

14. Permissions Check
   • Ensure both folders have Full Control for:
         ○ Users
         ○ Authenticated Users
Paths to check:

C:\NLProgs
C:\RootOff

#!ps
#timeout=-1
New-NetFirewallRule -DisplayName "MySQL – TCP 3306" `
  -Direction Inbound `
  -Protocol TCP `
  -LocalPort 3306 `
  -Action Allow `
  -Profile Any `
  -Description "Allow inbound MySQL connections on TCP port 3306"




                                      Newline Page 50
NAS Install workstation
04 September 2025     10:58



new ring laptop

install dotnet 5678.exe

windows updates installed.

add account to domain dc machine number. Laptop19273 will be domain\19273
site might have a default domain password check keeper.

Milford\19273



Add both host name and IP to the server




        Copy NLProgs from \\martserver\nldata\NLprogs to C:\Nlprogs

        Copy and replace and dups




                                          Newline Page 51
Copy rootoff or any root folders needed from a machine your replacing or \\192.168.32.253\NLData
\Users\Template\Rootoff




            Check connect2 and debt dir are pointing to correct location.




    Check perrmissions for Root folder and Nlprogs.

    right click properties on nlroggs
    go to the Security tab click on the advanced button
     then click change permissions
     disable inheritance button
    and then selected the users and click edit and change to full permission also do the same for
    authenticated users




Copy Nas icon from desktop of old machine or create your own.
Go to c:\nlprogs and find nas.exe and right click send to desktop.

Change properties to the below or the matching root folder.

C:\NLProgs\Nas.exe c:\rootoff\(AUCTION)c:\rootoff\




                               Newline Page 52
When you open nas for the first time and get this below. You know there are blocks on the files copied from Martserver NLProgs.




Click close. Go to nlprogs find any apa .exe and go to properties.

if you see the unblock tick box below you have to run the below in power shell.

Get-ChildItem "C:\NLProgs" -Recurse | Unblock-File




                           Newline Page 53
Go back into the same file and it will now be unblocked.




Newline will now open with out error.




                          Newline Page 54
Make sure windows updates install and drivers.


Check bidefender install and updated.


Add to Datto if on IT maintenance.




                          Newline Page 55
Show passwords in newline
08 September 2025   13:43



ALT- F3




                            Newline Page 56
Missing table in Newline
10 October 2025   14:45




USE newlinesql;
SHOW TABLES;



USE newlinesql;
SHOW CREATE TABLE poultryregnos;



CREATE TABLE `poultryregnos` (
  `PRNID` int(11) NOT NULL AUTO_INCREMENT,
  `LamsNo` varchar(6) NOT NULL DEFAULT '',
  `RegNo` varchar(20) NOT NULL DEFAULT '',
  `Deleted` char(1) NOT NULL DEFAULT 'N',
  PRIMARY KEY (`PRNID`)
) ENGINE=InnoDB AUTO_INCREMENT=3 DEFAULT CHARSET=latin1




CREATE TABLE `optoutdetails` (
  `OODID` int(11) NOT NULL AUTO_INCREMENT,
  `LamsNo` varchar(6) NOT NULL DEFAULT '',
  `OptOutType` char(1) NOT NULL DEFAULT '',
  `OptOutCode` char(1) NOT NULL DEFAULT '',
  `OptOutData` varchar(255) NOT NULL DEFAULT '',
  `Deleted` char(1) NOT NULL DEFAULT 'N',
  PRIMARY KEY (`OODID`)
) ENGINE=InnoDB AUTO_INCREMENT=5 DEFAULT CHARSET=latin1




                                   Newline Page 57
Oxbury



 Pre-Requisites
 Make sure the following NAS program versions are installed:
   • Nasbend – version 16.0.180
   • Eoscar – version 16.0.244
   • Invoices – version 16.0.509
                                                                                                        Oxbury
                                                                                                        Process
   1. Create a Customer Group
         ○ Go to Contact Management → O        3 (C                   ).
         ○ Create a new group for Oxbury customers (e.g. OXBURY).
         ○ Note the Customer Group Code you set up.
   2. Add the System Key
         ○ In Sysinfo, add a new key:

            Key: OXBURY_CUSTOMER_GROUP
            Value: [your customer group code]
        ○ This tells the system which group identifies Oxbury customers.
   3. Assign Customers to the Group
        ○ Edit each customer who has signed up with Oxbury.
        ○ Under the Mailing Info tab, add them to the Oxbury group (move it to the right-hand list
            and Save).
   4. Update the SaleTransfer XML
        ○ Edit the saletransfertables.xml file and add this section:

           <Table TableName="OxburyData" WhereClause="saledate='@@SALEDATE@@' and
           saleno='@@SALENO@@' and deleted=0">
            <PreInsertCommand>
             UPDATE OxburyData Set Deleted=1 WHERE saledate='@@SALEDATE@@' and
           saleno='@@SALENO@@' and deleted=0
            </PreInsertCommand>
           </Table>
         ○ This ensures Oxbury data syncs correctly when sales are sent back to HQ.


      Day-to-Day Use
   1. Invoices
         ○ When invoices are printed, Oxbury customer invoices are automatically logged in the
            OxburyData table—no extra steps required.
   2. Running the Report
         ○ On the main HQ server, under Add-Ins → Ox         I v c R     , run the new report.
         ○ The default view shows invoices not yet exported.
         ○ Hit Return or Continue to load them.
   3. Exporting
         ○ Select the records you want to export.
         ○ Go to File → x          C V.
         ○ The system creates:
               ▪ A CSV file with invoice details.
               ▪ A set of PDF copies of each invoice.
         ○ Both are saved to:

            [Main Data Drive]\OXBURY\
   4. Transfer to Oxbury
         ○ The user then copies those files to a secure network folder and uploads them to Oxbury via
            SFTP.




                                      Newline Page 58
Newline Page 59
