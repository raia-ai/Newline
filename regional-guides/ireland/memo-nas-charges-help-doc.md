---
title: "Memo Nas Charges Help Doc"
source: "Memo NAS Charges Help Doc.docx"
tags: [Regional Operations]
version: "1.0"
last_updated: "2025-11-17"
short_description: "NAS Charges Help Doc Charge Setup and Configuration To set up charge descriptions in NAS go into system configuration and view / setup charges"
long_description: "To set up charge descriptions in NAS go into system configuration and view / setup charges. This option provides a list of all charge descriptions and allows an admin user to setup new charge descriptions."
---

NAS Charges Help Doc

Charge Setup and Configuration

To set up charge descriptions in NAS go into system configuration and view / setup charges. This option provides a list of all charge descriptions and allows an admin user to setup new charge descriptions.

Setup New Charge

Click the Setup New Charge button to launch a setup wizard.

If the charge is linked to an item type, such as commission answer yes. If it is not linked to an item type but instead a one-off charge, or manual charge answer no.

Enter the name \ description for the new charge.

Tick yes if the charge has tax applied. No if it does not.

The tax is worked out on a per lot \ transaction basis. This can be rounded on a per lot basis, giving 1.6 or the figures can be added together and rounded on the sum.

Select how the charge is calculated. The dropdown list shows pre-set options. This list can be limited or increased and is based on formulas to make the charge system in NAS flexible and scalable.

Examples:

If there is a default rate it can be entered here.

You can set charges within groups. Processing charges are grouped under a processing group.

You can set a default customer to be paid out for a certain charge. Pay feed to the auction house.

Charge Groups

Other groups may be useful for applying charges to cows and calves and providing the ability to charge per head on the calf numbers. You will need two charge names, so you can setup different charge by methods for them but group them together on the paperwork (cheque and / or invoice)

Nominal Codes

Click the Nominal Code tab and set up nominal codes against charges.

Add New Nominal

Select a charge from the list

Add a nominal code. If you don’t add an office or item type this nominal code will apply to this charge across the whole company.

Setup Charges for Item types – seller side

Inside a sale go to the setup menu.

Click the Item Type Charges tab so it goes green.

Here you can view what you have set up

Or setup new item type charges. Click the Setup New Itemtype Charge button

In stage 1 Select the charge from the dropdown combo in the wizard and click next. Stage 2 enter the value \ rate of the charge and click next. Stage 3 select the charge by method.

Stage 4 add a minimum value if desired on a percentage style charge by. Stage 5 enables the user to set a maximum value on a percentage style charge by. Stage 6 is not applicable in this release.

Stage 7 sets a charge on unsold lots. Stage 8 lets you apply the charge to specified item types. Stage 9 lets you apply it to specific offices or all offices.

Stage 10 applies the charge settings immediately. In phase 2 there will be option to set a date the charge will take effect. Not available in phase 1 release.

Setup Charges for Item types – buyer side

Setting up buyer charges works the same way as setting up seller charges but the user selects buyer from the dropdown option first.

Processing Database

A default set of processing charges can be setup using the methods above. You can set up a charge within a processing group and give it a default charge by and rate.

Manifest Entry

Add Charges in Manifest Entry

Click the add charges button when a manifest number is entered top left.

You can enter the charge number and press the enter key or double click the charge from the list on the left-hand side.

If the charge by default is correct enter the rate. If you want this charge paid to a third-party search for them in the paid to text box. You can add notes if you wish. Click apply to apply the charge.

The charge record is shown in the summary grid above.

Save your changes.

The charges button now shows you have charges saved against this seller.

Charges Report

Filter options

Show Settled shows charges associated with cheques or invoices that have been produced and have a cheque or invoice number. These charges cannot be amended unless the paperwork is cancelled.

Settled charges have a green background and the settled tick box is ticked and they have an item no, cheque or invoice number.

Auto calculated charges such as commission are calculated per transaction \ lot. They are grouped together but the user can tick show auto calculated to see each charge value per transaction \ lot.

Charge By Options

Flat Rate

Is not charged by transaction. It is simply charged at the total value you enter.

By Head

Is charged by transaction linked to manifest. This example will charge $5 per head on lots sold linked to manifest AN888999.

By Head Multiplier

The user may need to make a per head charge without having lots or on only some of the heads in a lot. This lets the user manually enter the number of heads for the sum.

By Head 2nd Type

Charge by type for cow & calf deals where the number of calves may have charges on them as well as the number of cows.

By CWT

Is charged by transaction linked to manifest. This example will charge based on the (total weight /100) * $0.35

By % Lot

Edit \ Override Charges

From the charges screen double click the row you wish to edit \ override.

If there is only one transaction \ lot you will be presented with this screen

You can click the override button to enter a total figure. Overtype the current figure with the value you want. In this example 50 over written to 35.

You are asked to confirm your change, and advised it will be a flat rate charge averaged across lots.