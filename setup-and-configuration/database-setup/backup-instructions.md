---
title: "Backup Instructions"
source: "Backup Instructions.pdf"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "NLBackup Instructions How to install and configure it:- Nlbackup can be downloaded from the ftp server, there is a single exe called NLbackup.exe..."
long_description: "How to install and configure it:- Nlbackup can be downloaded from the ftp server, there is a single exe called NLbackup.exe in the NLbackup root folder of the ftp, please copy this and the Winrar.exe to the desktop."
---

                              NLBackup Instructions


How to install and configure it:-
Nlbackup can be downloaded from the ftp server, there is a single exe called NLbackup.exe
in the NLbackup root folder of the ftp, please copy this and the Winrar.exe to the desktop.

Double click Nlbackup.exe this will run an installer,change the detination folder to C:\ as
shown below, then click install.




Go to the C:\NLBackup folder and you should have a layout looking something like this:
Double click the settings.reg and click yes to import several key settings. You do not need to
alter these, however you do need to configure the config file. To do this doucle click on
config.ini, initially this will appear like so:




I have done a brief explanation of each setting below, most are obvious but listed anyway.



                                           [BACKUP]

 This is a section of the config file that hosts all files and folders that need to be backed up.
Please do not just put C:\NLData, the reason for this is because this will compress the whole
folder to one file, whilst this is not a bad thing it means that IF the backed up file fails the
whole of NLData will be missed. This may happen if anyone has a locked file in a sale folder.
I will desmonstrate a slight shotcut later in this document for building a list of folders. It’s
lazy code but please make sure there is a space between the last folder and the [MAIL]
section.

                                             [MAIL]

To and cc are both who will recieve the email, you can add more people to this by simply
seperating email addresses with a ; e.g

TO=Ritchie@newline.uk.com; welshpool@auctionmarts.com

CC=Joe@newline.uk.com
                                      [SERVERDETAILS]

Company        - Simply the company name that will be displayed in the email report

Name           - The name of the server i.e Martserver, ExchangeServer etc

SMTPServer     - The Mail server that will be used to send the email report, most will be
               mail.auctionmarts.com, fasthosts clients should be smtp.fasthosts.co.uk

Contact        - Contact name for the email report

SQLDatabase - The Location of the SQLDatabase, this can usually be
            C:\MySQL\Data\NewlineSQL, however in the case of people with more than
            one server this may be a unc path pointing to the mysql data i.e
            \\mysqlserver\mysql\data, This is essential if you’re unsure check!

BackupDrive - The location of the external drive the backup will be copied to.

SQLServerIP    - The IP/hostname of the server hosting the MySQL database, this is used for
               stopping and restarting the MySQL Service. On the most part this will be
               127.0.0.1, you will only need to change this if the backup is not being run
               from the server or if there is more than one server and the backup is not
               being run on the server that hosts the MySQL database.

NetworkBackup and CDDrive - Ignore these for the time being, these will be replaced.

MasterFolder - Location of the master folder, this folder is archive 7 times a week. This is
             essential if you’re unsure check!



                              Trick for building a list of Folders

Go to the command prompt and navigate to the nldata folder (please ensure you are not
mapping to an network drive) and follow the below commands (On the basis the NLdata
folder is on the C Drive.

                                              C:\

                                          Cd \Nldata

                                       Dir > folders.txt

                                     Notepad folders.txt
You will then be presented with a file looking like so, using copy and paste and general
bodging you should be able to get a list of folders.




Copy all the lines from the editted folders.txt into the config.ini under backup and configure
all other details your end file should look something like this (I am confguring the backup for
welshpool) :
Save this, next you need to decide how the backup is to be run, there is now two options
here from the list of files above you will see there are two backup programs namely
backup.exe and backupsilent.exe. The latter does not display a message box to tell you
about the backup, the first one does similar to this:
My suggestion would be to create a shorcut on the desktop to backup.exe and get the user
ot run this everynight and then also schedule a backup at say 2am in the morning, this will
ensure a backup is taken, even if it is just a local copy (Handy if files become corrupt
although a waste of time in the event of server failure.)



Step by Step for what it does:-
           •   Creates a log file and fresh email file for the new backup, if an old copy exists
               for that day it takes a copy of these and renames the .old, each stage of the
               backup writes to the logfile.
           •   Stops the MySQL Service
           •   Takes a local copy of the MySQLDatabase folder defined in the above ini file
               to C:\NLBackup\MySQL\Todays.
           •   Restarts the MySQL Service
           •   Compares the size of the MySQLDatabase folder and the
               C:\NLBackup\MySQL\Todays folder, if these are different an error is flagged
               and the backup will report it has failed.
           •   Compresses the C:\NLBackup\MySQL\Todays folder to
               C:\NLBackup\MySQL\Day-MySQL.Rar Where Day is the weekday name of
               that day i.e on Monday it would backup to C:\NLBackup\MySQL\Mon-
               MySQL.Rar
           •   Takes a local copy of the Master folder defined in the above ini file to
               C:\NLBackup\Master\Todays.
             •   Compares the size of the Master folder and the C:\NLBackup\Master\Todays
                 folder, if these are different an error is flagged and the backup will report it
                 has failed.
             •   Compresses the C:\NLBackup\Master\Todays folder to
                 C:\NLBackup\Master\Day-Master.Rar Where Day is the weekday name of
                 that day i.e on Monday it would backup to C:\NLBackup\MySQL\Mon-
                 Master.Rar
             •   Runs a SystemState backup which contains Active Directory info, group-
                 policies, system registry etc. if this fails an error is flagged and the backup will
                 report it has failed.
             •   Loops through each file/folder defined in the backup section of the above
                 config file and compresses each folder to c:\NLBackup\Backup if any of these
                 fails an error is flagged and the backup will report it has failed.
             •   The whole of the C:\NLBackup folder is then copied over to the backup drive
                 as defined in the config file, if this fails an error is flagged and the backup will
                 report it has failed.
             •   The email generated at the start is amended with all details of the backup
                 and is sent to the email addresses as defined in the config file.
             •   If Backup.exe is run then a messagebox will display stating whether the
                 backup has failed and how long it took.



Troubleshooting:-
The easiest place to start if the backup should report it has failed is the log files held in
C:\NLBackup\Logs. If this is the first time you have run the backup there should only be two
files in this folder, one is a direct copy of the email sent out and the other is the log file they
will be named like so:

Email File       -       2008-02-07-Message.txt

Log File         -       2008-02-07 Backup.txt

Your best to open a log file and have a look at it, below is an example of 9 lines from a
backup done in Ballina which failed , in this example the backup HDD was not attached.

2008-02-05 01:01:27 : Archiving of Nldata\WED started

2008-02-05 01:01:29 : Archiving of WED finished

2008-02-05 01:01:29 : WED compressed down to 0MB from Original folder size 9MB in 2 seconds

2008-02-05 01:01:29 : Archiving of WED has been Successful

2008-02-05 01:01:29 : Archiving of Nldata\WED1 started
2008-02-05 01:01:30 : Archiving of WED1 finished

2008-02-05 01:01:30 : WED1 compressed down to 0MB from Original folder size 6MB in 1 seconds

2008-02-05 01:01:30 : Archiving of WED1 has been Successful

2008-02-05 01:01:37 : ***WARNING*** : Transfer of RAR files to Backup HDD has failed.

As you can see the errors are flagged with ***WARNING*** so it should be clear to anyone
what happened and what may be the best way to go about fixing the issue.
