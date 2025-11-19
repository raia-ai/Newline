---
title: "Aphis Operation Of Markets"
source: "APHIS Operation of Markets.doc"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "New Functionality for Operation of Markets Using ELA Hyperlink to Market Download DLL A new menu option, ‘Mar..."
long_description: "New Functionality for Operation of Markets Using ELA"
---


New Functionality for Operation of Markets
                                  Using ELA


Hyperlink to Market Download DLL


A new menu option, ‘Market Download – Full Download’ has been added to
eLivestock to allow market operators to request Full Market Downloads for
the signed on date. This replaces the need to sign on to ruralnoi.gov.uk as
mkt001.


                       [pic]
                         Figure 1: eLivestock Menu

On selecting the Full Download option the user will be informed that a FULL
download request has been made and a progress bar will be displayed.

The download request will be made via a call to the Market download dll and
when it has been processed the user will be prompted to download the file
to a location on their local machine.

The information contained in the Full Download will depend on the time at
which the request is made.  A complete ‘Full Download’ will only be created
if a request is made at the end of the market day.




Resident Animals


After a Movement Out Upload, market operators examine the market list in
order to determine if there are any animals still in the market.

As the market list contains details of all the animals that have moved
through the market that day, the market operators must examine the ‘At
Market’ value of each animal in order to determine if it is resident (At
Market = ‘C’), on a notification out of the market (At Market = ‘P’), not
present (At Market = ‘NP’) or has already moved out (At Market = ‘M’).

With the average market handling up to 400 animals each day, this can be a
very tedious and time consuming process.

To avoid this problem a new menu option, ‘Market List - Resident Animals
Only’ has been added to the elivestock application.

                       [pic]


This option will only retrieve details of animals that are physically in
the market at that particular point in time.  The animals will be ordered
according to their ‘At Market’ value. Those with an ‘At Market’ value of
‘C’ will be listed first in lot number order, followed by those with an ‘At
Market’ value of ‘P’ in lot number order.  Animals with ‘At Markets’ values
of ‘NP’ or ‘M’ will not be listed.

The individual animal information returned by ‘Resident Animals Only’ will
be identical to that returned by ‘Market List’ and will be displayed in
exactly the same format. It will also be possible to edit animal details,
edit lot numbers and mark animals as Not Present on the results screen.






Generating Market Document Numbers


Currently markets apply their own unique numbering system when recording
movements out of market.  However, when the details of movements out are
uploaded via elivestock, ‘S’ documents are automatically generated for each
valid movement.

As there is no easy way to correlate the market document numbers with the
system generated ‘S’ document numbers, this process has now been  replaced.

Markets will now request and download batches of ‘M’ document numbers via
eLivestock. Markets will then use these allocated numbers when recording
actual movements out and will also include them in the Movement Out Upload
file.  The Upload functionality will subsequently record the moves against
these ‘M’ documents, instead of generating new ‘S’ documents.  This overall
process will be similar to the allocation and use of ‘V’ documents on Main
Aphis.


      Requesting Document Numbers


A new option, ‘Market Documents - Request Market Documents’ has been added
to menu on eLivestock, as shown on Figure 1.

                       [pic]
         Figure 1: ELA Menu options

Upon selection of this option, the Request Market Documents form will be
displayed (Figure 2).  Markets will be required to input a value between 1
and 1000. The upper limit of 1000 is held as a parameter and can be changed
if required.

[pic]
                                                        Figure 2: Request
Form

When the Order button is pressed on the Request form, the number of
requested documents will be validated to ensure that it is a numeric value
between 1 and specified maximum.  If a valid number has been requested the
appropriate number of documents will be created and allocated to the signed
on market.


Request Confirmation


Once all the document numbers have been successfully allocated a
confirmation screen will be displayed (Figure 3).  This will list the range
of ‘M’ document numbers that has been allocated to the signed on market.


                    [pic]

                                                   Figure 3: Request
Confirmation

Pressing the ‘Download XML’ button will prompt the market to download the
allocated ‘M’ document number range. The format of the download XML is
shown in Figure 4 and it is important the file is downloaded at this stage
as there will be no other opportunity to do so.

   <VMLMessage Type="TAG-ALLOCATION-RESULTS">
   <uploadFileName>tagallocation.xml</uploadFileName>
   <allocation>
          <requestDate>14/01/2008</requestDate>
      <startDocument>S400000965</startDocument>
      <endDocument>S400000965</endDocument>
   </allocation>
   </VMLMessage>

Figure 4: Tag allocation XML


Third party market software will subsequently upload this XML file and use
the allocated ‘M’ document numbers when creating MC2 documents for
movements out.


Additional Minor Amendments To eLA


Several other minor amendments have also been made to the eLivestock
application.  These are described below and primarily involve the
repositioning of buttons on screens and small text amendments.

(Confirm Out Screen)

The OK button on this screen is currently positioned at the very bottom and
users frequently have to scroll down or resize the screen to see it.  To
avoid this situation the OK button has been repositioned closer to the top
right of the form.

Users will no longer be required to populate the Issued To and Comments
fields on this form. In addition these input fields will be repositioned so
that they can be viewed along with the Lot Number Grid.




Upload Enhancements

Movements detailed in ‘Move Out’ Upload files can involve multiple animals.
 However, these movements will only be recorded if all the associated
animals can be moved successfully.  When an individual animal cannot move
an appropriate error message is returned.  The following text will now be
appended in BOLD font onto this message:

“NB ANY OTHER ANIMALS CONSIGNED WITH THIS ANIMAL MAY REQUIRE RE-SENDING OR
MANUAL LICENCING”

This additional text will be displayed on the confirmation screen and will
also be contained in the printed version of the errors.


Upload Confirmation


When a user attempts to upload a file detailing movements out of market,
they are required to indicate if the file is the last upload of the day.
If they respond yes, eLivestock will process the file as normal and will
then check if there are any animals still residing in the market.  If one
or more animals are found, the application will then display a warning
message to the user.

The last upload prompt is currently created using the java-script ‘confirm’
function and as a result the response buttons are labelled ‘OK’ and
‘Cancel’.  Although pressing the ‘Cancel’ button correlates to answering
‘No’, the naming of the button has caused some confusion with eLivestock
users.

                 [pic]
                 Figure 5: Original Upload Prompt

This generic pop up screen will therefore be replaced with an html page
that will be displayed in a new browser window. The page will contain the
upload prompt and ‘Yes’, ‘No’ and ‘Cancel’ buttons as illustrated below.


                                   [pic]
                                   Figure 6: New Upload Prompt







