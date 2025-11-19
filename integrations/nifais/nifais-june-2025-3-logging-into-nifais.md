---
title: "Nifais June 2025 3. Logging Into Nifais"
source: "NIFAIS June 2025 - 3. Logging into NIFAIS.pdf"
tags: [NIFAIS Integration]
version: "1.0"
last_updated: "2025-11-17"
short_description: "NIFAIS June 2025 Logging into NIFAIS This guide covers both Northern Irish NAS and the EAC softwar..."
long_description: "NIFAIS June 2025 Logging into NIFAIS"
---

                               NIFAIS June 2025
                                  Logging into NIFAIS

              This guide covers both Northern Irish NAS and the EAC software


To access NIFAIS, the user needs to log in to the Government Gateway, which then sends a
token back which NIFAISLOGIN.EXE receives (via an API on our JAS infrastructure) and then
passes to GovServices. GovServices can then talk to the NIFAIS web-service.

Note: This token will expire after 60 minutes (!) There is a mechanism where GovServices
can ask NIFAIS to “refresh” the token for another 60 minutes, but we can only do this up to
a maximum of 24 times in a 24 hour period before the token completely expires and the
user will have to log in to the Government Gateway again.

If the user goes to do something involving the NIFAIS service and they are not logged in,
they will get prompted with:




They can then launch the login process by:

(NAS) using the Options menu – Login To NIFAIS on the inward or outward reporting
screens.

(EAC) going into Main Menu – Aphis Settings



This starts up NIFAISLOGIN.EXE which then launches a browser taking the user to the
Government Gateway login-page.

(Ignore the access time that will show in NIFAISLOGIN.EXE –
They will need to click on GG Sign in / register, and then enter their Government Gateway
credentials:
If they sign in successfully, they will then be redirected to this web page:




They can now close the browser window and return to the program.


Note: All these credentials are handled/managed by NIFAIS via Government Gateway; if the
user doesn’t have credentials or they are invalid for some reason and the user cannot logon to
the Government Gateway, there is nothing Newline can do about this and the user will need to
contact NIFAIS.
