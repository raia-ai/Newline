---
title: "Cheque Cash To Change Software"
source: "Cheque Cash to Change Software.pdf"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "New Cheque / Cash to Change Option for IR Markets"
long_description: "New Cheque / Cash to Change Option for IR Markets."
---

             New Cheque / Cash to Change Option for IR Markets.

The Irish markets take a lot of cheques in from people and convert these to cash so they wanted an
option to be able to record this information on the system to help with their balancing at the end of
the sale. We have a new option on the Buyer Reports Menu option 7 for this.




If you select Option 7 you will get the following screen.
The user will enter the customer number of the person giving them the cheque or cash in the Money
In Frame on the left of the screen. You can enter either the Newline Computer number in to find the
customer or the old Info number but there is currently no name search option.

The program will automatically populate the customer number in the OUT frame as it presumes that
you are giving the money back to the same customer. You can amend this if it is different but the
system will display a warning message that this is actually what you want to do.

You then enter the amount of cash and cheque given in. You can enter all of the information off of
the cheque if required or just enter the bits that you want.

In this example I have entered a value of €4000 cheque IN and the mart has then given the customer
€100 in cash and the rest as a cheque back.




If the information is correct then the user clicks on Save or presses F5 to Save and the information is
then written away to the MYSQL table and also the grid at the bottom of the screen so the user can
view what they have already entered.

If the user exits the program and then goes back in later to add more information the grid at the
bottom of the screen will be populated with the previously entered details so they know what they
have already done and other users have already entered.
Sale Control Account Report.
There is a new set of totals in the sale control account report so that the user can check that they
balance their cash and banking before they close the sale and also when they close the sale.

There is a new header in the grid with the seller details in as per the below screen.




This will move down this grid as seller cheques are printed as in this example there are no seller
cheques printed yet.

These totals should net out to zero as the process should be money in and money out but if there is
a problem and the user wants to easily check that they have entered everything correctly then they
can double click on one of these new totals and get the following information.
This shows the break down details for the cheque in details.
