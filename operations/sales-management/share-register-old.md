---
title: "Share Register Old"
source: "Share Register Old.docx"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Share Register Intro: The NAS Share register Add-In allows users to keep a list of all shareholders"
long_description: "The NAS Share register Add-In allows users to keep a list of all shareholders. Print a share certificate for them and keep an electronic copy against their account. Print dividend cheque or BACs payments. Transfer or sell shares and keep a record of these transactions."
---

Share Register

Intro:

The NAS Share register Add-In allows users to keep a list of all shareholders. Print a share certificate for them and keep an electronic copy against their account. Print dividend cheque or BACs payments. Transfer or sell shares and keep a record of these transactions.

View Share Register

Provides a list of all registered shareholders, including the certificate number, issue date and quantity once at least one share certificate has been printed.

If you have different Share Holder groups you will have a drop-down combo choice to select a group to view.

Print Share Certificates

Lets a user search for a customer that is going to be allocated shares and become a shareholder.

Search for the person.

Enter the certificate number you wish to allocate them and the number of shares they are having and the value of each share. Allocate them to the shareholder group and click continue.

A share cert will then appear in pdf format for the user to print.

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

Tech:

INSERT INTO SysInfo (KeyName,KeyCode) VALUES ('SHAREREGISTER','Y')

INSERT INTO SysInfo (KeyName,KeyCode) VALUES ('CLIENTDOCS','Z:\CDOCS\')

This is the location the PDF copies will be stored, within the shareholder account number folder.

Requires sharecert.tpl

Jpg for share cert

Reference to jpg in headers.ini [Share Certificate]

[Share Certificate]

"Image","FP","","Z:\MASTER\jpegs\share-certificate.jpg"

[ShareBACS]

"Image","FP","","Z:\MASTER\jpegs\sharebacscert.jpg"

Tables

Make sure no null records in customers table for