---
title: "Set Up Aim"
source: "Set Up AIM.doc"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "These are the steps to install AIM: Must have: • AIM Tables • AIM webservice Cert • MSXML dlls • Internet Explorer Settings • ..."
long_description: "These are the steps to install AIM:"
---



These are the steps to install AIM:

Must have:
    • AIM Tables
    • AIM webservice Cert
    • MSXML dlls
    • Internet Explorer Settings
    • Records in SYSINFO
    • XMLNUM file in the market folder (counter file set to 1)
    • CHECK HEAD file for correct CMMS details

AIM Tables:

AIMACTIONS (Copy and paste from AIM on FTP)
AIMERRORCODES (Copy and paste from AIM on FTP)
AIMIRREGCODES (Copy and paste from AIM on FTP)
HERDSTATUS (Copy and paste from AIM on FTP)

SYSINFO Extra Records Needed

|AIM           |Y                                                  |
|AIMPOST       |https://www.ttt.agriculture.gov.ie/AIMExternal/aims|
|              |ervices/AIMWebServices                             |
|AIMCONTENT    |application/x-www-form-urlencoded                  |
|AIMSOAP       |https://service.aim.agriculture.gov.ie#serviceProce|
|              |ssorElement                                        |

The AIMPOST record has .ttt in it this is the AIM test database. When going
live this is removed.

AIM Webservice Cert:

For testing AIM install our Newline webservice cert and ensure the CMMS
number in the head file is M199. When going live we need to install their
webservice cert and use their CMMS number in the head file.

AIM Dlls:

MSXML5.DLL
MSXML5R.DLL

NB: Crucial these are in windows\system32 (not just windows) DJ this may be
the Vista issue for you.

INTERNET EXPLORER SETTINGS:

IE > Tools > Internet Options > Security > Trusted Sites

[pic]

Add these records –

https://www.ttt.agriculture.gov.ie
https://service.aim.agriculture.gov.ie

On the Security Tab Page click the Custom Level settings

[pic]

Ensure you have Don’t prompt for client certificate enabled. (May be
unnecessary)

Click the Advanced Tab:

[pic]

Tick the Allow active content from CDs and Allow active content to run in
files.



