---
title: "Nasgovservices Scoteid Pgi Checker"
source: "NasGovServices - ScotEID PGI Checker.pdf"
tags: [NIFAIS Integration]
version: "1.0"
last_updated: "2025-11-17"
short_description: "NasGovServices – QMS PGI Data Download V0.1: 2025-11-12 TR Background: QMS (Quality Meat Scotland) – from their website: “QMS is the public body ..."
long_description: "NasGovServices – QMS PGI Data Download V0.1: 2025-11-12 TR"
---

          NasGovServices – QMS PGI Data Download
V0.1: 2025-11-12 TR

Background:
QMS (Quality Meat Scotland) – from their website:

“QMS is the public body responsible for helping the Scottish red meat sector improve
its efficiency, sustainability, integrity and profitability and maximise its contribution
to Scotland's economy.
Our internationally recognised and approved assurance schemes cover over 90% of
livestock farmed for red meat in Scotland. With centuries of tradition behind
them, Scottish red meat farmers pride themselves on meeting the very highest
standards demanded by modern consumers.”


So if a Scottish farmer can sell his/her animals as being QMS-Assured he/she can command
a higher price for them. NAS can store the assured-status of a given customer (and also
check live on the status of a particular animal) so markets know whether an animal can be
sold as QMS-Assured.



ScotEID provide the data that NAS uses in relation to QMS-Assured statuses.



Previously, there was a utility provided by ScotEID that would download all the QMS
registration data from them to a CSV file, and then NASBEND would read this file and
update the data into NAS. The registration data would only be updated once a week and so
there was a mechanism in NASBEND that when a user goes into a sale that is configured as
being in Scotland (or the sysinfo key “UsingQMSDLL” was present and set to “Y” – see
further below) we would check to see when the data was last downloaded and if more than
6 days ago would prompt the user if they want to do a download:
This would then go and run the ScotEID-provided Downloader that would pull the data
down to a CSV file, and then NASBEND would read this file and import it into NAS.



ScotEID have now introduced an additional endpoint to their web service where we can
download the data directly from them, so we have added support for this in
NasGovServices.



The process is pretty much the same except that the data is now updated daily by ScotEID
and we can pull the data directly into the NAS database, so NASBEND has been changed
slightly so that when the user goes into a sale, if the QMS data has not been downloaded
today the user is prompted if they want to download it now:




If the user says Yes to this, then NASBEND makes a request to GovServices to go and
download the QMS data, and waits for a response from GovServices as to whether the
download was successful or not.
Depending on a few factors, this can take up to 20-30 seconds. GovServices makes a
request to ScotEID for the full QMS data download and if it successfully receives the data,
then takes care of importing this into NAS. GovServices will then reply to NASBEND.



If the download is successful, then the user will see:




And the user can click on OK and carry on into the sale



If there is a problem with the ScotEID credentials then the user will be prompted:




ScotEID credentials are set on an office-by-office basis in the Offices Configurator:
Otherwise, if the download fails for some reason the user will be prompted:




And there should be some more info on the issue in the prompt.




Slightly More Technical:


The “UsingQMSDLL” sysinfo key is for cases where a market might be close to the
England/Scotland border, and so their sale might be marked as being in England but they
will be dealing with Scottish customers and animals and so need access to the QMS data.



Tables:

QMSDATA: the actual registration data from ScotEID




If we receive and digest the full data download from ScotEID then we clear out all the
existing data from the QMSDATA table and re-insert the new data from scratch.

The data has the QMS registration number, the holding that the status applies to, the name
of the customer, the address of the holding, the *current* scheme membership of the
customer/holding, and then some details of when this holding number joined or left the
various schemes.



For reference, Membership type can be:

B – Beef

L – Lamb

J – Joint (Beef and Lamb)

O – Out (not in any scheme)

More info can be found in the document “QMS_Traceability_Checker_API_v1.0.pdf”



QMSDATES: this keeps a track of when downloads of the registration data had been done.




When a download has been successfully done, then we flag all existing records as
Deleted=’Y’, and insert a new record with the date of the download and the flag of “Q” so
we know that the download just done was for QMS data.

This is the table that NASBEND checks to work out if a download has been done today or
not, so in the above data the last download was on the 2025-11-11 and if I was accessing a
valid sale today NASBEND would prompt if I wanted to do a download. If today was the
2025-11-11 and I wanted to force a prompt-to-download so as to download the data again,
then you could either flag the top record as Deleted, or just actually delete the record
altogether.
VERSIONS:
All that is needed is:

NASBEND.EXE v16.0.233 or higher.

NasGovServices v1.9.6.1 or higher.



NASBEND checks on which version of NasGovServices it is talking to, and if a high enough
version then will automatically switch over to using the new ScotEID PGI downloader.
