---
title: "Protocol For End Of Markets1"
source: "PROTOCOL FOR END OF MARKETS1.pdf"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "PROTOCOL FOR END OF MARKETS The End Of Markets are now designed to print to file rather than printer"
long_description: "The End Of Markets are now designed to print to file rather than printer. At the end of the run the following screen appears."
---

PROTOCOL FOR END OF MARKETS

The End Of Markets are now designed to print to file rather than printer. At
the end of the run the following screen appears.




Print Full Market Report – will print the reports as before starting at report 1
and ending at 18.
Print Sales Ledger Report – will print report 1 (Market Balance) and report
18 (Sales Ledger Update)

Past reports can be printed via the UTILITY menu were you are given the
choice of which market and report to print.
After selection the report is displayed on screen with a print option.
For the print to file option to work the file PRN2FILE.COM must be in the
path of the PC running the report. This file can be found in the OCX folder
on the QB drive.

The default printer running the report must be set to Generic Text Only with
the Port Setting set to CHECK PORT STATE BEFORE PRINTING. It
doesn’t matter what the Spool Setting is set to.

The files are saved in a sub folder two levels down from the Debtdir folder.
Eg (C:\MARKET\ENDOFMAR\2002”) for any report relating to the year
2002 and C:\MARKET\ENDOFMAR\2003 for year 2003 etc.
These folders are created automatically via the End Of Markets.

The format of the file is (year+week No. + “.TXT”) if the file already exists
it adds a letter after the Week No. (“A” , “B”, “C) etc “B” would be the third
time the file was created.
