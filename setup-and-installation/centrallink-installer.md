---
title: "Centrallink Installer"
source: "Centrallink Installer.docx"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "New Zealand Centrallink Installer The installer will install a windows service so will require local admin rights to run"
long_description: "New Zealand Centrallink Installer"
---

New Zealand Centrallink Installer

The installer will install a windows service so will require local admin rights to run. The service itself will run under assigned credentials so will run with whatever permissions are assigned to the service.

If the installer is not run with admin rights the following screen is show and the user is asked if they want to restart the application as an elevated user.

Running the installer will bring up a screen like so:

The Saleyard Server name must then be typed to define which will then allow the server to be identified in Central. Once the details are filled out and the user clicks install the details are verified the installation process will begin. In the above screenshot you will notice there is an error provider beside of the Master folder this is because on my setup the directory does not exist.

Once install is clicked the following details are presented.

If the system is configured to use a proxy server by default then the Use Proxy Server checkbox can be ignored and the system default proxy settings will be used.

Once Save is clicked the install begins and the progress screen is shown like below:

If the Saleyard server already exists in Central the user must confirm whether the server is replacing an existing server and is prompted with the following message:

If the server is replacing an existing server then click yes. If it is an additional server then click No and select a unique Saleyard Server name.

By default the service is installed to run as System. If there is a proxy server in place and you wish to use the default proxy settings for an existing user then the service must be configured to launch with those user credentials.

To do this bring up the Services Console by running Services.msc.

Double click the Centrallink Service and go to the Log On Tab

Details of the correct account can then be entered into the This Account Field.

Our recommendation would be to setup a user on the domain specifically for this task. The service would only require permissions to write to the LAMS data folder which I believe is defaulted to D:\.

Morrinsville and Lorneville are currently setup for the service to run with the following credentials

Username		RFEX01\Newline		Password	relevant password for that account

The logon tab then looks as follows:

Once applied the service will need restarting. This can be done by going to General and clicking Stop and then Start.

To check the Saleyard configuration of Centrallink the installCentrallink program can be run again. The following form will then be shown showing the Saleyard name and the service state.

In this instance the username and password configured for this Central server is CanterburyPark and the service is stopped.