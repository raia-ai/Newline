---
title: "Inishowen Direct Operatio1"
source: "Inishowen Direct Operatio1.doc"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "[pic] Inishowen Direct Operation: Nick has already provided a word document (attached): Client Requirement: 1"
long_description: "Nick has already provided a word document (attached):"
---


[pic]

Inishowen Direct Operation:

Nick has already provided a word document (attached):

Client Requirement:

   1. Stock is assembled at the market , lot’d up and collected by a haulier
      and off to the abattoir.
   2. They send off an invoice to the abattoir. With haulage and procurement
      on it. They do not sell the stock to the abattoir therefore it goes
      through our system with a zero price.
   3. They’d like to be able to record a fixed price for lamb, hogget and
      ewe for the collection but not against each lot.
   4. After Sale: they need the facility to look up invoice summaries for
      the factories & history for the seller.
   5. They need to be able to allocate a lorry against the stock that is
      collected.
   6. They’d like to produce a monthly summary for the abattoir to show how
      many went per collection, total & amount due.
  
Solution:

   1. They have 4 weeks setup for inputting direct to factory stock, (see NH
      doc) they now use NL98 to reset the date (only for the week 1,2,3,4)
      when required
   2. The sales are setup with a D in the amend office details program (date
      file)
   3. Stock is booked into this sale and can be sold with a zero price to
      the factory
   4. Once they are ready to produce invoice etc and move the stock to the
      factory they use the movelot program (see NH doc) and move the lots to
      one of the direct sales on the system.
   5. They invoice the factory, (when the sale closes this gives them
      history for the buyer)
   6. They are going to start producing the cheques (this will give them
      history for the sellers)
   7. For the prices they are going to input one dummy lot, lot 1000 with
      prices for the collection in remarks, eg L 4.80, H 3.80 E 1.80 (this
      is lamb per kilo, hogg per kilo, ewe per kilo)
   8. To allocate a which lots go to which lorry they will enter either 1 or
      2 in the grade field in 21 – sales total as they are loaded up. they
      can then produce a relevant printout for the lorry drivers.
   9. These sales Direct SUN, TUE, THUR are closed down as per a normal sale
  10. To get the monthly invoice summary they’ll go into copy invoice Via
      customer edit and enter the monthly date range and print the summarry

Issues:

   1. They don’t want the agent field in Alinput to appear for collections,
      it looks like we have taken this for the sheep sales but I was not
      able to change it using nas.
   2. They’d like a ‘select all’ option in movelot, other people have also
      asked for this
   3. If you try and move the lots to a sale that is closed it lets you do
      this but then you lose the lots from both sales. It would be sensible
      to have a message telling the client to set the sale up. also it would
      be better to select the sale from the list rather than having to type
      in the folder name.
   4. Currently they use the breed field for the collection centre, they
      don’t want it to auto repeat. I explained short term this is something
      we will not be looking to change. I think they’ll get used to this but
      be aware.
   5. The sections are setup as days of the week, in the Monday section the
      flock number does not populate the remarks, in the Wednesday section
      it does? What is it in the head file that determines this?

NH – They’d like to start using this for Cattle, they seem to think you
have set this up for them but i couldn’t see where??

