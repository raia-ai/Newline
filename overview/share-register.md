---
title: "Share Register"
source: "Share register.docx"
tags: [Overview and Introduction]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Share register There is a share register add-on available for the NAS system"
long_description: "There is a share register add-on available for the NAS system."
---

Share register

There is a share register add-on available for the NAS system.

Intro:

The NAS Share register Add-In allows users to keep a list of all shareholders. Print a share certificate for them and keep an electronic copy against their account. Print dividend cheque or BACs payments. Transfer or sell shares and keep a record of these transactions.

View share register

Provides a list of all registered shareholders, including the certificate number, issue date and quantity.

Print share certificate

Lets a user search for a customer that is going to be allocated shares and become a shareholder.

Search for the person.

Enter the certificate number you wish to allocate them and the number of shares they are having and the value of each share. Allocate them to the shareholder group and click continue.

A share cert will then appear in pdf format for the user to print.

Print share dividends

To pay out dividends select option 3.

Share transfers

Select the shareholder to transfer from and click the select new shareholder button to transfer to.

Select if you want to sell or transfer the shares.

Enter the quantity of shares and new certificate number and click save.

If not all shares transferred or sold the user is prompted.

View share transfers

Provides a list of any share transfers. From and to details. Quantity and date details.

Historical copies of the share certificate can be found on the shareholders customer account.

View customer share holding

Option 6 shows the same information as option 1 but is sorted by surname rather than sorted by cert number.

Tech-

INSERT INTO SysInfo (KeyName,KeyCode) VALUES ('SHAREREGISTER','Y')

Requires sharecert.tpl

Jpg for share cert

Reference to jpg in headers.ini [Share Certificate]

Tables

Make sure no null records in customers table for