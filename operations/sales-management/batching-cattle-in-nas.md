---
title: "Batching Cattle In Nas"
source: "Batching Cattle in NAS.docx"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Intro: Store cattle are often batched into similar groups for sale when the value of each animal in the batch is deemed to be the same"
long_description: "Store cattle are often batched into similar groups for sale when the value of each animal in the batch is deemed to be the same. There are a number of different methods used by marts for matching store cattle which may depend on the layout of the yard, market managers preference, tradition, etc. These are set out in this document."
---

Intro:

Store cattle are often batched into similar groups for sale when the value of each animal in the batch is deemed to be the same. There are a number of different methods used by marts for matching store cattle which may depend on the layout of the yard, market managers preference, tradition, etc. These are set out in this document.

Lotting Method:

Same lot number

Individual sequential lot numbers

Random lot numbers

Same Lot Number

For example three steers sold together and each one will have lot 56 on their back. This means the picking\sorting yard staff have identified which animals should have an identical value and have put the same lot number on their back. This creates an immediate link for all these animals from a NAS point of view. There is no need to batch in the system because the lot number does that for us. Some clients raise an issue what if the lot is split in the ring. 2 of the cattle are sold to one buyer and the 3rd to another buyer. If they all have the same lot number on their back how to you ensure the right one is sold to the right buyer. The system allows for the automatic creation of a sub lot. When an animal is put on hold and not offered for sale with the other animals in the same lot number range a sub lot is created for instance 56A. The yard staff would need to put an A lot on the back to ensure the animals are back penned correctly, but the invoice and passout will reflect the new lot number and help ensure the correct animal is taken away by the haulier.

Individual sequential lot number

The same three steers may be lotted up as lot 56, 57 & 58. Each has their own unique lot number. This makes the process for splitting the animals in the ring very easy. The 3 animals come in together but the buyers are not happy to buy them as a 3. Lot 56 & 58 may be sold to one buyer and 57 sold to another.

Random lot numbers

Some markets do not determine the batch until the very last minute. Lot numbers 56, 58, 61 & 62 could all be sold as a batch. The clerk is left to address the selection in the ring as the animals walk in. This provides a great flexibility and allows the vendors to change their minds at the last minute, but does put pressure on the clerk and take more time to display on the board.

Batching Method:

Batch as pre-booked

Batched at picking point directly before the ring

Batched by lot number

Batched real-time by clerk in the ring

Batch as pre-booked

Within the sale there is a default setting for batch as entered.

This settings only needs to be set once in the desired section and sale. What this does is ensure that however the user enters the cattle into NAS through pre-book / 1. Pre Sale Lot Entry is how they are batched when they get to the salering.

Note: It is vitally important that you decide which way you want to run the system and stick with it for any given sale. The setting should not be amended part way through a sale. This would cause you issues. It is not recommended.

The system shows the settings to confirm they are as you require.

The user selects the itemtype and enters the sequential lot number range with a forward slash splitting the first and last lot in the range. The system then calculates how many heads that should be. This speeds the entry process up dramatically. Having different lots with no order would make it a slower process.

The user scans the correct passport to the correct lot number.

They click save and the lots have been entered as a batch.

Selling Lots entered as a batch

The examples below are based on using these settings. Not all marts weigh store cattle but in this example they do and they enter the gross weight. It is possible to batch without weight or possible to use the average weight. The setup is very flexible.

On the essential sale settings screen in salering it shows the user

Do not delete the batch data unless instructed by Newline. Deleting the batch data will remove all record of the pre-booked batches.

The list on the bottom left of salering shows batches waiting to be sold.

Here we see a batch with 3 heads comprising of lots 56-57-58. The user can type any one of these lot numbers into the system to bring in all 3 animals together because they have been batched. The clerk may see lot 57 first on the weigh bridge so enter that lot number.

Clicking Next Lot brings all 3 animals into the ring and displays them on the board.

The animals are ordered oldest to youngest. If the youngest animal lot 58 was obviously smaller than the others and the buyers decided it was not worth the same value they may ask to split the lot. The user may double click the lot to put it on hold.

The clerk sells the 2 not on hold. 57 & 56.

Then 58 is available again for sale by itself.

Buyers Invoice.

Mr Fox bought lot 58.

Mr Taylor bought lots 56 & 57.

What happens if the office batching is wrong?

This brings the first batch with 3 cattle into the ring, but you want to add the 2nd batch to it as well.

You can now sell the 2 batches with 5 cattle together.

Alternatively the clerk may want to put some of these on hold and mix the batches and sell differently to the original plan.

The clerk puts items on hold by double clicking them. When the other animals are sold the items on hold come back into play for sale.

Batched in the ring real-time

The essential settings in salering will show.

Note the setting (create batch file while entering) must NOT be set in the sale installation when pre-entering lots and selling this way.

The user sees individual lot numbers down the side of the screen because a batch file has not been created and batching is not on.

Enters one of the lot numbers they see on the back of the animals and presses next lot.

This lot appears on the board.

They click the F12 key and type the other lots to join this batch.

56 enter.  58 enter.

This takes the clerk time to see the lot numbers and enter them, but does provide flexibility. It can be useful when batches change a lot right up to the point of entry into the ring.

Batch by lot number

Note this setting must NOT be on.

If clerk wants to split lot.

An alpha sub lot is automatically created.

Tech: requires SUBLOTCATTLE set up in sysinfo.

Dynamic Batching Software

It is possible to have a clerk and laptop directly before the cattle enter the ring and dynamically batch the cattle. This makes the job very easy for the clerk in the ring as all they need to do is select the next batch and the right animals come into the ring. It is very quick, flexible and accurate. However it does involve additional resource.