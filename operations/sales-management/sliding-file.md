---
title: "Sliding File"
source: "Sliding File.doc"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "I have altered the sliding file so that we can set this up for different charge types, vendor or purchaser and to work on a percentage or headage b..."
long_description: "I have altered the sliding file so that we can set this up for different charge types, vendor or purchaser and to work on a percentage or headage basis. The format of the file is now like this."
---


I have altered the sliding file so that we can set this up for different
charge types, vendor or purchaser and to work on a percentage or headage
basis. The format of the file is now like this.

SPLITNO<V@VC@H>:H1H2H3H4H5H6:2*1M0/1.6*4M0/1.3*999M0U0
SPLITNO<V@VC@P>:F1F2F3F4F5F6F7F8F9:4*400M14/5*500M20/3*9999M15U0


The new part is the bit between the <> and this needs to be as follows

The V before the first @ is for vendor so if we want to charge this by
Purchaser we need to enter P here.
The VC is for Vendor Commission. If we are going to have a sliding value on
the extra deductions then we would enter 03 for extra deduction number 3.
The H or P is to say if the sliding value is per head or percent.

The rest of the file is the same as it was before. If these new fields are
not included in the sliding file the system defaults the settings to
V
VC
And P so it should work with the old file format.

I have not added the bit about the extra deduction or the purchaser side
yet but we now have the option in the file to set this up.

New cheque program is in nlprogs and is version 3.1.298

