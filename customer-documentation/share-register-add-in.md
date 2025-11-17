---
title: "Share Register Add In"
source: "Share Register Add-In.docx"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Share Register Intro: The NAS Share Register Add-In allows users to keep a list of all shareholders (and groups of different share holder types)"
long_description: "The NAS Share Register Add-In allows users to keep a list of all shareholders (and groups of different share holder types). Print a share certificate for them and keep an electronic copy against their account. Print dividend cheque or BACs payments. Transfer or sell shares and keep a record of these transactions searchable by date range. It also provides a facility to see the trading history of share holders with numbers and values sold and / or bought across a date range."
---

Share Register

Intro:

The NAS Share Register Add-In allows users to keep a list of all shareholders (and groups of different share holder types). Print a share certificate for them and keep an electronic copy against their account. Print dividend cheque or BACs payments. Transfer or sell shares and keep a record of these transactions searchable by date range. It also provides a facility to see the trading history of share holders with numbers and values sold and / or bought across a date range.

Setup Share Holder Customer Group(s)

Set up a Share Holder Customer Group, or groups if you have different types of share holders or different areas of share holders. Go into the Contact Management menu and set up customer groups menu.

Double click a spare row and type Share Holder and save.

View Share Register

Provides a list of all registered shareholders, including the certificate number, issue date and quantity once at least one share certificate has been printed. You must have at least one share holder entered for the list to be visible. Entering shares is done through menu option 2. Print Share Certificates.

If you have different Share Holder groups you will have a drop-down combo choice to select a group to view.

Print Share Certificates

Lets a user search for a customer that is going to be allocated shares and become a shareholder. This menu option is how shares are loaded onto NAS.

Search for the person.

Enter the certificate number you wish to allocate them and the number of shares they are having and the value of each share. Allocate them to the shareholder group and click continue.

A share cert will then appear in pdf format for the user to print. This can be printed on plain A4 paper and Newline can add a jpg to provide a smart graphic with it or it can be printed on pre-printed stationary.

Print Share Dividends

To pay out dividends select option 3.

Share Transfers

Select the shareholder to transfer from and click the select new shareholder button to transfer to.

Select if you want to sell or transfer the shares.

Enter the quantity of shares and new certificate number and click save.

If not all shares transferred or sold the user is prompted.

View Share Transfers

The user can select a date range to view transfers by. This can be useful if the accountant only wants to see them for a financial year. The user can filter by customer group \ mailing code if they wish.

NB: Customer Groups A.k.a. Mailing Codes can be setup in Contact Management (in the main NAS menu) and Setup Customer Groups.

View Share Transfers provides a list of any share transfers. From and to details. Quantity and date details.

Historical copies of the share certificate can be found on the shareholders customer account.

View Customers Share Holding

Shows a list of customers with shares.

Customer Edit Share Details Tab

The Share Holder account can be the trading account, but in the case where the Share Holder Name is different to the Trading Account Name, or the Name changes. E.g. Simon Jones is the Share Holder and his sons join the business and the Trading Name becomes Simon Jones & Sons Ltd two accounts are necessary to ensure all Share correspondence is only addressed to the Share Holder. The accounts can be linked together though.

Add the Trading Account number in the Share Reg Account box shown above.

If the Share Holder was added to the wrong customer group in error the user may correct the mistake by editing the code field in the grid and editing the customer group in the mailing tab in customer edit.

View Share Holder Trading

Enter the trading date range and click the continue button. It will show the name and address of the share holder and the amount they have traded. This is useful for bonus share decisions.

Trading accounts linked to Share Holder accounts will be shown here too.

Customer Lists

Shows account, name and address and share cert number and the number of shares.

Contacting Share Holders

Use the seller / buyer trading analysis option in the history menu to run a customer group / mailing type report.

Once you’ve made the selection and run the analysis you will have options to contact the share holders by post (address labels), text and / or email.

Shareholder Names – Customer Edit

The system can be setup so share holder names cannot be amended. This prevents users from finding a share holder account and changing the name on the account so a family member can buy \ trade on the account. The user is warned to use another account or the payment tab.

The initials and surname field are disabled if the account is set with a share holder mailing code. If the user clicks the fields to try and amend they see a warning message.

Shareholder List

This list gives a total number of shares at the bottom of the report.

Tech:

Use central update sysinfo keys

INSERT INTO SysInfo (KeyName,KeyCode) VALUES ('SHAREREGISTER','Y')

This key changes the add-in option from Share Certificates to Share Register and provides the share register menu options.

INSERT INTO SysInfo (KeyName,KeyCode) VALUES ('CLIENTDOCS','Z:\CDOCS\')

This is the location the PDF copies will be stored, within the shareholder account number folder.

INSERT INTO SysInfo (KeyName,KeyCode) VALUES (' AUTOFLAGSHARECUSTOMER','S')

Where S is mailing code to show share holder. May vary at different sites. Needs to be set at all remotes sites.

Requires sharecert.tpl

This is required to print the share certificate. Printing the certificate is how the user enters share holder details.

Jpg for share cert

Reference to jpg in headers.ini [Share Certificate]

[Share Certificate]

"Image","FP","","Z:\MASTER\jpegs\share-certificate.jpg"

[ShareBACS]

"Image","FP","","Z:\MASTER\jpegs\sharebacscert.jpg"

Tables

Make sure no null records in customers table for