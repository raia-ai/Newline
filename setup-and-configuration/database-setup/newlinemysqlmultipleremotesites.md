---
title: "Newlinemysqlmultipleremotesites"
source: "NewlineMySQLMultipleRemoteSites.doc"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "• Load MySQL onto server – • Capture archive data – • Convert archive data – • Configure new software – • Test McCartneys data in n..."
long_description: "• Load MySQL onto server – • Capture archive data – • Convert archive data – • Configure new software – • Test McCartneys data in new format - • Training @ Ludlow - • Role out to remote sites -"
---




    • Load MySQL onto server –
    • Capture archive data –
    • Convert archive data –
    • Configure new software –
    • Test McCartneys data in new format -
    • Training @ Ludlow -
    • Role out to remote sites -

Software Requirements:-
    • MySQL       Version 3.23.47 VBdrive
    • MyODBC
    • Mdac2.7
    • MySQLX           Control to bypass ODBC
    • Various OCXs
    • Newline exes

Xcreatecsv
Tsremote
Tsserver
Users2k – create users folder. Create sub folder admin
End mar17
Endmar18
Endmar19
Regbuyer
Market.exe
Asale.exe
New datatran

/ 30 ODES

connect2 – mySQL server IP on line 1 and data source newlinesql on line 2.

INSTALL:-
    • MySQL
    • MyODBC
    • Mdac2.7
    • MySQLX – only needed on server computer for running xcreatecsv

SET UP MySQL:-
Put winmysqladmin.exe in the start up/start menu folder
C:\mysql\bin>mysql
>source cretab.sql (This sets up the appropriate tables in the mySQL
database (newlinesql data source).

XCREATECSV

Ensure that MySQLX has been installed
Ensure that connect2 exists in the debtdir folder.
Ensure that otherdes and extrades are the same in all market folders – make
a file odes with all of these in.
Ensure that head file animal types are standardised in the different market
folders
Run xcreatecsv from debtdir folder
Click Transaction Details
Type the year to convert
Click ESC when asked about customers
This should insert the transaction data for that year into the transaction
table
Also need to do cheques & invoices

NEWLINE FILES
Copy OCXs to the path
Add regbuyer to the prodrive directory
Remove oldsales.exe and archive.exe
Use correct asale.exe
Edit debtdir for 2 additional lines UK & market number e.g. Ludlow 1or
Worcester 9
Plus 2 extra lines line connect2

PRINTER TEMPLATES
Go in Debtdir folder

PROGCOP.BAT
Change to copy OCXs

REMOTE SITES
TS.INI on remote PCs to tell them to run tsremote.exe to connect to the
server
