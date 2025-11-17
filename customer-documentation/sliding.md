---
title: "Sliding"
source: "Sliding.doc"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "[pic] Sliding Scales 1"
long_description: "1. The difference between Spiltyes and Spiltno:"
---


[pic]

                               Sliding Scales



   1. The difference between Spiltyes and Spiltno:

There are two ways these rates can work,  eg stock with a value of £150.

This is an example of splitYES:
1.         10% £100 5% >£100 £150 = £12.50 commission. In this example the
first hundred is charged at 10% commission, the remaining £50 is charged at
5%

This is an example of splitNO:
2.         10% £100 5% >£100 £150 = £7.50 commission. In this example the
whole value is charged at 5% as the value is >£100.

   2. Breakdown of the sliding File:

SPLITNO:A1:9*500M0.8/5*999999M0.8U0

SPLITYES:A1:9*500M0.8/5*999999M0.8U0

This is a step by step breakdown of the how the sliding scale is made up.

    • :A1 is the item types, they should be added without any commas or
      fullstops, eg    :A1A2A3:
    • 9     =     the % value
    • *     =     separate the % from the value
    • 500   =     the value, eg £500 upto £500
    • M     =     is the minimum (NOTE: if no minimum file still needs M)
    • 0.8    =    is the value of the minimum, eg 80 pence (NOTE: if value =
      0 the file still needs 0).
    • /      =    separates the minimum from the next % value
    • 5     =      the % value
    • *     =     separate the % from the value
    • 999999 =    the value, eg £999999 upto £999999
    • M      =    is the minimum
    • 0.8    =    is the value of the minimum, eg 80 pence
    • U     =     Unsold charge NOTE: if no unsold file still needs U)
    • 0     =     0 value unsold charge, eg 2 would be £2. (NOTE: if value =
      0 the file still needs 0)

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

