---
title: "Invoice Credit Control"
source: "Invoice Credit Control.docx"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Intro: Credit control is a major concern in modern auction businesses"
long_description: "Credit control is a major concern in modern auction businesses. Buyers do not always pay on the day and are given credit terms involving credit limits and number of days of credit. The auction wants to keep the buyers within these terms but buyers will sometimes try and trade outside them. Newline have added a new feature to aid the users when trying to keep buyers within their terms."
---

Intro:

Credit control is a major concern in modern auction businesses. Buyers do not always pay on the day and are given credit terms involving credit limits and number of days of credit. The auction wants to keep the buyers within these terms but buyers will sometimes try and trade outside them. Newline have added a new feature to aid the users when trying to keep buyers within their terms.

The latest version of the invoice program has a credit checking option in it. There is a Newline admin option in the  system config shown below that is used to turn the features on and set them up.

Credit Limits

In the example above Newline have set up a credit limit on a customer and then gone to print an unpaid invoice that will take them over their limit. The user will see the following message.

If the user says Yes to continue they get asked the following.

Enter reason for override.

I am able to do this without having to enter a password as my user level is high enough. If the user access level is above 3 then you will need to enter the password to continue.

If the user access level is greater than 3 then you get prompted to enter a password to continue.

This is the password set on the configuration screen.

The comments entered at the time of overriding the credit message are written away to the contact system so these can be viewed from the customers record or from the contacts system.

Tech Note : You need FULLCONTACTSYSTEM set to Y in sysinfo for this to update.

Credit Terms

If the customer does not have a credit limit or any credit days set then the system will default back to the trading terms for that office. I have this set to 14 days for this sale and when producing an invoice for a customer with debts older than this you get the following message.

Again you can continue past this and enter the required password if you access level is not high enough.

You can also set different trading terms for a customer on their customer details.

I have just added special credit days to this customer of 100 days so the message that appears now looks like this.

They will need to check they have credit terms set up for each of the different offices.