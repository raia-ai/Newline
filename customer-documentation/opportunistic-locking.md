---
title: "Opportunistic Locking"
source: "Opportunistic Locking.pdf"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Opportunistic Locking Only on PCs running NT, W2000 Professional/Server or XP PCs being used as Servers only HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentCon..."
long_description: "Only on PCs running NT, W2000 Professional/Server or XP"
---

Opportunistic Locking

Only on PCs running NT, W2000 Professional/Server or XP

PCs being used as Servers only
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\LanmanServer\P
arameters
Right Click
New>DWORD Value
Type in EnableOplocks
Ensure the value is (0)

PCs being used as both server and workstation
Enter as above and then as below.
N.B. This means that LanmanServer has EnableOplocks value as (0) and in addition
and on the same machine’s registry settings LanmanWorkstation has all three values
as (0) as detailed below.


PCs being used as workstations only

HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\LanmanWorkstat
ion\Parameters
Right Click
New>DWORD Value
Type in UseOpportunisticLocking
Ensure the value is (0)

HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\LanmanWorkstat
ion\Parameters
Right Click
New>DWORD Value
Type in UseLockReadUnlock
Ensure the value is (0)

HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\LanmanWorkstat
ion\Parameters
Right Click
New>DWORD Value
Type in UtilizeNtCaching
Ensure the value is (0)

DJ 15th May 2003
