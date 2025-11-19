---
title: "Updating Ni Customers For Nifais"
source: "Updating NI Customers for NIFAIS.txt"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "0) Maybe just check they are on MySQL v5 - think we've caught all the people that were on v4, but might be worth just double-checking this"
long_description: "0) Maybe just check they are on MySQL v5 - think we've caught all the people that were on v4, but might be worth just double-checking this."
---


0) Maybe just check they are on MySQL v5 - think we've caught all the people that were on v4, but might be worth just double-checking this.


1) Install GovServices to C:\Program Files\Newline ASP\NasGovServices

Check siteconfig.json is correct!    

***Please also make sure that the service is called "NasGovServices", as I've found a few places where this is named NasGovService, which might
cause problems for future automated deployments.

For Both: Server should be "localhost", except for Cloud users 

For EACS: 
database should be "eacsql"

For Markets:
database should be "newlinesql"


2) Check the field sizes in the sysinfo table.  I've started just setting both fields "keyname" and "keycode" to 100 CHARS
Run these two sql statements:

ALTER TABLE sysinfo MODIFY COLUMN keyname CHAR(100) DEFAULT '';
ALTER TABLE sysinfo MODIFY COLUMN keycode CHAR(100) DEFAULT '';



3) check the following sysinfo keys
NIFAISLOGIN_SITEID: this should be set to this customer's Site id from the "NIFAIS Users" spreadsheet (link in folder)

NIFAISLOGIN_APIKEY: this should be set to this customer's API Key from the "NIFAIS Users" spreadsheet (link in folder)

GOVSERVICES_NIFAIS_SHEEP_MODE: Set this to "LIVE"




4) Make sure the required .EXEs are fresh/up to date:
For Markets, this will be Z:\NLPROGS
For EAC's, this will be in C:\NEWLINE\

BOTH: Need NIFAISLOGIN.EXE v1.0.0.3 (and associated files)

Markets: Need BALANCE.EXE v16.0.404 or higher

EAC's: Need EAC.EXE v16.0.63 or higher  
******following line of info out of date currently - not using connector while settling issues
(or v16.0.57 if they have the ODBC/MS-Update issue - if this is the case, you will also need to install the new ODBC driver through ConnectWise, and then you should be ok)
******end of outofdate







