---
title: "Setup Web"
source: "SETUP WEB.doc"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Method to set up Web Cam in Sale Ring 1"
long_description: "Method to set up Web Cam in Sale Ring"
---


Method to set up Web Cam in Sale Ring

1. Add DB server IP & local router IP and market no. to MySQL table on DB
Server.

2. Z:\webfiles is the data folder written to by salering. Note it is
currently hard wired.

3. Update auctionmarts.exe will ask for 1. DB Server (on line
213.171.198.168). 2. Database name=newlineweb. 3. Market no. This needs to
be set up on the local server’s desktop for easy access.

4. regsvr32 c:\windows\system32\msstdfmt.dll This dll needs to be
registered like this in the path.

5. On dedicated server set up media configurator session. This needs to be
the same name as the local configuration on the laptop.

Local router points to the particular laptop running the sale.

On local laptop set up uliveserverconfig. Note the same name as on the
media configurator.


NB We are currently using Vs 1 of the streaming software. We will need to
test the latest version that allows recording and get this out before we
take on any more cutomers.

DJ
25th May 2005



