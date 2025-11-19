---
title: "Imageviewer Import Program"
source: "ImageViewer Import Program.docx"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Image Import Program Running the program will bring a form up as shown in figure 1 Figure : Section Selection Form If there is only 1 section in..."
long_description: "Running the program will bring a form up as shown in figure 1"
---

Image Import Program

Running the program will bring a form up as shown in figure 1

Figure : Section Selection Form

If there is only 1 section in a sale this screen is not shown and the program knows to just deal with that 1 section. Once the user has clicked ok the import program is loaded as shown in figure 2.

Figure 2: Import Screen

This form shows the lots loaded into the current section. It also shows the lot description. This can be either the full description, short description or both depending on what information is stored for that lot.

The lots are optionally filtered to only show lots that do not have images against them. If you untick the option for Hide Lots With Images as shown In figure 3 then lots with images loaded against them are shown and the number of pictures currently loaded for that lot is also shown in the Pics column.

Figure 3: Hide Lots With Images Filter

Select the buttons in the top right hand corner to either import File(S) or a whole folder. Selecting the “Add Folder To Import” option for example will bring up the dialog box as shown in figure 4

Figure 4: Select a folder to import all images from

Once the folder has been selected the program will go through all the files in the folder. Each file is then checked to see if the image has previously been imported into that sale. The check is done on the checksum of the file. If a file has previously been imported then by default it is hidden. These images can still be displayed and re-imported by un-ticking the option Hide Already Imported.

The user will be prompted with the dialog shown in Figure 5

Figure 5: Select an auto-import option

From here the user can select whether they want to attempt to match the filenames to a lot number. If the user selects “Yes All Files” then each file processed will be checked to see whether the filename can be calculated as a lot number. If the user selects No then the calculations are not done and the images can either be assigned to lot numbers manually or as a batch (See notes further on in document). Optionally the user can decide whether to do this on a file by file basis which will show the dialog displayed in figure 6.

Figure 6: Manual Choice For Each Filename

If the user chooses to match filename(s) to lot numbers then Auto-Matching is performed.

Auto-Matching

When a Filename is added to the import program the user has the choice as to whether to attempt the program should attempt to convert that filename to lot number can be matched for that sale. It does this by reading data out of an XML configuration file. The file is called ImageImportMasks.xml and is stored in a folder called XMLConfigFiles off of the master folder.

This config file contains a list of possible masks that can be used for matching lot numbers. If the file does not exist then the following default file is created and used

Each Node called MASK is used. The Mask Text is used to calculate what it prefix and postfix text of the filename. The percent symbol is where you would expect the lotnumber text to be. If Ignore Spaces is set to true then spaces are removed from the filename. If CastAsNumeric is set to true then the filename is cast as a numerical value once the mask text calculations have taken place so a filename of 0001 would be the equivalent of a value of 1. 0001L for would still be a value of 0001L however as the whole filename cannot be converted to a numerical value. I’ve listed some examples below

This is based on Richard Wintertons current requirements but can be adapted for other filename structures. An Example of another mask would be the IPAD convention which typically starts with IMG_ so the 92nd photo taken would have a filename of IMG_0092.

We could add this sort a Mask Node to the Masks collection to calculate that image name as Lot 92 like so:

One important thing to note is the iPad (For example but is similar on many devices) will not reuse a number by default so if the client took an image of lot 92 decided they didn’t like it and re-took it then that image filename would be IMG_0093.jpg. This would throw the calculations out by 1 lot and so auto-import would not be advisable in this case. Richard Wintertons already rename there files for website upload so the auto-import option works well there.

Import Option

Figure 7 below shows the loaded form once images have been loaded. Here I have ran the Autoimport option you can see below that the filenames (Shown in the middle grid) have had their names matched against a lot number. When this happens the lot number is shown against the filename and the import option is ticked.

Figure 7: Import Form After AutoImport Example

Lot numbers can be set/adjusted manually if required by simply changing the value in the lot field. Similarly any images which should be skipped from import can be unchecked.

If the user does not use the autoimport option then the Lot Number field is empty and the import checkbox is not ticked. The user can then manually set the lot numbers if they choose. Alternatively a batch import can be performed.

Batch Import

As previously described some scenarios will mean autoimport is not a valid option even with images taken in a sequential order. For this scenario it is advised to use the batch import. Load any images you want into the application without running the autoimport option as shown in Figure 8

Figure 8: Images loaded that have not been matched

The user can either type the lot numbers into the lot number column or they can perform a Batch Import.

To start a batch import the user can either select the Start Batch Import button or double click either an image or lot number. Once a batch import is started an information provider is then shown on the form above the filenames grid as shown in Figure 9 also zoomed in on Figure 10.

Figure 9: Batch Import Information

Figure 10: Batch Import Information

The user can then select either the first lot or image in the batch by double clicking in the relevant grid. The user can choose whether they want to do images first or lots i.e if the user double clicks a row in the image files grid then they will be prompted for the corresponding lot number and vice-versa. If the user is not sure of the image name then they can single click on the image grid which will then update the preview screen.

For a full example of this working please see this video link below:

If you have an older version of word then the above video may not show in which case you can open the following link in your internet browser:

https://www.youtube.com/watch?v=40MIoWeZTr8&feature=youtube_gdata_player

Importing Lots

Once the relevant images have had lot numbers assigned to them the lots can be imported into NAS by clicking the Start Import button in the bottom right hand corner.

There are several options within the import process.

Rename Files On Import

Selecting this option will rename the files based on the lot number and picture number. This will be more feature rich in future development.

Show Resize Options

Selecting this option allows images to be resized to a separate folder, this can be used for upload to websites or simply to shrink the images for archive purposes. The resize form is shown below in Figure 12.

Figure 1 : Resize Options Form

The output directory can be set using the top textbox or the browse button.

For the actual resize option it is suggested to set the maximum required horizontal and width value and then select the maintain ratio option. In the above example the horizontal is greater than the vertical therefore the resized image will be created so it is 800 pixels wide. The vertical will then be calculated based on the percentage difference of the original. If the maintain option was unchecked then the resized image will be stretched to the values set.

Image Type and quality can be set on this form to allow for more compression if required. JPEG is still currently the best compressed format for images if transparency isn’t required.

The user can also open the output folder(s) if they wish to see the resized images by setting the complete on option.

Finally the user can set these as the settings for all images on the import by selecting the Apply To All Subsequent Images option. If this is un-ticked then this form is shown for each image that will be imported.

Once the resize options the import begins If the lot is entered more than once in the sale the following form is shown so the user can select the correct lot.

Clicking Open Image will show the user the image, Skip Image will skip the import of this one file and clicking Select Lot confirms which lot the file should be imported against.