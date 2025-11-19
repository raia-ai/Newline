---
title: "Tablet Selling"
source: "Tablet Selling.pdf"
tags: [Tablet Applications]
version: "1.0"
last_updated: "2025-11-17"
short_description: "New Alinput Alterations for Tablet Selling"
long_description: "New Alinput Alterations for Tablet Selling. I have added a new form for the user to select the section they want to sell as the current list of sections with the tick box option was very hardwork to get correct. The program checks to see if you have SELLMOBILE set in the registry and if you do it will display the following screen."
---

                    New Alinput Alterations for Tablet Selling.
I have added a new form for the user to select the section they want to sell as the current list of
sections with the tick box option was very hardwork to get correct. The program checks to see if you
have SELLMOBILE set in the registry and if you do it will display the following screen.




Once you have click on the button for the section you want to sell you get this confirm message
appear.




If you click Yes to this you then get the normal section prompts and then the selling screen.

I have moved the zero on the on screen keyboard to after the 9 as per normal keyboards as this was
a real pain when I was using it on Monday. I have also made the next lot grid font slightly bigger and
bold so this stands out a lot more. It also looks like the seller name in the grid was wrong so I have
made alterations to this to show the seller from the transaction.
The on screen keyboard would not work on the purchaser selection screen so if you had to enter a
new customer it was not possible to do this without using the inbuilt on screen keyboard. It was a
fairly major alteration to get this to work due to the fact that the purchaser name search screen was
a modal form and therefore nothing on any other form could be done while this form was loaded. I
have made this a non modal form now and added a variable that we set when the form loads and
clear when the form unloads. The program will then loop once the form is loaded until the variable is
not set. There is a sleep inside the loop so it should not max out the processor. Now when you have
the below screen up and the customer is not in the list you can press the F1- New button and the
program will automatically create an account for the name entered. This is only when in tablet selling
mode.




I have added a new Weight Input flag re Total Weight in the HEAD file so the system knows what to
store when pre entering the lot and then what to do when selling the lot. I have added an option S so
the user can enter the actual average weight with decimal places E.G. 50.9 and this will then show on
the selling screen. Then when the user comes to sell the lots the system will round the weight down
to the nearest whole kilo so this weight would become 50.0. This was something that Exeter needed
as they currently right the full average weight down on the sale sheets and give this out at the time of
selling but then only want to show the rounded down average weight on the invoices and cheques as
they do currently.
