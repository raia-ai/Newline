---
title: "Nifais June 2025 2. Govservices Deployment Ni And Eac"
source: "NIFAIS June 2025 - 2. GovServices Deployment - NI and EAC.pdf"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "NIFAIS June 2025 GovServices Deployment NIFAIS Update – NI and EAC markets With the new updat..."
long_description: "NIFAIS June 2025 GovServices Deployment NIFAIS Update – NI and EAC markets"
---

                               NIFAIS June 2025
                          GovServices Deployment
                         NIFAIS Update – NI and EAC markets



With the new update we are now going to report sheep movements to NIFAIS through
GovServices, so we will need to deploy this to all NI markets and EAC centres. GovServices
for NIFAIS does not need NasDataHost, so we won’t need to deploy this as well. The NI
markets might well already have NasDataHost, the EACs won’t.



Deploy the appropriate GovServices from these folders:

\\nldc02\E\NEWLINE SHARES\EXES\Services\NasGovServices\NIFAIS June 2025




For sites that already have GovServices, you can just stop the service and update the
program files from the ZIP. For sites that don’t have GovServices, follow the instructions in
the installation notes in here:

\\nldc02\E\NEWLINE SHARES\EXES\Services\NasGovServices

except don’t use the installer, just setup the program folder and unpack the ZIP into there.
