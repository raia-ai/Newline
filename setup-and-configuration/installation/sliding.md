---
title: "Sliding"
source: "Sliding.doc"
tags: [Setup and Installation]
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
