---
title: "Nas Conversion"
source: "NAS Conversion.doc"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Convert LAMS to NAS • Make sure all sales closed • Run Create Sales For Transfer • Share called NLDATA (standardize on D drive) • ..."
long_description: "• Make sure all sales closed • Run Create Sales For Transfer • Share called NLDATA (standardize on D drive) • (NetBEUI overcomes standalone laptops without hubs) • NLPROGS are the programs for NAS. Goes on C drive on all workstations. • Change Prodrive in all sale folders to C:\\NLPROGS\\"
---


Convert LAMS to NAS

    • Make sure all sales closed
    • Run Create Sales For Transfer
    • Share called NLDATA (standardize on D drive)
    • (NetBEUI overcomes standalone laptops without hubs)
    • NLPROGS are the programs for NAS. Goes on C drive on all workstations.
    • Change Prodrive in all sale folders to C:\NLPROGS\


NEW SETUPS
Create mySQL tables with centraldbsql
Missing files in MARKET (Main) folder :
Outstand.bnt
Mknames.nom
Yearnom.ind

EACH SALE FOLDER NEW FILES:
Salefolder: has word LIVE in it. This makes folders available in the office
setup form.
Cdb.ini: had 1 in it.
Count: 3 lines with 1 in each line

C:\ working folders on workstations
C:\ROOTOFF  -    working c drive for workstations
C:\ROOTOUT –     working c drive for away/remote/farm sales
Debtdir, prodrive and connect2 needed in these folders.

Change debtdir if needed. Extra lines required.
Set up desktop icon
Target has - C:\NLPROGS\nas.exe C:\ROOTOFF\(AUCTION)C:\ROOTOFF\
Line 4 of debtdir is important for program update purposes, and central db.

Table SYSINFO
Needs a field in it CentralDB with Y in it. Needs UK in the country code
Table SYSCONDAT needs UK in the country code. Sysinfo will superceed
syscondat at some point.


NAS notes
Program update should take you back to mainmenu when done successfully.

To add sales to the list select folder names against the sale.
Setup sale need to check wk/sale no is 3 char long.
Duplicate holding numbers list would be useful to show which is main
account.
Standardise our date formats in different options
List unsold passes still blue
Reports – create sheep movement licence should be create sheep samu file
Extrades still blue
Salering – should always show lot number you are selling (entering the
price and purchaser) and not just the first item selected in configuration.
(Cirencester have asked for this).

1ST TIME. Remake Customer Index in all sales.
