---
title: "Xcira Sale Setup Within Nas"
source: "Xcira Sale Setup within NAS.docx"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "From this version of NASBEND onward when setting up a sale in NAS the user may choose to set up an Internet Bidding Sale by ticking the Internet Bi..."
long_description: "From this version of NASBEND onward when setting up a sale in NAS the user may choose to set up an Internet Bidding Sale by ticking the Internet Bidding Available tickbox."
---

From this version of NASBEND onward when setting up a sale in NAS the user may choose to set up an Internet Bidding Sale by ticking the Internet Bidding Available tickbox.

Newline can set this so the user must tick it if they want to do so, or alternatively always show it ticked and the user can untick it if they want to do so.

Tech Note:

INSERT INTO SysInfo (KeyName,KeyCode) VALUES ('XCIRASALES','Y');

Alternatively the Y can be replaced with ALL.

If Y set the user has to tick Internet Bidding Available themselves each time. If ALL if will auto tick the tickbox.

When F5 is pressed or clicked the Xcira sale setup program loads.

The user ticks the section and itemtypes they wish to sell on Xcira.

Note the user must select the sale start time and click the save button.