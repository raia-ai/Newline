---
title: "Streaming"
source: "STREAMING.doc"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Camera Streaming 1) Internet setup 2) Local setup 3) Recording Only Internet Setup • Install camera onto laptop"
long_description: "1) Internet setup 2) Local setup 3) Recording Only"
---


 Camera Streaming

   1) Internet setup
   2) Local setup
   3) Recording Only

Internet Setup

    • Install camera onto laptop.
    • Install ‘Streaming Media Player’ onto laptop.
    • Install ‘Live Server Configurator’ Version 4 onto laptop
         o Add new media source, choose camera and microphone. Name the
           source something simple like – barbers, newark, bjp (name will
           be a reference on the media server). Do not setup recording
           here.
    • In the router open TCP port 5119 – 5120 and point to the laptop.
    • RDP into our dedicated web server.
         o Under the unreal streaming menu, open the media server. Add new
           source using the public IP of the mart and the name you used in
           the live server configurator.
         o In MYSQL control center open the ‘newlineweb’ database, then
           find tblmediaserver and add the market No, web server address
           and the public IP of the mart.
















    • On the mart server add updateauctionmarts.exe to the working folder.
      Create a shortcut to the desktop, using the following target path
      (NAS):
         o C:\ROOTOFF\UpdateAuctionmarts.exe
           Z:\MARKET\(WEBUPDATE)C:\ROOTOFF\
    • When they go into Sale Ring they must tick the ‘Live Internet Sale’
      option
    • Add a folder ‘webfiles’ to the c: on the server (and nldata folder).
    • Add sales to auctionmarts.com (username and password needed).
    • Run updateauctionmarts.exe shortcut on server and select the current
      sale, this will minimize, this must stay minimized to update the sale
      ring details to the web. Close when sale is finished
Local Setup

    o Add and setup the same programs to the laptop as in the internet
      setup.
    o When adding the details to the mysql server on the dedicated web
      server also include the local IP of the laptop and the local IP of the
      server.
    o If it’s working locally and over the internet then you will need to
      follow the steps for the internet setup as well as this.
    o Install the Media Server Configurator Version 4 to the mart server and
      setup.
    o Add a shortcut to auctionmarts.exe on the machine which is going to
      view the sale locally. In the path use the following:
         o C:\ROOTOFF\UpdateAuctionmarts.exe
           Z:\MARKET\(LOCALSALE)C:\ROOTOFF\


Recording Only

    o Add and setup programs on laptop as in internet setup
    o Create a shortcut to ‘Live Server Configurator’ on the desktop.
    o When they want to record then they open the shortcut, right click on
      the live source and select ‘Start Recording’.
    o When the sale in finished then they open the shortcut, right click on
      the live source and select ‘Stop Recording’.
    o The sale is located: C:\Program
      Files\UnrealStreaming\ULiveServer\........... (name of source).
    o Create a batch file on the laptop which then ‘Moves’ the sale across
      to the server. This is so the laptop doesn’t run out of space on the
      hdd.
