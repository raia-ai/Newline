---
title: "Newline Asp Mobile Bidding 2016"
source: "Newline ASP mobile bidding 2016.docx"
tags: [Tablet Applications]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Newline ASP – Xcira Mobile bidding platform – pre Xcira production Introduction The mobile bidding platform is a variant of the Xcira Onlinering..."
long_description: "Mobile bidding platform – pre Xcira production"
---

Newline ASP – Xcira

Mobile bidding platform – pre Xcira production

Introduction

The mobile bidding platform is a variant of the Xcira Onlineringman online bidding system. The Irish marts have requested a mobile bidding platform to allow their customers to bid in the salering (over Wi-Fi) without being pressurised by professional buyers around the salering. As this is purely a bidding platform, there is currently no camera, no audio and no requirement for a bid value (note – Onlineringman is designed around a bid value). Xcira is looking to remove the bid value from the auctionear mobile APP but this will not be ready until spring.

Definitions

Onlineringman = bidders users interface (shouldn’t be required – but maybe useful for testing)

Auctionear = Android & iOS Xcira APP for mobile bidding

Clerk = mobile bidder clerking screen

Marque = display for mart customers, showing floor or mobile bidding

Online ring manager = admin page for credit limits & allocating buyers to sales

Access to the bidding, registrations & help pages are on the mid Tipp mart website; http://www.midtippmart.com/

Access to ring manager is here

http://apps.ams1.auctionsolutions.com/ringmanager/authentication/logout.php

username & password is mtadmin

each week after the Xcira sale is setup the bidders must be transferred to the sale, exactly the same as the online bidding.

Requirements (IMPORTANT)

As the mobile bidding system is in a pilot stage at Thurles (mid Tipp mart) Xcira have not put the clerk & marque into production. As its bespoke this means that they have to create the fills prior to each sale day but cannot do it until the sale is setup in NAS. This means that whilst it’s in pilot stage pre Xcira production mid Tipp (with newline’s monitoring) will need to have the Monday sale setup on the prior Friday, then Xcira will set and send us the files. We have shortcuts to the file names on the desktop of the salering laptop (clerk) & media player (marque), but the files need to go into C:\Program Files (x86)\Auction Client\7046 on both devices.

Bidders registration in NAS – the bidders ID for the mobile bidding is this format newuka & a 4 digit number, e.g. newuka1007. We have agreed the last 4 digits will be entered in the buyers number field in NAS. If these buyers win the bid the salering clerk will enter the buyer number, this will then allow the invoice to be produced in the office.

Hardware

The existing salering laptop has had a touch screen added to it and is set for extended desktop. This touch screen will be where the Xcira clerk screen is loaded, one person will drive salering and the Xcira clerk. Once the Xcira clerk has been double clicked and is open the operator clicks on activate bidding. The existing media player has been setup with a TFT screen next to it and set as extended desktop. The user (or newline) will need to double click on the marque icon for it to launch on the extended desktop attached to the media player.

Salering

We have made changes to salering & the XML for Xcira to allocate a sequence ID so that when a lot is brought into salering the sequence ID will change & pass the new sequence to the Xcira clerk.

Clerk

This means the operator only has to press next lot on the clerk screen. Once they have clicked on next lot the next lot in sequence will be displayed, they click the no.1 button and the mobile bidders will be able to bid (all touch, no requirement for mouse or on-board keyboard).

When a bid comes in from a mobile it is set to ‘auto accept’ so that the clerk doesn’t have to do anything. If the floor bids next the clerk simply clicks the next value button (in the below example no.3), this enables the mobile bidders to be able to bid again & shows the floor as the active bidder.

When the lot is sold the clerk presses sell & this sells the lot to the current high bidder. If there is a mistake they can press undo. The clerk can see the bid history to easily identify the winning bidders number to enter in salering.

Mobile bidding Login

Go to mid Tipp mart website on the mobile, click on the 1st red button ‘bid & view online auction’

Click on the name of the sale, below example ‘Newline ICBF live test’

Double click on the username/password screen to enlarge it

Type in username and password (case sensitive), auctionear will load from here.

Mobile bidding

There are five stages to the mobile bidding:

Press once to activate – you cannot bid until activating the button, this is to stop accidental bidding.

Ready to bid – to bid press the bid button.

You are now High Bidder – the bid button is deactivated

You’ve been outbid

Sold to You