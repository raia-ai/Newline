---
title: "Invoice Program Alterations 22 08 2018"
source: "Invoice Program Alterations 22_08_2018.pdf"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Partners: D.R"
long_description: "Partners: D.R. Jones, BA J.K.M Jones S.D.W Jones, BA (Hons) ..."
---

                                                                                                                        Partners:
                                                                                                                        D.R. Jones, BA
                                                                                                                        J.K.M Jones
                                                                                                                        S.D.W Jones, BA (Hons)
                                                                                                                        P.C.W Jones, BSc (Hons)
                                                                                                                        L.J Jones, BSc (Hons)
                                                                                                                        R.M Jones BA (Hons)


                        Invoice Program Alterations 22nd August 2018


       Contents
         New Email Address Column ................................................................................................................. 1
         New Date Printed Option..................................................................................................................... 2
         New Option to Enter Buyer Address Details if Not Entered at Time of Invoicing. .................................. 3




       New Email Address Column


       On the main invoice list of customers screen if the user presses RETURN to the customer search option,
       so they bring back all buyers in a sale, there is an extra column on the grid which shows the buyers email
       address if there is one entered.




                                                Private and Confidential                                                                       1
T. 0044 (0) 1803 202140                                www.newlineasp.com www.auctionmarts.com                                    1 Montpellier Terrace
F. 0044 (0) 1803 202148                                Newline ASP is a Partnership                                               Torquay, Devon
E. info@newlineasp.com                                 VAT Reg No: 699 1408 89                                                    TQ1 1BJ, UK
                                                                                               Partners:
                                                                                               D.R. Jones, BA
                                                                                               J.K.M Jones
                                                                                               S.D.W Jones, BA (Hons)
                                                                                               P.C.W Jones, BSc (Hons)
                                                                                               L.J Jones, BSc (Hons)
                                                                                               R.M Jones BA (Hons)
       There is also a new button at the bottom of the screen for Auto Email Dummy Invoices. This option will
       email a dummy invoice to all buyers in the list that have an email address entered and has not already
       had an invoice for that sale.

       This will use the "EmailDummyInvoice" stationery if there is one set up otherwise it will use the "Invoice"
       stationery if not present. It also uses the invinv.tpl as it needs to be printed with all the information that
       the actual invoice will have on it apart from an invoice number.

       The user can enter an email subject message at the start of the run that will then be used on all emails
       sent in this run.




       New Date Printed Option.


       There is a new field in the saleinvoices table so we can record the date that an invoice was printed. The
       nldbdef will need to be sent out to create this new field in the table for this new option to work.

       There is then an option in the list of invoices if this new field is present in the sale invoice table under the
       filter options to view just the invoices printed on a particular day.




                                       Private and Confidential                                                  2
T. 0044 (0) 1803 202140                      www.newlineasp.com www.auctionmarts.com                   1 Montpellier Terrace
F. 0044 (0) 1803 202148                      Newline ASP is a Partnership                              Torquay, Devon
E. info@newlineasp.com                       VAT Reg No: 699 1408 89                                   TQ1 1BJ, UK
                                                                                                Partners:
                                                                                                D.R. Jones, BA
                                                                                                J.K.M Jones
                                                                                                S.D.W Jones, BA (Hons)
                                                                                                P.C.W Jones, BSc (Hons)
                                                                                                L.J Jones, BSc (Hons)
                                                                                                R.M Jones BA (Hons)




       If this new filter option is selected, then the user will get a screen like the below.




       This will list all the dates that have had invoices produced with the number for each day and the total
       value. The user can then select the day they would like to view and this will list just the invoices printed
       on that day with all the charges and payment details.

       New Option to Enter Buyer Address Details if Not Entered at Time of Invoicing.


       There is a new sysinfo key FILL_TEMP_CUST_DETAILS which if set to Y will prompt the user at the time of
       printing the invoice to fill in the buyer’s details. When the user presses I for Invoice they will get this
       screen.



                                       Private and Confidential                                                 3
T. 0044 (0) 1803 202140                      www.newlineasp.com www.auctionmarts.com                  1 Montpellier Terrace
F. 0044 (0) 1803 202148                      Newline ASP is a Partnership                             Torquay, Devon
E. info@newlineasp.com                       VAT Reg No: 699 1408 89                                  TQ1 1BJ, UK
                                                                                               Partners:
                                                                                               D.R. Jones, BA
                                                                                               J.K.M Jones
                                                                                               S.D.W Jones, BA (Hons)
                                                                                               P.C.W Jones, BSc (Hons)
                                                                                               L.J Jones, BSc (Hons)
                                                                                               R.M Jones BA (Hons)




       The user can then fill in the rest of their details if required at the time of printing the invoice. If the post
       code finder is set up on that computer, then they can enter the post code and click on find address and
       the system will populate the details and the user will just need to enter the house number.

       This new screen will only pop up if there are no address details entered for that customer.




                                       Private and Confidential                                                  4
T. 0044 (0) 1803 202140                      www.newlineasp.com www.auctionmarts.com                   1 Montpellier Terrace
F. 0044 (0) 1803 202148                      Newline ASP is a Partnership                              Torquay, Devon
E. info@newlineasp.com                       VAT Reg No: 699 1408 89                                   TQ1 1BJ, UK
