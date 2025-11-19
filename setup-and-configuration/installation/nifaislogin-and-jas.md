---
title: "Nifaislogin And Jas"
source: "NIFAISLOGIN and JAS.docx"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "To log into NIFAIS: We start up NIFAISLOGIN When they SignOn, NIFAISLOGIN accesses the JAS API to get a JAS access token (providing the site id) ..."
long_description: "When they SignOn, NIFAISLOGIN accesses the JAS API to get a JAS access token (providing the site id)"
---

To log into NIFAIS:

We start up NIFAISLOGIN

When they SignOn, NIFAISLOGIN accesses the JAS API to get a JAS access token (providing the site id)

JAS returns a token for NIFAISLOGIN to use to access the JAS API

NIFAISLOGIN then accesses the JAS API and says that we are about to try and login to NIFAIS

JAS returns a session id and key and the login URL to use

NIFAISLOGIN launches a browser and goes to the login URL provided, then starts polling the JAS API endpoint waiting for the NIFAIS token

When NIFAISLOGIN receives the NIFAIS access token it then posts this to GovServices, and NIFAISLOGIN closes.