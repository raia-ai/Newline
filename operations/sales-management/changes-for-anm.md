---
title: "Changes For Anm"
source: "changes for ANM.doc"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "The ability to create a catalogue has been added to the suite"
long_description: "1. The ability to create a catalogue has been added to the suite. This is done by entering say 10 heads in the Prebook option (Option 6) and then striking the F9 key when the first eartag prompt appears. This is where the system draws a box on screen with the pen numbers (lot numbers) down the left hand side of the box and the animal type on the right. Essentially pressing F9 at this stage creates a skeleton lot sequence, which in turn creates ..."
---


   1. The ability to create a catalogue has been added to the suite. This is
      done by entering say 10 heads in the Prebook  option  (Option  6)  and
      then striking  the F9 key when the first eartag prompt  appears.  This
      is where the system draws a box on screen with the  pen  numbers  (lot
      numbers) down the left hand side of the box and the animal type on the
      right. Essentially pressing F9 at this stage creates  a  skeleton  lot
      sequence, which in turn creates the file for the  catalogue.  Striking
      F8 will abort the sequence.
   2. An extra prompt has been added at the beginning of the Prebook option.
      This allows a date for moved onto market to be entered, this  in  turn
      allowing accuracy of movement reporting to the CTS.
   3. Completing this skeleton lot procedure,  later  in  the  sequence  (on
      market day), is done by using the eartag entry option. Option 12. This
      is used because the passports are normally not available at  the  time
      of catalogue production. The system prompts lot number by turning  the
      first lot number green. The user may confirm that the beast is in  the
      same pen (lot) by pressing enter, or, he may type in a new  pen  (lot)
      if the animals have been split into smaller bunches for instance.  The
      user may then answer the  prompts  or  barcode  scan  the  appropriate
      passport to enter the details.
   4. In the event that there are additional lots after the initial loading,
      the prebook option may be used again but instead  of  pressing  F9  to
      store the skeleton lots, the user may confirm the lots  after  filling
      in all the details, again either by keyboard or bar code. There was  a
      possible cause for confusion at the conclusion  of  this  option.  The
      final prompt was enter (confirm) or F8. If F8  was  pressed  the  lots
      were not saved. The F8 will be removed. We feel that this is how  (a).
      Operators became confused thinking they had input  lots  that  weren’t
      there and (b). Lots failed to appear in the batching screens.
   5. The ability to sell by eartag  number  has  been  added  to  sell  pre
      entered lots. Option 8. The user must specify automatically sell  same
      lot number in the initial questions, and at the end of each pen  (lot)
      the computer will allow individual eartag  numbers  to  be  chosen  or
      rejected for sale.
   6. The ability to edit the animal mark has been added to lot edit, as has
      the weight  field,  even  if  the  invoice  and/or  cheque  have  been
      produced. It should be  noted  that  this  is  only  possible  if  the
      transaction is  sold  per  head  otherwise  data  integrity  would  be
      compromised.
   7. A VAT inclusive option has been added at any vatable item (currently V
      or E) by using the screen description V-INC.
   8. Back penning has been  added  to  the  salering  program.  It  is  not
      essential to enter the back pen  immediately  the  lot  is  sold.  The
      system will queue the lots in the back pen box and by clicking on  the
      appropriate lot in the queue the operator may input the back  pen  and
      the mark. This  removes  some  of  the  pressure  from  the  operator.
      Operators please note.
   9. Back penning has also been added to the Sell pre entered lots  option.
      Option 8. The operator must enter Y to terminal in the  sale  ring  to
      invoke this option. The system again queues  the  lots.  In  order  to
      avoid confusion it should be noted that after the purchaser  has  been
      entered the system will prompt F10 for back penning. Once  entered  it
      then shows how many heads are in the lot. This will normally be one in
      the case of store cattle but there is an option to  change  this.  Its
      intention is to allow changes in number of heads for sheep where there
      are many in one lot. In all cases the user has  to  backpen  EACH  lot
      (pen) individually, thus changing 1 head to three in the case of store
      cattle will have no effect.
  10. Four extra fields have been  added  to  Amend  Animal  Type  Settings.
      Option 5 in Installation. These are  Remarks,  Breed,  Beef/Lamb  Farm
      assured numbers and Extra description. The latter will be used for the
      extended description in the case of car sales,  machinery  sales  etc.
      The version of Typeset.exe in LAMS255 is wrong. Users should note that
      many of the questions asked by the computer  and  words  displayed  on
      display boards are user changeable.  These  changes  may  be  made  in
      Option 5 of installation. Contact Davey Hay or Ian Finlay for details.
  11. The salering program has been amended to  allow  animals  to  be  sold
      without lot numbers. Previous versions all worked  using  lot  numbers
      and thus the sequence was  not  important.  Merely  entering  the  lot
      number of one of the beasts in the ring brings up all  the  beasts  in
      the lot. At ANM this is not  an  option  and  it  is  imperative  that
      batched animals are brought into the ring in the exact  sequence  they
      were batched. There is no other method of  identifying  them.  In  the
      event that beasts are incorrectly batched the  unbatch  option  should
      NEVER be used. This is designed for lot numbers! Instead  the  batcher
      should choose F3 to bring up a new vendor. Choose the same  vendor  he
      had before and rebatch the beasts.  The  beasts  will  remain  in  the
      batching lists until they are sold. The effect of  this  is  that  the
      salering operator will now have two batches for the  same  beasts.  He
      will need to be told about this and simply chooses F12 unsold for  the
      first incorrect batch. This will remove  them  from  the  display  and
      bring up next batch, the correctly batched animals.
  12. There is an entirely new program called Viewsale. It is essentially  a
      full audit trail of the particular ring and is mainly used to allocate
      passports to the appropriate buyer.  This  is  a  VB  program  and  is
      accessed via an icon. As the Salering software is used to  sell  lots,
      it creates a log file of  Vendor,  Pen  (lot),  Str/Hfr  etc.,  Price,
      weight, remarks, eartag, animal mark, buyer,  matched  with  passport.
      The screen shows a line for each lot and as  each  is  highlighted  by
      up/down arrow the details appear in boxes at  the  top.  In  order  to
      match, the operator presses the space bar. The screen is automatically
      updated every few seconds.
  13. There are a set of new icons on Davey Hay’s PC which automatically log
      on and off Elgin and Quoybray and move sales back and forward to these
      sites. See the “overview” document for details.
  14. The salering software has been altered to list animals  in  descending
      age order, and there has also been some repositioning of data  on  the
      display boards.
