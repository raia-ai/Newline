---
title: "Setup Zebra Zt230"
source: "Setup Zebra ZT230.docx"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Model Currently Sold as at July 2013: Zebra ZT 230 This is the correct driver"
long_description: "Model Currently Sold as at July 2013: Zebra ZT 230"
---

Model Currently Sold as at July 2013: Zebra ZT 230

This is the correct driver. We should download the latest driver from Zebra when installing these printers.

http://www.zebra.com/gb/en/support-downloads/industrial/zt230.html

There are some useful How To Videos on the website.

Please make clients aware of these videos and get them to watch the Manual Calibration and Ribbon Media Load videos.

Download the latest Driver from Zebra:

Install the driver:

this folder name will change with future driver versions.

Give Port a user friendly name like Zebra and put the IP address of the printer. Give the printer a IP reservation on the server.

Not needed

Calibration:

Manual Method using printer controls.

Windows driver method.

VERY IMPORTANT!!

Note : 3 Ways to Change Printer Settings:

Printer Interface

Windows Driver Print Preferences

Web Interface

The windows driver interface does not sync with the printer interface or web interface. We must be very careful not to overwrite settings by using the windows driver interface!!

2 Parts to Configuration:

Configure the printer settings -  Do this in Web Interface

Configure the label width & height – Do this in windows driver interface (as not possible in web interface)

I have disabled the configuration via the windows printer settings by ticking the use printer settings. The driver is then not used for these settings.

Web Interface:

Key Settings!!

Media Type Must Be GAP/NOTCH

Print Method Must Be Thermal Transfer

This page provides the printer settings.

Label Size:

Done through windows driver in the options tab from printer preferences. Cannot see a way to do this in the web interface at present.

Put size in mm (optional) set width and height to match type of labels you have. Set

Web Interface Modify Settings:

If prompted for a password it is 1234

Note when changing settings it is only temporary until you apply it to save current setting.

Light sensor:

This is the red light in the printer. It wants to be in middle of label to sense it correctly. By default over to the left.