---
title: "Overview"
source: "OVERVIEW.doc"
tags: [Overview and Introduction]
version: "1.0"
last_updated: "2025-11-17"
short_description: "REMOTE SALES SETUP & CONTROL (ANM ONLY) SYSTEM OVERVIEW The Newline system creates markets ready for remote use at the Thainstone server end..."
long_description: "REMOTE SALES SETUP & CONTROL (ANM ONLY)"
---


REMOTE SALES SETUP & CONTROL (ANM ONLY)


SYSTEM OVERVIEW


The Newline system creates markets ready for remote use  at  the  Thainstone
server end  by running the “Create markets for transfer”  option.  This  has
the effect of adding all new customers,  debts  etc.  and  then  compressing
(zipping) the sale ready to move  it  to  the  relevant  remote  market.  It
automatically places the zipped file in the  server’s  \download\  directory
(folder). This file is then copied using the  icons  provided  in  the  Data
transfer folder or  via  normal  Windows  cut  &  paste  techniques  to  the
\download\ directory (folder) of the appropriate remote server.  The  remote
user does not need to become  involved  with  the  transfer  procedure,  but
simply runs the “Receive central market data” which moves the data from  the
\download\ directory into the  live  directory  for  the  day  in  question,
(MON/TUE etc). The data is automatically uncompressed  and  made  ready  for
the sale.

When the sale is completed the remote user runs the “Create data for  return
to central market”. This again compresses the market and places it  back  in
the \download\ directory of the local server. It is copied down the line  to
the NT server at Thainstone by the system  administrator  using  either  the
transfer icons or normal Windows copy routines,  where  the  central  system
administrator runs “Receive returning data from markets”. This  uncompresses
the data and places it back  in  the  appropriate  directory  (folder).  The
market is completed here and central files are automatically updated.

HOW TO SET UP A REMOTE SALE.

The system administrator at Thainstone  chooses  the  market  he  wishes  to
transfer and making sure it has already been  properly  shut  down,  updated
and archived, he sets up a new market at option 6 of  the  Main  Menu.  Once
this has been  done  he  comes  out  to  the  Windows  desktop.  The  system
administrator then  clicks  the  Newline  market  icon  and  chooses  Create
markets for transfer in the opening Newline menu. There will only be one  PC
set up with this option and it is currently David  Hay’s.  The  system  will
prompt, “Choose market name ready for transfer”. This is similar to the  run
a market prompt. Just type in the  market  concerned  such  as  Elginfur  or
Caithotm.  The system then prompts C to continue or E to escape.  Make  sure
you are in capitals and answer appropriately.  The  system  then  warns  you
that there must be no one working in this particular market at the time  and
asks you to type the word “GO”  and  press  enter  when  you  are  ready  to
proceed. At this stage the computer will address the  appropriate  data  and
compress it. The computer then prompts:

 Back to menu          [B]        Create transfer disk [D]
Create modem file   [M]                  Create ISDN file      [I]

Choose [I] and press enter.

N.B. In the case of setting up a market to run locally at  Thainstone,  just
choose [B] Back to menu at this stage.

Otherwise when [I] is chosen in the case of a remote sale:

The computer will zip the appropriate data into a zip  file  with  the  name
the  system  administrator  chose.  This  is  automatically  placed  in  the
\download\ folder.

The system administrator  then  exits  the  Newline  programs  back  to  the
Windows desktop.
The system administrator enters the Data transfer  folder  and  chooses  the
appropriate icon to move the zipped market from the Thainstone server on  to
the remote server.

As an alternative, and  to  explain  what  this  does,  a  very  experienced
Windows  user  could  use  network  neighbourhood  to  log  on   to   either
\\caith01\c or \\elg01\newline.
Using normal Windows cut and paste routines he can copy the appropriate  zip
file from the \download\ directory  of  the  NT  server  to  the  \download\
directory of  the appropriate remote server. The icons used by  the  systems
administrator in fact log on to the appropriate local server using “net  use
R: \\cth01\c”. The data is automatically copied and  immediately  afterwards
the icon logs off using “net use R: /delete”

The remote user, on advice from the system administrator that  the  file  is
in place, simply runs “Receive central market data”. This prompts,  “Receive
market Disk [D] Modem  [M]  ISDN  [I].  Choose  [I]  and  press  enter.  The
computer prompts market name to update  from  disk.  Enter  the  appropriate
name. This offers the normal choice. Choose C and enter.  The computer  then
inflates the zip file and places it in the appropriate folder ready for  the
sale.

HOW TO RETURN A COMPLETED REMOTE SALE.

Once the sale is complete the remote user chooses “Create  data  for  return
to central market”. He does not necessarily have to balance the  sale  first
although it may be good practice to do so. HE MUST NOT  RUN  END  OF  MARKET
ROUTINES. The computer will prompt,  “Choose  market  name  to  update  from
disk”. The remote user enters the name of the current market and the  system
deflates the data and prompts:

Back to menu          [B]         Create transfer disk [D]
Create modem file   [M]                  Create ISDN file      [I]

Choose [I} and the system places the  file  in  the  remote  PCs  \download\
directory.

The system administrator at Thainstone then  chooses  the  reverse   Windows
copy procedure icon in the Transfer  data  folder  which  places  the  newly
zipped file in the NT server’s  download  directory.  Again  an  experienced
Windows user may do this manually.

N.B. Italics notes are for the benefit of Sandy Duncan.
The system administrator then chooses “Receive returning data from  markets”
from the opening Newline menu. This has the effect of unzipping  the  remote
sale and returning it to its folder on the Thainstone NT server.

The market may then be balanced or amended and the end  of  market  routines
may then be run, when the central Market database is properly updated.

SETTING UP A NEW SALE AT A REMOTE SITE.

Both Elgin and Quoy Bray have their main PC logged on to the  NT  server  at
Thainston. This means that this PC only in their local network can  see  the
main market directory (folder) at Thainstone. This is where  the  debts  are
and thus a debt enquiry on either of these PCs will  show  the  up  to  date
position. It also means that cash may be posted from these points.

If a market is set up on either of these machines  there  will  be  a  major
time delay because some work will  be  done  on  the  ISDN/Lease  line.  The
answer is to run the set up routine on one of the other PCs on the  network.
This will work quickly.

Newline. 14th September 2000.
