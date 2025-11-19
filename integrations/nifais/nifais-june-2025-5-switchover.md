---
title: "Nifais June 2025 5. Switchover"
source: "NIFAIS June 2025 - 5. Switchover.pdf"
tags: [NIFAIS Integration]
version: "1.0"
last_updated: "2025-11-17"
short_description: "NIFAIS June 2025 GovServices Deployment Switchover Currently, the service-switc..."
long_description: "NIFAIS June 2025 GovServices Deployment Switchover"
---

                                 NIFAIS June 2025
                           GovServices Deployment
                                       Switchover


Currently, the service-switchover is expected to happen over the last weekend of June – the
old service will be switched off on the Friday (possibly the Thursday night?), the new service
will be commissioned over the weekend and be available first thing Monday morning.

(This might be liable to change!)
Update from NIFAIS (as of 2025-06-05):

Both APHIS and NIFAIS will go offline at 2pm on Saturday 28th June 2025. NIFAIS, including stage
2 non-bovine functionality, will then be fully available for end users from Monday 30 th June 2025.



Go-Live:

When ready to use the new service, we will need to send out/update these sysinfo keys:

 Key                                        Value                       Scope
 GOVSERVICES_NIFAIS_SHEEP_MODE              “LIVE”                      Global/for all
 NIFAISLOGIN_SITEID                         Client-specific site ID     Per client
 NIFAISLOGIN_KEY                            Client-specific key         Per client


GOVSERVICES_NIFAIS_SHEEP_MODE: when this key is set the programs and GovServices
will then switch over to use the new system. Note: If GovServices is already running, it will
take approximately 5 minutes for it to pick up the new setting, or you can just restart
GovServices.

NIFAISLOGIN_SITEID: This will be the unique Site ID for the client, created in the JAS
infrastructure.

NIFAISLOGIN_KEY: This is the unique access Key for the client, created in the JAS
infrastructure.




NI users will be a bit smoother as they will be operating in reasonable hours; the EAC users
we will need to pay a bit of extra attention to, to avoid calls at crazy out-of-work hours!
