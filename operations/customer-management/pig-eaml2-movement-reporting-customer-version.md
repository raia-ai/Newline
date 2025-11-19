---
title: "Pig Eaml2 Movement Reporting Customer Version"
source: "Pig eAML2 movement reporting customer version.docx"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "New Pig eAML2 movement reporting"
long_description: "New Pig eAML2 movement reporting."
---

New Pig eAML2 movement reporting.

Lot Input Operation.

The item types being used for Pigs need to be set up with a type group of P for Pigs

If the program does not allow you to enter P for Pigs then you need to go in to option 2 in the set up menu. Then go to options and select the highlighted option.

This will display the following information and you need to enter Pigs against the P type.

Once these are set when you go in to Prebook or Full Lot and Price Input you will get the following details appear once you have selected a Pig item type.

You will need to enter the Slap Mark from the movement licence in to market in to the slap mark field and if you enter the FCI info in to remarks then this will be printed on the eAML with the FCI declaration if required.

If you are processing a private sale of Pigs and these did not come to the market so you do not want to produce an eAML licence then if you amend the M/P/L/N field to N for No movement reporting you will not need to produce an eAML licence or update BPEX with the movement.

Invoice Program Operation.

When producing an invoice for Pigs you will now get the movement screen appear with the following information.

Because the BPEX web service needs two pieces to information to identify the holding the pigs are moving to we have had to introduce a Post Code field to the Address details. You MUST make sure there is a valid post code in this field and the program will not allow you to continue until something is entered in here.

If the customers has own transport ticked on their account details then the program will now automatically populate the address details for you. If this is not selected on their account you can enter OT in to the Haulier Name field and the program will again auto populate their address details.

If you are printing a licence for Prime Pigs then the Print FCI Declaration is automatically set to Y and if printing a licence for Store Pigs this is set to N. The user can amend this by selecting this option or clicking in the box and changing the default to what is required.

If all information has been entered on the movement form correctly pressing RETURN to continue will then connect to the BPEX web service and send the movement details to their database and their database will return a reference number which is printed on the eAML licence top right in the Movement Ref: box. If there is a problem with the connection to the web service or the information you are sending does not validate then we will get back an error message and we will not receive this number. We will still printout the eAML movement licence but the operator MUST get in touch with the BPEX helpdesk and sort out the problem and they will give you a Movement Ref to manually write on the eAML licence.

This will be the same procedure if you have broadband issues or their web service is down.

Cheque Program Operation.

If you have some unsold pigs that need to move off of the market you will need to produce an Un-Sold Passout for these pigs and when the passout has been printed the computer will then printout an eAML licence.

If you select the passout option in the cheque program you will now get the movement screen appear if there are Pigs on the passout.

This will have all of the same options as the movement form in the invoice program has apart from the Print FCI declaration as this is not required.

When all Invoices have been printed and all Unsold passouts have been printed then all Pigs movements OFF of the market will have been sent to BPEX. All that has to then be done is the ON market movement recording.

On Market Movement Recording.

To report the On Market movement details to BPEX you need to select option 22 Sale Reports from the main sale menu. You then select option 11 Movement Reporting and you will get the following menu appear. It is from this new menu that you will send all movement details to the required party but to send Pigs you select option 3.