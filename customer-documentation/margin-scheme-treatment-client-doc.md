---
title: "Margin Scheme Treatment Client Doc"
source: "Margin Scheme Treatment - Client Doc.docx"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Introduction This document sets out how Newline may be configured by users to meet their interpretations of different HRMC VAT margin schemes"
long_description: "This document sets out how Newline may be configured by users to meet their interpretations of different HRMC VAT margin schemes."
---

Introduction

This document sets out how Newline may be configured by users to meet their interpretations of different HRMC VAT margin schemes.

Seller Commission Rate

For the examples in this document the seller commission is set as above. A 5% seller commission with a minimum of £50 and max of £600 per lot.

Buyer Commission Rate (aka Buyer Premium)

For the examples in this document the buyer premium is set to 2% with a minimum charge of £5.

Loading Lots

The user selects the VAT or VAT scheme status for the lot during lot entry from the drop-down VAT scheme combo.

Lot Vat status defaults

With this system remove the old AMS sale setup from the configuration.

ensure Auctioneers Margin Scheme unticked.

Within the sale settings.

Item types can be set up to have different defaults when booking lots in. If an item type vatable status is:

yes, the VAT status will default to vatable.

No, the VAT status will default to not vatable.

Check seller, the VAT status will default to whatever scheme has been cross referenced in the VAT schemes table (requires Newline assistance).

The C in the itemtypeflag field cross references to the C in check seller and therefore will default the VAT status to Margin Scheme for item types marked check seller.

Seller Default VAT Scheme

The sale level may be set as AMS. The seller may be set as AMS or Vatable and the item type may be set as Non Vatable, Vatable or Check the Seller VAT status.

Seller is VATABLE

This is denoted by the entry of a VAT number on the account.

Seller is AMS

This is denoted by the AMS textbox having a Y in it.

Item Type Settings

Lot Default Status

Seller is AMS and Item type is check seller, therefore default lot VAT status is AMS.

Seller is VAT registered and item type is check seller, therefore default lot status is Vatable. Note seller Vat number shown in yellow frame on right for visible reference.

Seller is VAT registered but the item type \ good is not a Vatable item, therefore the default will be No VAT.

Edit Lots

To amend a lots VAT Status use the lot edit screen.

Change VAT Status as required and click the F5 Save button.

Seller Transfer

When doing a seller transfer the user is warned if the new seller would have a different VAT status default and prompted if they would like to update the lot VAT statues.

NAS Printing Settings

In NAS there are menu settings that the user may turn on to determine what fields will print out on the paperwork.

Seller Side

Buyer Side

AMS (Auctioneers Margin Scheme)

For more info on this scheme visit HMRC website.

https://www.gov.uk/government/publications/vat-notice-7182-the-vat-auctioneers-scheme/vat-notice-7182-the-vat-auctioneers-scheme

AMS UK Seller:

The example below shows a seller offering 3 lots under AMS. Note the (AMS) in brackets is free text in our example lot description. This is user entered example data only and not added by the system by default. The VAT flag column (highlighted below) has a user configurable system status and is available by default.

See pdf called “Seller N1020 AMS” for printed output example.

Breakdown of charges and VAT on each lot.

No VAT on goods because the seller has chosen to sell the lots under AMS rules. There is no VAT shown separately on the commission or entry fee, although the * shows they are vatable charges. The VAT figure is inclusive in the charges. This extra inclusion is the auctioneers margin under the scheme. The a in the VAT status column indicates the lot is sold under the AMS scheme rules. The E shows the lot has been purchased by a non UK buyer. These VAT flags are user configurable in NAS and can be set up to suit client requirements.

UK Buyer:

There is no VAT on goods because the seller has chosen to sell the lots under AMS rules. The VAT on buyer’s premium is inclusive and is not shown separately (The * to the left of Buyers Prem charge indicates a vatable charge type).

See pdf called “Buyer U246 UK AMS” for printed output example.

Breakdown of charges and VAT on each lot.

Printout VAT scheme messages

These can be configured by the user against different schemes.

Double click to edit the messages. There are variable that can be inserted into the message.

These are different on the seller and buyer sides.

European Buyer:

AMS rules apply and are recognized throughout the EU. Therefore, this is treated in exactly the same way as the UK buyer.

Non-European / Outside Europe:

No VAT on goods is charged as the seller is AMS and the buyer is outside Europe.

Note – the VAT flag is w. It would not normally be w but I have set it to be so in this case to show that users can configure the flag to their requirement. This would be done once by the system administrator at the outset.

VAT Seller:

VAT on goods is charged on all lots sold. The v flag indicates the lot is vatable and the e that the buyer is European. The E flag that the buyer is exporting outside of Europe. These flags may be set by the auction firm as they require. See below. Charges VAT is split out under normal VAT rules and is shown separately.

User configurable paperwork VAT status flags for the seller statement side (seller flag) and buyer invoice side (buyer flag).

UK VAT registered Buyer:

There is goods VAT charged on lot 13. The V column shows a v for vatable lot. The VAT on the buyer’s premium is shown separately.

European Buyer:

Lot 11 is a AMS lot and therefore no VAT on Goods. The VAT on the buyers premium is included in the buyers premium charge. Lot 14 is a vatable lot. VAT on goods has been charged and the VAT on the buyers premium for this lot is shown separately in charges VAT.

See pdf called “Buyer E1304 Euro MXD” for printed output example.

Non-European / Outside Europe Buyer:

See pdf called “Buyer N1021 Non Euro MXD” for printed output example.

For buyers with the country code set to Outside Europe the VAT on goods is automatically zero rated (this is user defined. See pictures below), i.e. not charged. A VAT deposit for the amount of VAT on goods at the normal rate is automatically calculated and added. Proof of export is required under export VAT rules for the buyer to have the VAT deposit refunded.

Note – some sites have this named differently. E.g.

Non Europe

Outside Europe

Worldwide

Margin Scheme

https://www.gov.uk/government/publications/vat-notice-718-the-vat-margin-scheme-and-global-accounting/vat-notice-718-the-vat-margin-scheme-and-global-accounting

The auction may configure the scheme as they require using the VAT calcs configuration screen.

MS UK Seller:

No VAT on goods because the seller is selling under the margin scheme. There is no VAT shown separately on the commission. However, the difference between the Auctioneers Margin Scheme and the Margin Scheme is that VAT is shown separately on other charges like entry fee.

Seller Paperwork

Note the system can be configured to show the commission inclusive of VAT against each lot under a comm column. Commission is £50 per lot and £10 VAT, shown as £60 for the inclusive figure. The paperwork has a user configurable VAT message at the bottom. The system can show a user configurable VAT status flag. See far left of lot details. In this example M shows a margin lot bought by a UK buyer, e shows a margin lot bought by a European buyer and E a margin lot bought by an overseas buyer. These flags can be any letter the auction firm wishes to use.

UK Buyer:

Having specified this charge as a commission charge and ensured it is set to include VAT, the premium and VAT are included in one figure and not shown separately.

Buyer Paperwork

The buyer invoice can be set to show the buyer premium per lot. There is also the option to show a VAT status flag on the far left. The letter is user configurable. A VAT scheme message may be set at the bottom of the paperwork.

European Buyer:

There is no VAT on goods because the seller is selling under MS rules. The commission charge – buyers premium is inclusive of VAT.

Non-European / Outside Europe Buyer:

VAT Seller:

Good status vatable rather than MS.

VAT on goods charged on all lots. Charges VAT shown separately on commission and entry fee.

UK Buyer VAT registered:

There is goods VAT charged on lot 13 (because the seller lot has been set with a VAT status). The V column shows a v for vatable lot.

European Buyer:

Non-European / Outside Europe Buyer:

For buyers with the country code set to Outside Europe the VAT on goods is automatically zero rated, i.e. not charged. A VAT deposit for the amount of VAT on goods at the normal rate is automatically calculated and added. Proof of export is required under export VAT rules for the buyer to have the VAT deposit refunded.

Lot 15 was vatable and has been zero rated. Lot 12 was MS. The vat status flag can be set to be different if the auction firm requires this to make it clearer on the invoice these lots purchased under different VAT schemes.

Print Out Messages

Seller Side (VC)

The amount of VAT shown on this invoice [VAT AMT] against the sale of your goods is your output tax due to the Customs and Excise on your next return.

or

The amount of VAT shown on this invoice £[VAT AMT] against the sale of your goods is your output tax due to the Customs and Excise on your next return. Vat No [VAT NO]

Seller Side (VA)

The amounts of commission etc shown on this statement include VAT which must not be shown separately or reclaimed as input tax by you.

Buyer Side (PI)

If you are registered for VAT this invoice contains £[VAT AMT] claimable as input tax.

Buyer Side (PA)

Input tax deduction has not and will not be claimed by me in respect of goods sold on this invoice and marked m or e above.

Setup VAT Schemes

Select the scheme from the drop-down combo.

Scheme Settings

Here you can setup precisely how you want to run the scheme.

Select whether you want to charge VAT on goods, show separately or include VAT on commission charges, show separately or include VAT on other charges. S

There is a quick method to set data to be the same in a column. Right click the header and select your setting.

Set if you want a scheme message to show on the seller & /or buyer paperwork.

When you set these as you require. Click save scheme settings.

You can tailor the messages as you wish.

VAT Status Flags

Users have the flexibility to set the flags as they wish.

These can be set differently or the same for seller side and buyer side.

Legends

There is an option to set up legends they can print on paperwork to explain the flags. They will print user defined legend text unless set as <not set>.

Click close to exit the change scheme selection.

Seller Notification Letter

The user may wish to print the lots VAT status on the seller notification letter. This helps put the onus back on the seller to check and agree how (under which VAT scheme) they intended the lot to be sold.

Sale Sheets

Show Config menu option has to be setup with column order and width the user wants for the above layout to work.

Tech:

Required exes & dll

Alinput

Balance

Cheques

configureNVC

configurenasdatahost

invoices

NASresources.dll

NASVatCalcs.dll

SQL file to add required table inserts – vatschemes-schema and data.sql

Sysinfo –

USINGNASVATCALCS

SERVERID (used for link to nasdatahost) NET.TCP://LAPTOPNAME:52351

Regasm nasvatcalcs.dll

Nasdatahost must be set up - configurenasdatahost

Tpl options

Odes?

Ctrl-LeftShift-C