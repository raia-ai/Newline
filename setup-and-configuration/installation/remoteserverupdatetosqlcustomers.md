---
title: "Remoteserverupdatetosqlcustomers"
source: "RemoteServerUpdatetoSQLCustomers.doc"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Remote Server SQL Customers Update: Copy NLDBDEF from Code on NLDC02 via Central to MASTER folder on Remote server"
long_description: "Remote Server SQL Customers Update:"
---



                     Remote Server SQL Customers Update:


Copy NLDBDEF from Code on NLDC02 via Central  to  MASTER  folder  on  Remote
server.

Latest Exe’s from 09Progs, 10 Progs, Alinput V8 from working  &  any  unique
progs.

SpellUK                from dictionary folder in Code to go into Master
SftTabs_IX86_U_60.ocx        from OCX on NLDC02
Polarspellchecker.dall            from OCX on NLDC02

Change Access types to 2 in user details in newlinesql on all  users  except
NL

Log into NAS as NL, run program update, NLDBDEF should run.

Go into Remote Server update and log in as remote user (whatever the  remote
user is in userdetails table).

You should only have one opton
[pic]

Once this option has run (may take several minutes) log out.

In MySQLCC add new record in SYSINFO on remote server;
SQLCustCopied    Y
I suggest this is done by the program going forward but for now it is to  be
done manually.

Log back into NAS, test remote server  update,  should  now  have  normal  3
options in it. Ensure the new customer edit screen loads correctly.

-----------------------
Endsleigh House, 1 Montpellier Terrace, Montpellier Road, Torquay,
Devon, TQ1 1BJ
 Tel: 0044(0) 1803 202140                                         Fax:
0044(0) 1803 202148


Partners: D.R. Jones, BA
J.K.M Jones
S.D.W Jones, BA (Hons)
P.C.W Jones, BSc (Hons)


Vat No: 699 1408 89



E-mail:     info@newlineasp.com
Web:  www.newlineasp.com
      www.auctionmarts.com





