---
title: "Microsoft Loopback Adapter"
source: "Microsoft Loopback Adapter.pdf"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "INSTALLING MICROSOFT LOOPBACK ADAPTOR Go into Control Panel and then ‘add new hardware’, alternatively go to run and type hdwwiz.cpl click ok"
long_description: "INSTALLING MICROSOFT LOOPBACK ADAPTOR"
---

     INSTALLING MICROSOFT LOOPBACK ADAPTOR


Go into Control Panel and then ‘add new hardware’, alternatively go to run
and type hdwwiz.cpl click ok. Click Next to the Welcome Screen.

Wizard will then browse for devices




Click Yes, I have already connected the hardware
Goto the bottom of the list and select add a new hardware device.




Select Install the hardware that i manually select from a list (Advanced)
Go down to Network Adapters and Click Next




Select Microsoft under the Manufacturer column and then Microsoft
Loopback Adapter on the left. Then Next and Finish. Babooshka you have a
loopback Adapter.
The Loopback adapter will then send out a DHCP request which it will not be
able to resolve (Unless the laptop is a DHCP server.) This will search for 60
seconds after which it will assign an APIPA network address and you will be
able to function as if a cable were plugged in. You may want to add a fixed IP
address different to any other IP address on the network as this will get
around this 60 second interval.

Do this in the normal way in network connections by either Start > Settings >
Network Connections or Start > Control Panel > Network Connections or
again Start > Run ncpa.cpl Click OK. Right Click on the Microsoft Loopback
Adapter as shown below:




Above is Still Searching for an                   Above is set to APIPA

IP address
