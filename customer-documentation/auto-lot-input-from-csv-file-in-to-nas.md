---
title: "Auto Lot Input From Csv File In To Nas"
source: "Auto Lot Input from CSV file in to NAS.docx"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "New Auto Lot Import in to NAS Sale"
long_description: "New Auto Lot Import in to NAS Sale."
---

New Auto Lot Import in to NAS Sale.

There is a new option in the Options menu below to import lot details in to a new sale in NAS. This will update details from a CSV file in to the current sale. The CSV file does have to be in a particular format but the option will display the field order when the below option is selected.

If this option is selected the screen will show this.

This shows the order the data needs to be in the CSV file for the import to work.

After you click on Continue to progress the system will display an option to select the required CSV file that you want to import in to the current sale. Once you have selected the file you will get a screen showing the lot information that you are trying to import and if there are any problems with the data.

On the above screen you will see there are a number of records in the file that do not have a valid customer number so we cannot find the seller details for these numbers so display No Seller and these records will not be updated to the sale.

The program will do a look up for the breed to get back the breed number in NAS for the breed description entered in the file. This breed description will have to be in the breed system in NAS for the match to work.

The system will also check to make sure that the item type is valid in the file and that it is in a section in the current sale. Again if it is not then the lot will not be updated to the current sale.

To update the information in to the current sale you then just select the Update Lots to Sale option in the File menu at the top of this screen.

This will then go through the details in the grid and update the records it can to the sale. The status of each lot will then be shown on the end of each line in the grid.

If the user tries to import a file in to the sale with the same lot numbers as transactions already in the sale then the system will display a message in the Update Status column informing them if this.

This is only if they have lot checking on for the section being added.