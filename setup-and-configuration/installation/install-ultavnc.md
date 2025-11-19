---
title: "Install Ultavnc"
source: "Install UltaVNC.pdf"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Installing UltraVNC as a service"
long_description: "Installing UltraVNC as a service. Installation UltraVNC is compatible with all versions of windows from windows 95-XP, there is a new version that does support vista available from www.uvnc.com, this article describes the setup for version 1.02 but alot of the settings here can be applied in the new vista version."
---

                     Installing UltraVNC as a service.
Installation
UltraVNC is compatible with all versions of windows from windows 95-XP, there is a new version
that does support vista available from www.uvnc.com, this article describes the setup for version
1.02 but alot of the settings here can be applied in the new vista version.

You can download ultravnc from ftp://81.174.141.178/ultravnc/setup.exe

Run the setup

                                              Click OK




                                             Then Next




                          Click I Accept the Agreement and then click Next
Click Next Again




And Next Again
Untick UltraVNC Mirror Driver, UltraVNC Viewer, DSM Encryption Plugin and UltraVNC Repeater




                                  Tick the following options

Register UltravncServer as a system Service, Start or Restart UltraVNC Server, Configure Admin
                          Properties and Clean old VNC registry Keys




                                         Next Again




You will then be prompted with this error, click ok and this will display the admin properties window,
                                              see below.
1) Tick Ports and leave these on the defaults, Main should be 5900 and Java should be 5800 as
   shown above.
2) Set the Password to letmein
    3) Tick Enable Blank Monitor on Viewer Request ( This allows us to blank out the screen so they
       cannot see what we are doing.)
    4) Forbid the user to close down WinVNC
                                            Then Click Finish




Windows Firewall Configuration
If you can get away with it don’t just turn the firewall off, this is a very bad idea for obvious reasons,
here is two simple ways to configure the firewall for VNC (The same can be applied for RDP just
change the port number to 3389).

The Command Line Way
Run the following from a command line (You will need admin rights.)

                        Netsh firewall add portopening TCP 5900 VNC-Server

                     Netsh firewall add portopening TCP 5800 VNC-Server-Java

You should simply get an Ok. Response for each line as shown below:
The Windows Gui Way
Either goto Start > Run type firewall.cpl and click ok to bring the firewall configuration panel up or
alternatively, Click Start Settings Control Panel, Windows Firewall.




                                       Go to the Exceptions Tab
                                            Click Add Port




  In the field Name Type a name of your choice in this case type VNC Server, in port put the port
number for the application you are installing in this case put in 5900 and click ok. Thats it you should
                                      now be able to VNC in.
