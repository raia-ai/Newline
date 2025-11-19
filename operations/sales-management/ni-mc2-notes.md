---
title: "Ni Mc2 Notes"
source: "ni mc2 notes.doc"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "N.I MC2 PURMIT SUPPLEMENTARY NOTES: You need the following bits for the new system; Notification.rpo Mc2.tpl Both are in; \\Ftpserver\ftpnewline..."
long_description: "N.I MC2 PURMIT SUPPLEMENTARY NOTES:"
---


N.I MC2 PURMIT SUPPLEMENTARY NOTES:

You need the following bits for the new system;

Notification.rpo
Mc2.tpl

Both are in;
\\Ftpserver\ftpnewline\1aphis

Edit the 9th line in debtdir, remove spareline and insert 1  (think  nas.exe
should do this with a tweak)

Setup mc2 printer and add overlay of  notification.rpo
Set printer to font size 11 in invoice and cheque.

NOTE:
    • When you cancel an invoice or a Passout it  cancels  the  MC2  purmit,
      however it will still show in the ‘create aphis movement  file’.  When
      you re-invoice or do another passout the new  details  will  overwrite
      the ones in ‘create aphis movement file’.

    • Also, the buyers invoice prompts the  MC2  movement  license.  On  the
      sellers passout it does not prompt this but it will print it out.

    • For the mart details to print on the MC2 you need to  setup  the  name
      and address in view/amend office details per sale.

