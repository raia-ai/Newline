---
title: "Weighbridge Full Lot Input"
source: "Weighbridge Full Lot Input.pdf"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Newline Software – Alinput – Fullinput Weighbridge - OUTLINE New options – Weighbridge settings 1) Weighbridge Configuration – setup com ports etc..."
long_description: "Newline Software – Alinput – Fullinput Weighbridge - OUTLINE New options – Weighbridge settings"
---

     Newline Software – Alinput – Fullinput Weighbridge - OUTLINE
New options – Weighbridge settings

1) Weighbridge Configuration – setup com ports etc
2) Connected to weighbridge – If set then shows weighbridge grid for weighbridge data.
3) Vendor sent from weighbridge – Don’t need to enter vendor on first screen, get from
   weighbridge.




Weighbridge creates a file with lot information – c:\rootoff\wtinfo.wk (size 40). If you clear this
file (start new sale) then it deletes it.
New option – F1 Change = This will allow you to change the vendor when entering the lot. Once
lot entered and on price field you cannot amend the vendor.

Weighbridge Info Grids – Show the information from c:\rootoff\wkinfo.wk sent from the
weighbridge. Lots ready to process (enter/sell) and lots processed (sold).

          •   To get a lot from the grid then either double click on the row or press F10. It will
              populate text boxes showing the info imported in red (grid). It then set focus to
              the item type. Depending on the item type settings it will go to the relevant
              boxes. The item type is the main page trigger.

          •   To delete a lot press the delete key on the grid.

          •   When they are processed (sold) they will appear in the second grid and remove
              from the process grid (can sort processed grid by lot No - Asc,Dsc).

          •   When a lot is sold it will automatically pull in the next weight to process (auto
              F10) It will not leave the process grid until it has been sold (matching LotNo).

          •   If the wrong vendor or no vendor is sent through then it will warn you and
              prompt for the correct vendor or just a valid account number such as X1.
Printing

The program is not set to use the printer by default, you will need to select this. When the
vendor changes it will print to the star printer.

Details printed: Market Name, Vendor details, lot number, head, breed, weight, price, total
price, purchaser details, overall value, overall heads and sale date.

When adding a printer make sure its generic text only and the share name is star. You also have
the option to not print the purchaser.




Display Board
The Weigh Unit (24/7)

At the weight unit they use a keyboard.

F1 – to start, enter the vendor (F123), enter Lot No, enter Heads, Press F3 = sends weight to
Newline software.

F2 = Quit if you make a mistake halfway through.
