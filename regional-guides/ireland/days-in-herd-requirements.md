---
title: "Days In Herd Requirements"
source: "Days In Herd Requirements.pdf"
tags: [Regional Operations]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Days In Herd Requirements"
long_description: "Days In Herd Requirements. Programs Alinput version 190 from Temp Customers Balance version 138 from Temp Customers Salering version 48 from 16progs"
---

                               Days In Herd Requirements.
Programs
Alinput version 190 from Temp Customers
Balance version 138 from Temp Customers
Salering version 48 from 16progs

Mysql Data
Table NasDisplaySystemProperties
PropertyName - DaysInHerd
CountryCode – IR

Operation
When the On market movements information is sent to AIM when the system receives the reply the
system looks through the movements received from AIM going in reverse order to see when the
animal moved on to the herd number of the person selling the animal. So in the below example the
system goes back through the movements until the Move To Herd number equals D3170323. When it
finds this herd number the system then works out the number of days between this movement date
and the current sale date.




In this example this is 553. This is written away to the Aim table in the DaysInHerd field.
If the system does not find a match for the On Movement date for the herd number of the seller then
it will check to see if the first move from is the same as the herd number of the seller and if it is then
it will use the date of birth of the animal as the starting date to work out the number of days in herd
as it mean that the animal was born in that herd.




Display System
We will need to amend the display system and add the number of days to the main animal grid on
the TV display so that we can display the number of days in herd against each animal in the ring. The
display will then look like this.
