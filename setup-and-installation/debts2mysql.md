---
title: "Debts2Mysql"
source: "Debts2Mysql.pdf"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Installing Debts2MySQL Installing the Service Copy all files from ftp://81.174.141.178/Debts2MySQL into the NLProgs folder, also take a copy of the..."
long_description: "Installing Debts2MySQL Installing the Service Copy all files from ftp://81.174.141.178/Debts2MySQL into the NLProgs folder, also take a copy of the rootoff folder and call this Rootdebt. Open Debtdir in rootdebt and make sure all folder pointers are pointing to a local hard drive rather than a network drive, the reason for this is because you will be running the Debts2MySQL application with the System user account which will not have a drive mapped to it."
---

                           Installing Debts2MySQL
Installing the Service
Copy all files from ftp://81.174.141.178/Debts2MySQL into the NLProgs folder, also take a copy of
the rootoff folder and call this Rootdebt. Open Debtdir in rootdebt and make sure all folder pointers
are pointing to a local hard drive rather than a network drive, the reason for this is because you will
be running the Debts2MySQL application with the System user account which will not have a drive
mapped to it.

DebtDir should look like so:




Go to a dos box and change directory into the C:\NLProgs folder and run the following command
This installs the Srvany exe as a service. Srvany is an exe wraaper that allows you to run normal
windows applications as a service. You will need to edit the registry to set srvany.exe to run the
debts2mysql.exe, you can do this by running Regedit and browsing to

               HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\NasDebts

Once navigated to here right on NasDebts and got New > Key. The name of this key should be
Parameters, Click on Parameters and on the right hand pane again right click and create a new string
value, call this application. Press Enter to open the application key and paste the following
information:

               C:\NLPROGS\debts2mysql.exe C:\ROOTDEBT\(AUCTION)C:\ROOTDEBT\

You end settings should look like this:




To then start the service either right click on my Computer and go to manage, go down to services
and Applications on the left hand side, in the right pane there will be a service listed called
NasDebts, the startup type should be set to automatic, this means the debts2mysql.exe will run
before the user logs on. You can also run the following from a command line.

                                          Net start NasDebts

Debts2MySQL takes 2 minutes to start so you will have to wait for this time before checking if it has
run.
Troubleshooting the Service
Unfortunatly running debts2mysql in this manner has a few issues, these are the 2 major issues,

1)      If there is a data error, the service will still report it is running however this will not be visible
as the app is running behinf the scenes, the easiest way to see if there is an error is to stop the
service by either right click on my Computer and go to manage, go down to services and Applications
on the left hand side, in the right pane there will be a service listed called NasDebts, right click on
this and go to stop. You can also run the following from a command line.

                                                 Net stop NasDebts

        Once stopped you can run the application manually by navigating to:

             HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\NasDebts\Parameters

Copy the text from the application string value and paste this into Run, you should see a full screen
form, again this takes 2 minutes to run so make sure you wait that length of time. It should finish
with a Z on the form if there are no errors otherwise the error will be presented.

2)      Debts2mysql relies on srvany.exe and on more than one occasion i have seen this go missing
from the nlprogs folder, or more commonly change it’s extension to .wri, this means the service will
not run, when attempting to run the service you will get the following error




This error actually has nothing to do with debts2mysql and the best fix is to just recopy all files from
ftp://81.174.141.178/Debts2MySQL to the C:\NLProgs folder, restarting the service should then fix
the issue.
