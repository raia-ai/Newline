---
title: "Gdpr In Nas Cleanse Customer Records"
source: "GDPR in NAS Cleanse Customer Records.docx"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "GDPR – Cleanse Customer Records Admin users may cleanse customer data from NAS to comply with GDPR"
long_description: "GDPR – Cleanse Customer Records"
---

GDPR – Cleanse Customer Records

Admin users may cleanse customer data from NAS to comply with GDPR.

Click the Help Menu for information and instructions.

Select the date range and options as described in the help section and click the Ok button.

These options clear all customer data completely and permanently before the date range selected if they are no longer trading, or not in a customer group that you wish to keep, or do not have a live debt, and before 7 years ago for the copy cheques, invoices and end of sale reports.

Passwords are required to run the options. Ask Newline.

Tech: Need to add records to PWLIST

Distribute centrally

Version 16.0.44 custlist

New audit table – updated when above options run

CREATE TABLE GDPRlog (

GDPRid int(11) NOT NULL auto_increment,

userid int(11) default '0',

daterun date default '1901-01-01',

datefrom date default '1901-01-01',

optionrun varchar(20) default '',

notes varchar(200) default '',

deleted char(1) default '',

PRIMARY KEY  (GDPRid)

) TYPE=MyISAM;

Log example