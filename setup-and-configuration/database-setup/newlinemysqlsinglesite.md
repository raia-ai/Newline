---
title: "Newlinemysqlsinglesite"
source: "NewlineMySQLSingleSite.pdf"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Newline Server Side - MySQL Summary • Load MySQL onto server – • Capture archive data – • Convert archive data – • Configure ..."
long_description: "• Load MySQL onto server – • Capture archive data – • Convert archive data – • Configure new software –"
---

                     Newline Server Side - MySQL

Summary

   •   Load MySQL onto server –
   •   Capture archive data –
   •   Convert archive data –
   •   Configure new software –

Software Requirements:-
   •   MySQL                  Version 3.23.47 VBdrive
   •   MyODBC
   •   MyTool
   •   Mdac2.7
   •   Various OCXs
   •   Newline exes

Xcreatecsv
Regbuyer

/ 30 ODES

connect2 – mySQL server IP on line 1 and data source newlinesql on line 2.

INSTALL:-
   • MySQL (on Server only)
   • MyTool (on Server only or remote support machine)
   • MyODBC (on Server & Workstation)
   • Mdac2.7 (on Server & Workstation)

SET UP MySQL:-
Put winmysqladmin.exe in the start up/start menu folder
C:\mysql\bin>mysql
>source cretab.sql (This sets up the appropriate tables in the mySQL database
(newlinesql data source).

XCREATECSV

This program is used to convert the old flat file archive files into the mySQL database
format.
Ensure that connect2 exists in the debtdir folder.
Ensure that otherdes and extrades are the same in all market folders – make a file odes
with all of these in. Theses files have the various cheque and bill deductions that
customers charge, like washout fees, or buyers premium, etc. The odes file combines
the otherdes and extrades file.
Ensure that head file animal types are standardised in the different market folders
Run xcreatecsv from debtdir folder
Click Transaction Details
Type the year to convert
Click ESC when asked about customers
This should insert the transaction data for that year into the transaction table
                    Newline Server Side - MySQL

Also need to do cheques & invoices

NEWLINE FILES
Copy OCXs to the path
Add regbuyer to the prodrive directory
Remove oldsales.exe and archive.exe
Use correct asale.exe
Edit debtdir for 2 additional lines UK & market number e.g. Ludlow 1or Worcester 9
Plus 2 extra lines line connect2

PRINTER TEMPLATES
Go in Debtdir folder

PROGCOP.BAT
Change to copy OCXs
e.g.
COPY Z:\PROGRAMS\*.* C:\PROGRAMS
COPY Z:\OCX\*.* %WINDIR%
