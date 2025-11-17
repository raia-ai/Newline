---
title: "Allflex Help"
source: "Allflex Help.doc"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "TABLE OF CONTENTS Chapter 1 3 LOGING ON AND ADDING USERS 3 Chapter 2 7 IMPORTING DATA 7 IMPORT SETUP 8 IMPORT DATA 9 Cha..."
long_description: "EXCEPTIONS 11 Exception Categories 12 Exception Summary 14 Exceptions By Category 15"
---



TABLE OF CONTENTS

Chapter 1   3

  LOGING ON AND ADDING USERS 3

Chapter 2   7

  IMPORTING DATA  7

  IMPORT SETUP    8

  IMPORT DATA     9

Chapter 3   11

  EXCEPTIONS      11
   Exception Categories     12
   Exception Summary   14
   Exceptions By Category   15

Chapter 4   16

  ANIMAL DATA FORM     16

TABLE OF FIGURES

Figure 1    3
Figure 2    4
Figure 3    5
Figure 4    6
Figure 5    6
Figure 6    7
Figure 7    8
Figure 8    9
Figure 9    9
Figure 10   10
Figure 11   10
Figure 12   11
Figure 13   12
Figure 14   13
Figure 15   14
Figure 16   15
Figure 17   16



Chapter 1


LOGING ON AND ADDING USERS


To load the data manager program click  Start  >  Programs  >  Allflex  Data
Manager. Alternatively click the Allflex Data Manager icon, located  on  the
desktop.

You will be prompted to enter a User name and Password as  shown  in  figure
1:

[pic]

Figure 1


The first time you login it must be as the administrator as shown in  figure
1. You will need to ask a member of Newline ASP staff for the password.

The Main screen of the Data Manager will load and appear as in figure 2:

[pic]

Figure 2



Click View > Preferences and you will see the following Import  Setup  form.
See figure 3:

[pic]

Figure 3

This  form  allows  the  administrator  to  set  many   different   options,
restrictions and amendments to lookup tables.  This  will  be  discussed  in
more depth later. For now click on the  User  Administration  tab.  This  is
where login user names are created. See figure 4 and figure 5:

[pic]

Figure 4


Right click on the dark grey space below the Users and Passwords. This  will
bring up options to Add,  Edit  or  Delete  Users.  Pick  the  one  you  are
interested in. Figure 5 provides an example of adding a new user.

[pic]

Figure 5


Here you enter a User Name. (A good tip here is to enter the same name  that
the user has to logon to Windows. Then it will appear as  the  default  user
name when the program is loaded.) If this user needs  to  be  able  to  add,
edit or delete other users then tick the  Allow  Administration  box.  Click
the OK button when you are finished.

Setup all the users when you load the program for the first time. Don’t  use
the administrator login once you have setup your own  name.  Save  this  for
technical support occasions, when dealing with Newline ASP.

Chapter 2



IMPORTING DATA


To import data from farm  management  packages  click  on  the  Imp  Animals
button. Or click File >  Import  Animals.   This  will  display  the  Import
Template Wizard form. See figure 6:

[pic]

Figure 6


Anidata is the  default  farm  management  package.  To  import  files  from
Anidata click the Import button. To import files  from  other  packages  you
will need to make a New Template (More on this later).


IMPORT SETUP


The  Setup  button  enables  the  administrator  to  set   various   options
determining what data should be imported wholesale, and what should not.  It
enables policing of the data to ensure that only accurate data is  imported.
 We look at this option next in figure 7:

[pic]

Figure 7


Born, Bought and Sold should always be ticked. This  is  because  an  animal
must have been born and it is essential to have information about  this.  It
is also crucial to have all the details regarding animals being  bought  and
sold in order to follow their movements accurately.  The other  options  are
optional.  If  you  leave  them  ticked  additional  exception  reports  are
generated which show up administrative errors. (For example  if  the  action
of a Passport being received has been recorded, but no  action  of  passport
applied for. The database  administrator  knows  that  the  farmer  has  not
recorded this information. Because in  reality  if  the  passport  has  been
received it must have been claimed for.)

A tick in the Stop Watch tick box, will create a  message  box  stating  the
length of time it took to import the Farm management files at the end of  an
import. This is optional.

The Search Days text box. Set to 2 in  figure  7,  allows  sets  the  search
spectrum for mirror image bough and sold actions. If animal UK AB1234  56789
is sold on October 19, 1999 he will be bought on this day also.  However  to
allow for people error we  set  the  Search  days  to  2.  Thus  if  someone
recorded the date incorrectly but within 2 days of  the  correct  date,  the
computer would still match it as 2 sides of the same transaction.

The Submit/Receive Days text box is set as default to 30.  This  is  because
when you Apply for a passport you may not  receive  it  straight  away.  The
computer searches on a  30  day  spectrum.  This  is  completely  changeable
depending on administrator preference. Once you have decided  which  options
your project will use you are ready to import the data.


IMPORT DATA


Click the Import button from the Import Template Wizard form. See figure  6.
Figure 8 shows the Locate Tables dialog box. You need to find  the  path  to
the files you intend to import. Or put another way  locate  the  folder  you
want to import and double click on it.

[pic]

Figure 8


[pic]

Figure 9


Click double click on one of the CSV files. Or click on it  once  so  it  is
highlighted and click on the Open  button.  The  import  will  begin  and  a
progress bar appears to show you what is happening. See figure 10:

[pic]

Figure 10


Once the import has finished you will see the Exception Report message  box.
See figure 11:

[pic]

Figure 11


You can choose to view the exceptions, or not view them by  clicking  either
Yes (I do want to view them) or No (I do not want to view them).  Exceptions
are discussed more in Chapter 3.


Chapter 3



EXCEPTIONS


When prompted to view exceptions after an import  by  the  Exception  report
message box (shown in figure 11) Click the Yes  button.  You  will  then  be
presented with the Exception Control form. Seen in figure 12:

[pic]

Figure 12


The Selected Session shows the  current  import  holding  number,  date  and
time. If you want to see other import exceptions  click  the  down  pointing
triangle in the right hand corner of the drop  down  list,  and  select  the
session you want.

The  Exception  Control  consists  of  three  tabs:  Exception   Categories;
Exception Summary; and Exceptions By Category.


Exception Categories


This tab shows the Herd number imported, the date and  time  of  import  and
the type of exception, along with  the  number  of  specific  exceptions.  A
report is generated by clicking the Print button.

[pic]

Figure 13


Click OK to preview the report.

You should see something along these lines, figure 14. If  the  text  merges
meaninglessly it indicates that you need more fonts, or need to  setup  your
print properly.

[pic]

Figure 14


To print the report out click the printer icon. To close  the  report  click
the X, in the top right.


Exception Summary


The Exception summary does precisely what the name  implies.  It  summarises
what herd was imported. How many animals were imported  and  how  many  were
rejected. This is shown in figure 15:

[pic]

Figure 15

Double-clicking on the yellow herd folder. Shown  as  T2235  in  figure  15,
will display a drop down tree. The tree  structure  shows  all  the  animals
rejected. Double-clicking on a specific animal reveals why  the  animal  was
rejected. In figure 15 animal UK Z406400717 is rejected because  the  farmer
has not recorded an action of Born or Bought.


Exceptions By Category


Also based on a tree structure.

[pic]

Figure 16



Chapter 4



ANIMAL DATA FORM


Click the Animals speed button, from the Tool Bar options. Once data  is  in
the database most work is likely to be done in the Animal Data  Form,  shown
in figure 17. In  the  Animal  Data  Form  you  can  view  individual  herd,
selected herds or all herds. You  can  filter  the  herds  into  Active  and
Inactive animals. Definitions of which are in the footnotes.[1] Records  can
be exported to CSV format. Reports can be generated. The form is split  into
two grids. The one on the left is referred to as Grid1 and the  one  on  the
right, is referred to as Grid2.

[pic]

Figure 17





Single Herd


To select a single herd, click the Single Herd option button, (so it  has  a
dot in it) then click the drop down list box and click on the herd  required
( this is the drop down box with T2235 in it in figure 18.)

[pic]

Figure 18


Active \ Inactive


To view only active animals tick the Active tick box only. To view  Inactive
animals tick the Inactive tick box only.


Grid 1


Grid 1 shows rows of animal details. Information such  as  official  number,
date of birth, breed, sex, dam and so on.


Grid 2


Grid 2 has shows the historic action details of the selected animal in  grid
1.


Right Click Menu in Grid


Right clicking on Grid 1 will reveal a menu with options  to  find  data  in
specific columns, sort over all the  columns,  show  and  hide  columns  and
more.


Show \ Hide Columns


If you wish to only show certain columns in either grid, right click on  the
relevant grid and click the option show\hide columns. This brings up a  menu
as shown in figure 19:

[pic]

Figure 19

Tick the boxes of the columns you want to see in the  grid.  When  you  have
made your selection click the X in the top right hand corner.


Sort Over Columns


This option is also selectable from the right click  menu  on  either  grid.
See figure 20:

[pic]

Figure 20

Select the columns you want to sort by. Usually you will only  sort  by  one
or two columns. For instance Breed, and then Sex.

If you just want to sort by one column, either A-Z  or  Z-A  you  can  click
once at the top of the column and it will sort it for you.


Finding Data


Left click once in the column you want to search for data.  Right  click  on
the same grid. You should then see the option to Find in that  column.  Left
click it. If you leave like in the left hand list box,  you  can  type  what
you are looking for in the left and use the * wildcard if you  do  not  want
to type the full word. Press the OK  button  when  this  is  done.  See  the
example in figure 21:

[pic]

Figure 21



ANIMAL DATA FORM FIXED REPORTS


Use the herd and active filters to select the animals  you  want  to  report
on. Click the reports icon, (it has a printer on it.) This will bring  up  a
list of reports you can print as shown in figure 22:

[pic]

Figure 22


Double-click on the report template you require. The data selected from  the
grids will be reproduced in the report template.


Chapter 5


FILTERING



-----------------------
[1] The definition of an active record is that an animal has a Bought  From,
or Born action recorded and no subsequent Sold or Died action, and  will  be
assigned to a herd number recorded in the holding table. That is the  animal
is active in the herd where it actually resides at  the  present  moment  in
time.
The definition of an inactive record is that an animal is recorded  as  Sold
or Died and a historic date of these actions  recorded,  and  no  subsequent
Bought From action recorded against it.  It  will  be  assigned  to  a  herd
number in the holding table.


