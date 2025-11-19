---
title: "Vbsendmail"
source: "vbSendMail.doc"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "vbSendMail.dll Version 3.65 by Dean Dusenbery & FreeV..."
long_description: "vbSendMail.dll Version 3.65"
---


vbSendMail.dll
                                Version 3.65

                                     by

                       Dean Dusenbery & FreeVBCode.com
                          http://www.freevbcode.com



Disclaimer:  The vbSendMail component and accompanying files are provided
“as-is” by FreeVbCode.com, which is not responsible for any harm to
computer systems or software with which it is used. You are free to modify
the code and/or use the package yourself in any way you see fit. You are
free to redistribute the package under the following conditions: as 1)
appropriate credit is given to FreeVBCode.com and Dean Dusenbery (the co-
author of the component), 2) this documentation is provided unaltered and
in full, and 3) you do not charge any kind of fee for the code or binary
version of the class without the express permission of FreeVBCode.com.
This permission does not include the right to upload the package to another
web site.  DO NOT, UNDER ANY CIRCUMSTANCES, POST (OR SUBMIT FOR POSTING)
THIS PACKAGE OR ANY PORTION THEREOF ON ANOTHER WEB SITE WITHOUT THE WRITTEN
PERMISSION OF FREEVBCODE.COM

Overview    4

  Introduction   4
  Credits   4
  Package Contents     5

Usage 6

  Introductory Example 6
  Sending multiple e-mails   6

Basic Properties 9

  From      9
  FromDisplay    9
  Message   9
  Recipient 9
  CcRecipient    10
  CcDisplayName  10
  BccRecipient   10
  ReplyToAddress 10
  SMTPHost  11
  SMTPPort  11
  POP3Host  11
  Subject   11
  Attachment     12
  Delimiter 12
  Priority  12
  Receipt   13

Advanced Properties    13

  PersistentSettings   13
  EmailAddressValidation     14
  SMTPHostValidation   14
  ConnectTimeout 15
  ConnectRetry   15
  MessageTimeout 15
  EncodeType     16
  UseAuthentication    16
  UsePOPAuthentication 16
  UserName  17
  Password  17
  AsHTML    17
  ContentBase    18
  MaxRecipients  18

METHODS     19

  Send      19
  Connect   19
  Disconnect     19
  IsValidEmailAddress  19
  GetIPAddress   20
  GetIPHost 20
  Ping      20
  MXQuery   21

EVENTS      22

  SendSuccesful  22
  SendFailed     22
  Status    22
  Progress  23

TROUBLE SHOOTING 23

  Distribution Issues  23
  Run time error 429   24
  License Error  24
  VbSendMail Error Messages  24
  SMTP Server Errors   24
  Dial Up Networking   25
  ASP Errors     25
  What’s Regsvr32.exe ?      25
  SMTP Server Configuration Issues      25
  Spam and Mail Bomb Issues  26

UPDATE HISTORY   26

  Version 3.65 Released 9/05/2003 26
  Version 3.54 Released 3/23/2002 26
  Version 3.52 Released 1/24/2002 26
  Version 3.50 Released 7/21/2001 27
  Version 3.04 Released 3/21/2001 27
  Version 3.03 Released 2/16/2001 27
  Version 3.02 Released 1/12/2001 27
  Version 3.0 Released 1/3/2001   27
  Version 2.71 Released 09/04/2000      28
  Version 2.70 Released 08/05/00  28
  Version 2.61 Released 06/12/00  28
  Version 2.6 Released 06/04/00   29
  Version 2.0 Released 04/18/00   29
  Version 1.75 Released 03/20/00  30
  Version 1.6.1 Released 03/09/00 30
  Version 1.6: Released 12/12/1999      30
  Version 1.0: Released 9/8/1999  31

KNOWN ISSUES     31



Overview




Introduction


If you've ever wanted to send simple e-mail messages with Visual Basic, and
you've tried struggling with third party .OCXs or Microsoft's unwieldy MAPI
or CDO libraries, then vbSendMail.dll is for you.

This .DLL, developed in VB6, provides the simplest possible interface to
SMTP mail.  It is great for applications that have a mail form on it, or
for those where mailing to multiple recipients is necessary.

The .DLL allows you to send multiple file attachments in an e-mail, or send
the e-mail to multiple CC Recipients.  And, it contains a number of
advanced properties, described below, that are optional but useful under
special circumstances (e.g., the SMTP server requires login, you want to
send your e-mail formatted as HTML, etc.).

The .DLL works by encapsulating a Winsock control, sending messages based
on the SMTP protocol to the mail host, and responding to replies from the
SMTP host.  This document will focus on the usage of the .dll; for further
details on its implementation, consult the code itself.

Visual Basic 6 or above is required because a number of built-in methods
(e.g., Split, Replace) only available in VB 6 are used. It should be
relatively painless to develop VB 5 replacements for these built in methods
and use this code in VB5 as well. In fact, if you search FreeVBCode.com,
you will find VB5 friendly versions of all the VB6 specific functions used
in this component.





Credits


      • Thanks to all of the users of vbSendMail for your feedback and
        suggestions, without which many of the feature additions and
        improvements to the component would never have been made.
      .
      • All of the changes from version 2.0 forward were made by Dean
        Dusenbery,  http://www.freevbcode.com/AuthorInfo.asp?AuthorID=2365
        resulting in considerable improvement of the component.  Many
        thanks go out to Dean.


      • The functions that provide name server MX lookup were adapted from
        code provided by Gregg Housh. Thanks Gregg.


      • Thanks to Lance Peterson,
        http://www.freevbcode.com/AuthorInfo.asp?AuthorID=2022  for adding
        support for multiple file attachments starting with version 1.75.


      • I used Carl Franklin's book Visual Basic 4.0 Internet Programming
        to learn how to use Winsock to communicate with an SMTP server.
        See http://carl.franklins.net for more information.


      • Sam Huggill's web site, http://www.vbsquare.com has a tutorial on
        Base64Encoding.  This is where I learned how to add the file
        attachment feature to the program (This routine has been re-written
        by Dean, but thanks to Sam for getting us started).


      • The functions that use Ping and IP Address/Host Name Resolution
        were adapted from Richard Deeming's IP_UTILS .bas module, which is
        available at http://www.freevbcode.com/ShowCode.asp?ID=199





Package Contents


   The .zip file you've downloaded should contain the following:


   1) The binary compiled version vbSendMail.dll.


   2) All the code components of vbSendMail.dll, including
      -- SendMail.cls
      -- frmSckt.frm
      -- modDNS.bas
         -- vbSendMail.vbp


   3) Code for two simple application clients that utilize the
      vbSendMail.dll, including
        -- frmSendMailExample.frm
        -- SendMailExample.vbp
        -- frmBulkMailExample.frm
        -- BulkMailExample.vbp


   4) The project group files that include the .dll server and the sample
      clients.
      -- SendMailExample.vbg
         -- BulkMailExample.vbg


   5)  A sample .asp file that uses the component, vbSendMail.asp.


   6) A Zip file containing a separate project demonstrating the MX query
      module.


   7) -- This read me file.





Usage




Introductory Example


Sending e-mail via this .dll is as simple as the following three easy
steps:

1)     ' Module Level Declaration (WithEvents optional but recommended)
      Private WithEvents poSendMail as vbSendMail.clsSendMail

2)    ‘ form load or module main sub…
      Private Sub Form_Load()

           ‘ initialize the component
           Set poSendMail = New clsSendMail

      End Sub

3)    ‘ use a command button to send the message
      Private Sub cmdSend_Click()

           'Assumes you have a form with text boxes named as below
           poSendMail.SMTPHost = txtServer.Text
           poSendMail.From = txtFrom.Text
           poSendMail.FromDisplayName = txtFromName.Text
           poSendMail.Recipient = txtTo.Text
           poSendMail.RecipientDisplayName = txtToName.Text
           poSendMail.ReplyToAddress = txtFrom.Text
           poSendMail.Subject = txtSubject.Text
           poSendMail.Attachment = txtFileName.txt      ‘ file
      attachment(s), optional
           poSendMail.Message = txtMsg.Text
           poSendMail.Send

      End Sub

The above example illustrates basic usage of this component.  If all you
want to do is send mail with 0 or 1 attachments to one person at a time,
this example probably tells you all you need to know about the component.





Sending multiple e-mails


Assuming the sender, the subject, and the message are the same, there are
two ways to send multiple emails.  One is to specify multiple Recipients
and/or CCRecipients via the Recipient, RecipientDisplayName, CCRecipient,
and CCRecipientDisplay properties.  See the documentation for these
properties for more information.

      ‘ multiple recipients with semicolon delimiter, two shown…
      poSendMail.SMTPHost = txtServer.Text
      poSendMail.From = txtFrom.Text
      poSendMail.FromDisplayName = txtFromName.Text
      poSendMail.Recipient = “johns@domain.com;janes@domain.com”
      poSendMail.RecipientDisplayName = “John Smith;Jane Smith”
      poSendMail.ReplyToAddress = txtFrom.Text
      poSendMail.Subject = txtSubject.Text
      poSendMail.Message = txtMsg.Text
      poSendMail.Send

The second method involves populating all the properties for the first
message, and only the Recipient and RecipientName for subsequent e-mails.
For example.

      ' first message
      poSendMail.SMTPHost = txtServer.Text
      poSendMail.From = txtFrom.Text
      poSendMail.FromDisplayName = txtFromName.Text
      poSendMail.Recipient = Recipient(0)
      poSendMail.RecipientDisplayName = RecipientName(0)
      poSendMail.ReplyToAddress = txtFrom.Text
      poSendMail.Subject = txtSubject.Text
      poSendMail.Message = txtMsg.Text
      poSendMail.Send


      '2nd message
      poSendMail.Recipient = Recipient(1)
      poSendMail.RecipientDisplayName = RecipientName(1)
      poSendMail.Send

      ' etc

In other words, the properties are not reset after a mail message is sent.
This design makes the component efficient for use in applications where
mailings of the same message to multiple recipients is required.

Alternatively, you can use the Connect and Disconnect properties to improve
performance when sending a large number of messages. This example
illustrates how you could read the Recipient list from a database recordset
called MyData.

      ‘ setup the properties that are common to all messages
      poSendMail.SMTPHost = txtServer.Text
      poSendMail.From = txtFrom.Text
      poSendMail.FromDisplayName = txtFromName.Text
      poSendMail.ReplyToAddress = txtFrom.Text
      poSendMail.Subject = txtSubject.Text
      poSendMail.Message = txtMsg.Text


      ‘ establish the server connection
      If poSendMail.Connect Then


           ‘ loop through the data set
           Do While Not MyData.EOF
                  poSendMail.Recipient = MyData!Recipient
                 poSendMail.RecipientDisplayName = MyData!RecipientName
                 poSendMail.Send
                 MyData.MoveNext
            Loop

            ‘ disconnect from the server
            poSendMail.Disconnect

      End If

Please refer to the included BulkMailExample and SendMailExample projects
for working samples of how to use these properties and methods.

Basic Properties


The following properties need to be set to send e-mail and/or are very easy
to use.


From


      Public Property Get From() As String
      Public Property Let From(ByVal NewValue As String)


      The e-mail address of the sender.





FromDisplay


      Public Property Get FromDisplayName() As String
      Public Property Let FromDisplayName(ByVal NewValue As String)


      The sender's display name; usually set to the sender's first and/or
      last name. In most e-mail programs, this value is displayed as the
      "From" field.



Message


      Public Property Get Message() As String
      Public Property Let Message(ByVal NewValue As String)


      The message body text.



Recipient


      Public Property Get Recipient() As String
      Public Property Let Recipient(ByVal NewValue As String)


      The e-mail address of the recipient(s).  If you'd like to specify
      multiple recipients, delimit the e-mail addresses with a semicolon (;)
      or you can set a custom delimiter with the Delimiter property.



RecipientDisplayName

      Public Property Get RecipientDisplayName() As String
      Public Property Let RecipientDisplayName(ByVal NewValue As String)


      The recipient(s)' display name; usually set to the recipient's first
      and/or last name. In most e-mail programs, this value is displayed as
      the "To" field.  When specifying multiple recipients, delimit their
      names with a semicolon or you can set a custom delimiter with the
      Delimiter property.





CcRecipient


      Public Property Get CcRecipient() As String
      Public Property Let CcRecipient(ByVal NewValue As String)


      The e-mail address of the CCrecipient(s).  If you'd like to specify
      multiple CCrecipients, delimit the e-mail addresses by a semicolon or
      you can set a custom delimiter with the Delimiter property.




CcDisplayName


      Public Property Get CcDisplayName() As String
      Public Property Let CcDisplayName(ByVal NewValue As String)


      The CCrecipient(s)' display name; usually set to the recipient's first
      and/or last name. When specifying multiple CCrecipients, their names
      with a semicolon or you can set a custom delimiter with the Delimiter
      property.



BccRecipient


      Public Property Get BccRecipient() As String
      Public Property Let BccRecipient(ByVal NewValue As String)


      The e-mail address of the BccRecipient(s).  If you'd like to specify
      multiple BccRecipients, delimit the e-mail addresses by a semicolon or
      you can set a custom delimiter with the Delimiter property. Unlike
      recipients and CC recipients, there is no corresponding DisplayName
      property for blind recipients.




ReplyToAddress


      Public Property Get ReplyToAddress() As String
      Public Property Let ReplyToAddress(ByVal NewValue As String)


      The default address to which a message reply will be addressed.  This
      property is optional.  It is useful if you want the recipient to reply
      to a different e-mail address than the one from which the message is
      sent.





SMTPHost


      Public Property Get SMTPHost() As String
      Public Property Let SMTPHost(ByVal NewValue As String)


      The mail host (i.e., the remote machine which processes the sent e-
      mail).  Can be in "dotted quad" (e.g., 211.23.141.7) or domain name
      (e.g., mymailhost.com) format.


      Important change! Starting with version 3.5 vbSendMail supports
      Automatic host lookup. Leaving the SMTPHost Property blank will invoke
      the search when the Send Method is called. If a suitable host is
      found, the SMTPHost property will be loaded with the host name. If the
      SMTPHost property is blank and a host is not found the Send Method
      will fail. Optionally, you can manually perform a  search by using the
      new MXQuery Method




SMTPPort


      Public Property Get SMTPPort() As Long
      Public Property Let SMTPPort(ByVal NewValue As Long)


      The SMTP port on the remote host.  This property has a default value
      of 25, which conforms to the SMTP standard.  Unless you are sending
      mail via a machine where the SMTP port was changed to a non-standard
      value, you don't have to set this property.



POP3Host


      Public Property Get POP3Host() As String
      Public Property Let POP3Host(ByVal NewValue As String)


      Optional, only required by servers configured for ‘POP First’
      operation. The POP3 mail host (i.e., the remote machine which
      processes e-mail).  Can be in "dotted quad" (e.g., 211.23.141.7) or
      domain name (e.g., mymailhost.com) format. The POP3Host is used for
      authentication purposes only, as required by some ‘POP first’ servers
      like Yahoo (smtp.mail.yahoo.com & pop.mail.yahoo.com). Both the
      SMTPHost and the POP3Host must be specified. They may be, but are not
      required to be, the same. You must have a valid e-mail account on the
      server and some servers require you to use the account’s ‘From’
      address (e.g., yahoo). Related to: UsePOPAuthentication.


Subject


      Public Property Get Subject() As String
      Public Property Let Subject(ByVal NewValue As String)


      The message's subject.




Attachment



      Public Property Get Attachment() As String
      Public Property Let Attachment(ByVal NewValue As String)


      The full path of one or more files to attach.  If you are attaching
      multiple files, separate entries with a semi colon or you can set a
      custom delimiter with the Delimiter property. The file(s) will be
      encoded according to the Base64 or UU encode algorithm selected by the
      EncodeType Property.


      Important change! When  sending HTML mail by setting the AsHTML
      property to True, the email body is scanned for tags that include file
      names that match the file names set in the Attachment Property.  All
      names that match are automatically encoded as embedded objects
      belonging to the HTML body and may or may not be available to the
      recipient as separate attachments that can be copied using the mail
      clients ‘save attachment’ feature.  See AsHTML for more information
      about embedded files.




Delimiter


      Public Property Get Delimiter() As String
      Public Property Let Delimiter(ByVal NewValue As String)

      A single character string used to separate multiple entries in
      properties that support multiple entries, e.g. Recipient,
      RecipientDisplayName, Attachment, etc. The default value is the
      semicolon “;”.  This property does not need to be set unless you want
      to change the default delimiter character to something else.  Only
      single character strings are accepted. If a multiple character sting
      is passed, only the left most character will be used.



Priority


      Public Property Get Priority() As MAIL_PRIORITY
      Public Property Let Priority (ByVal NewValue As MAIL_PRIORITY)

      Sets the priority of the email message to one of the following values:


           Public Enum MAIL_PRIORITY
                 HIGH_PRIORITY = 1
                 NORMAL_PRIORITY = 3         ‘ default value   = normal
                 LOW_PRIORITY = 5
           End Enum


      Email priority is an attribute that is passed along with the email in
      a MIME header. Note that not all email clients are compatible with
      this property.



Receipt


      Public Property Get Receipt() As Boolean
      Public Property Let Receipt (ByVal NewValue As Boolean)

      Sets / clears the return receipt request flag (default = False).  If
      set, outgoing mail will include a request that a ‘return receipt’ be
      sent back to you once the email has been read. Not all email clients
      support this feature.



Advanced Properties


All of the following properties are optional and in some cases, should be
used by advanced users only.  If you choose not to set them, defaults will
be set automatically by the component.


PersistentSettings


      Public Property Get PersistentSettings() As Boolean
      Public Property Let PersistentSettings(ByVal NewValue As Boolean)


      If this value is set to true, the values of all of the following
      properties are saved to the registry when they are set.


           FromDisplayName
           From
           SMTPHost
           EmailAddressValidation
           SMTPHostValidation
           SMTPPort
           ConnectTimeout
           MessageTimeout
           ConnectRetry
           UseAuthentication
           UserName


      FromDisplayName, From, and SMTPHost need to be set at least once.  If
      you set PersistentSettings to true, you will not need to set them
      again when the component is instantiated for a second time (unless of
      course you want to change sender and/or SMTPHost information).


      The other properties (described below) all have default values, so you
      don't need to set them at all.  If you change the defaults for any of
      these properties and don’t set PersistentSettings to true, the values
      of these properties will revert back to their defaults when the
      component is re-instantiated.


      IMPORTANT NOTE:  If you set this property’s value to true, the user of
      the client application must have appropriate permissions to write
      values to the registry, if the component is run on Windows NT or 2000.
       For this reason, you should be cautious about setting the value to
      true.  In particular, if you are calling vbSendMail from an ASP page,
      DO NOT set the value to true, because the Internet Anonymous user is
      not permitted to write to the registry.


      If this value is set to true and the user does not have permissions to
      write to the registry,  vbSendMail will fail.


EmailAddressValidation


      Public Property Get EmailAddressValidation() As VALIDATE_METHOD
      Public Property Let EmailAddressValidation(ByVal NewValue As
      VALIDATE_METHOD)


      Before sending an e-mail message, the .dll can optionally attempt to
      validate the recipient's e-mail address by checking the syntax of the
      e-mail address. This behavior is set via the EmailAddressValidation
      property, which can be set to one of the following values from the
      VALIDATE_METHOD Enum:


           Public Enum VALIDATE_METHOD
                 VALIDATE_NONE = 0
                 VALIDATE_SYNTAX = 1
           End Enum


      The default is VALIDATE_SYNTAX.  If the e-mail address fails this
      validation test, an error will be raised, and the program will not
      attempt to send the e-mail.  If this property is set to
      VALIDIATE_NONE, and an invalid e-mail address is specified, an error
      may be raised, depending on how the SMTP server validates e-mail
      addresses.  However, this error won't occur until after the program
      attempts to send the e-mail. If an error is not raised, the message
      will be returned to the sender.




SMTPHostValidation


      Public Property Get SMTPHostValidation() As VALIDATE_HOST_METHOD
      Public Property Let SMTPHostValidation(ByVal NewValue As
      VALIDATE_HOST_METHOD)


      Before sending an e-mail message, the .dll can optionally attempt to
      validate the SMTP host specified by checking its syntax, attempting to
      ping it, or resolving the DNS name via DNS lookup. This behavior is
      set via the SMTPHostValidation property, which can be set to one of
      the following values from the VALIDATE_HOST_METHOD Enum:


           Public Enum VALIDATE_HOST_METHOD
               VALIDATE_HOST_NONE = 0
               VALIDATE_HOST_SYNTAX = 1
               VALIDATE_HOST_PING = 2
               VALIDATE_HOST_DNS = 3
           End Enum


      The default is VALIDATE_HOST_DNS.  If the host fails the validation
      test specified, an error will be raised, and the program will not
      attempt to send the e-mail.  If this property is set to
      VALIDIATE_NONE, and an invalid host is specified, an error will be
      raised after the time-out period expires.


      NOTE: If you are sending e-mail via the Internet, setting this
      property to VALIDATE_PING is NOT recommended.  This is because many
      SMTP hosts do not accept pings.  The setting VALIDATE_PING may be
      useful on an Intranet, especially because the host may be on a LAN and
      its naming may not conform to normal IP host syntax rules (for
      instance, the mail server name MAILHOST will be rejected if this
      property is set to VALIDATE_SYNTAX).






ConnectTimeout


      Public Property Get ConnectTimeout() As Long
      Public Property Let ConnectTimeout(ByVal NewValue As Long)


      This property controls how long, in seconds, the program should wait
      for a response after attempting to connect (or sending a request to
      the SMTP server other than the message body) before raising a time out
      error.  The default value is 45, which should be more than enough
      time.  Change this value only if you expect occasional connect time-
      outs and you don't want to keep the user waiting more than 45 seconds.




ConnectRetry




      Public Property Get ConnectRetry() As Long
      Public Property Let ConnectRetry(ByVal NewValue As Long)


      The value of this property determines how many times the component
      should attempt to connect to the SMTPHost if the initial connection
      fails.  The default is 3.






MessageTimeout


      Public Property Get MessageTimeout() As Long
      Public Property Let MessageTimeout(ByVal NewValue As Long)


      This property controls how long, in seconds, the program should wait
      for a response after attempting to send the message body and any
      attachment before raising a time out error.  If this property is not
      set, the program will wait 60 seconds on messages with no attachments,
      or 10 minutes for messages with attachments.  Be careful about setting
      this property if you are planning to send large attachments; if you
      lower it too much, you may get time out errors on these messages.




EncodeType


      Public Property Get EncodeType() As ENCODE_METHOD
      Public Property Let EncodeType(ByVal NewValue As ENCODE_METHOD)


      This property uses the ENCODE_METHOD enum, listed below, to determine
      what type of encoding will be used for file attachments:


           Public Enum ENCODE_METHOD
               MIME_ENCODE = 0
               UU_ENCODE = 1
           End Enum


      The default is MIME_ENCODE. UUEncode should only be used in cases
      where the host that you connect to is not MIME compliant and  cannot
      accept MIME (base 64) encoded files. You should use MIME if possible
      since it is faster, produces smaller code and is DBCS compliant.  In
      addition, if you are formatting your message as HTML (see AsHTML
      property, below) you must use MIME encoding.






UseAuthentication


      Public Property Get UseAuthentication() As Boolean
      Public Property Let UseAuthentication(ByVal NewValue As Boolean)


      Set this value to true if your SMTP mail server requires
      authentication. VERY FEW servers require authentication, so you will
      most likely not need to set this property. If you set it to true for a
      server that does not support authentication, the login process will
      simply time out and the mail session will continue. If your mail host
      does support logins, you will need a valid account on the server to
      use Login Authentication. Note that vbSendMail supports LOGIN
      Authentication only. It does not support other forms of Authentication
      and it does not support encryption.



UsePOPAuthentication


      Public Property Get UsePOPAuthentication() As Boolean
      Public Property Let UsePOPAuthentication(ByVal NewValue As Boolean)


      Set this value to true if your SMTP mail server requires ‘POP First’
      authentication. Some servers (e.g. yahoo.com  & others) require POP3
      authentication before allowing SMTP transactions to occur. You must
      supply a valid POP3Host, SMTPHost, Username, Password, and usually the
      ‘From’ address that matches the login. Related to: POP3Host


UserName


      Public Property Get UserName() As String
      Public Property Let UserName(ByVal NewValue As String)


      If your SMTP server requires authentication, use this property and the
      one below to supply a valid user name and password to the server. This
      Property is used for both SMTP and POP3 authentication.



Password


      Public Property Get Password() As String
      Public Property Let Password(ByVal NewValue As String)

      The password associated with the UserName property. . This Property is
      used for both SMTP and POP3 authentication.







AsHTML


      Public Property Get AsHTML() As Boolean
      Public Property Let AsHTML(ByVal NewValue As Boolean)


      Set this property to true if your message is formatted as HTML text
      and you want the receiving email client to interpret the email as HTML
      instead of plain text.  You must also make sure the message text
      includes valid HTML tags. For example, setting this property to true
      and setting the Message Property to “Hello There” will be interpreted
      as plain text. To send your message as HTML you must set this property
      to true and set the message property to valid HTML, something like:


      <HTML><BODY><B>Hello There</B></BODY></HTML>


      You can embed images, etc. by using the AsHTML Property and the
      Attachment Property together.  When AsHTML is True the Attachment
      Property is used to embed files called out in the HTML code. The
      message text is scanned for file names that match the file names set
      via the Attachment Property.


      In the following example the file smileyface.gif, is  treated as an


            AsHTML = True
           Message =  “<html><body><b>Hello There</b><img
           src=”smileyface.gif”> </body></html>”






ContentBase


      Public Property Get ContentBase() As String
      Public Property Let ContentBase(ByVal NewValue As String)


      When sending HTML formatted messages, the ContentBase allows you to
      specify the 'base' or root location for the links in your message. For
      example, if your web site is http://www.mysite.com, and you set the
      ContentBase to this URL, you can reference images as  <IMG SRC =
      "http://www.mysite.com/images/happyface.gif">. Use this when you want
      to send links to images on a public web site instead of sending the


      Not all email clients support the content base header, so set this
      property at your own risk.





MaxRecipients


      Public Property Get MaxRecipients() As Long
      Public Property Let MaxRecipients (ByVal NewValue As Long)


      The maximum number of recipients allowed before an error is raised.
      SMTP servers are required to support 100 recipients per email. Many
      modern servers will support far more than 100. This property allows
      the user to change the default limit of 100. Care should be exercised
      when changing this value since not all servers will support values
      greater than 100.







METHODS






Send


      Public Sub Send()


      Sends the e-mail message.  Will raise the SendSuccessful event if
      successful.  Will raise the SendFailed event if either 1) the client
      application specifies an invalid SMTP host, sender e-mail address, or
      recipient e-mail address (assuming you don't set EmailHostValidation
      or SMTPHostValidation to VALIDATE_NONE) or 2) The SMTP host responds
      with any kind of error. Please refer to the Usage Notes for an example
      of how this method is used.






Connect


      Public Function Connect() as Boolean


      Optional,  used to open a connection to an SMPT host. Returns True is
      successful, false if not successful.


      The Connect and Disconnect (see below) Methods are useful when you
      need to send bulk mail. There are two ways to initiate mail; 1) using
      the Send Method  and  2) using  Connect-Send-Disconnect Methods. Using
      the Send Method alone performs a Connect and Disconnect automatically
      each time it is called. Calling the Connect Method before the Send
      Method overrides this automatic feature and allows faster processing
      of multiple messages by avoiding the overhead associated with the
      connect/disconnect process. Please refer to the Usage Notes and the
      included BulkMailSample client for examples of how this method is
      used.




Disconnect




      Public Sub Disconnect()


      Optional, used to close a connection to an SMPT host. See the Connect
      Method for a complete description. Please refer to the Usage Notes and
      the included BulkMailSample client for examples of how this method is
      used.




IsValidEmailAddress


      Public Function IsValidEmailAddress(AddressString As String)


      This checks the syntax of an e-mail address and determines if it is
      valid based on a) its syntax, and b) whether the top-level domain name
      it contains (e.g., .com, .net) is valid based on the list published at
      http://www.iana.org/domain-names.html.  Since this list is bound to
      changed over time, you may want to visit this site and update the
      component from time-to-time.


      Note that you don't need to call this function to send an e-mail.  If
      the EmailAddressValidation property is set to VALIDATE_SYNTAX, this
      function is called internally by the component, and if it returns
      false, the message is not sent.  However, the function is exposed
      publicly for your convenience, in case you want to check the e-mail
      address before attempting to send it.






GetIPAddress



      Public Function GetIPAddress(sHostName As String) As String



      Returns the IP Address of sHostName, or an empty string if either 1)
      the client is not or cannot be connected to a TCP/IP network that
      would allow for address resolution, or 2) if sHostName is an invalid
      DNS name.  It is not necessary to use this function to send e-mail; it
      is provided purely as an added enhancement to the component.




GetIPHost




      Public Function GetIPHost() As String



      Returns the local machine's DNS name, or "" if this is unavailable for
      whatever reason.  Not necessary for sending e-mail; provided as an
      added enhancement to the component.






Ping


      Public Function Ping(Address As String, _
                          Optional RoundTripTime As String = "", _
                          Optional DataSize As String = "", _
                          Optional DataMatch As Boolean = False) As Boolean


      Allows you to Ping an IP Address on DNS Host Name.


      Address: Host to ping in dotted quad or domain name format.


      Optional Parameters:  These are all designed to return statistics
      about the Ping, if it was successful.


      -- RoundTripTime: The time in ms for the ping to complete.
      -- DataSize: The size of the data, in bytes, returned by the ping
      -- DataMatch: True if the host returns the same data it was sent,
      false otherwise.


      If you are interested in reading ping statistics, set any or all of
      these parameters to an un-initialized variable and read them back if
      the function returns true.


      Returns:  True if the ping was successful, false otherwise.


      This function is not necessary for sending e-mail.  It is only exposed
      for your convenience.





MXQuery


      Public Function MXQuery(optional IPDomain as string ) As String



      Performs a name server (DNS) search for mail exchange (MX) records for
      the passed IP domain. If blank the IP Domain is assumed to be the home
      domain of  the local host.  If successful, a host name is returned
      that can be used to set the SMTPHost Property. If the lookup fails, a
      null string is returned.  If the local host is part of a sub domain
      and no domain is specified, the search will start at the sub domain
      level and continue up to the root domain until a MX host is found. If
      nothing is found at the root level or a DNS server is not available, a
      null string is returned. Searching foreign domains is permitted unless
      the local host is located behind a firewall. Searching through a
      firewall is not supported.


      Host names returned by the MXQuery function are the names provided by
      the local DNS server. The DNS server may or may not have MX records
      for the closest or ‘best’ SMTP host depending on the network admin’s
      policies. Most networks that operate DNS servers will have the local
      SMTP host identified but there is no requirement that they do so.  For
      instance, the @home network does not (at least in my location)  have
      any MX records for local SMTP hosts. An MXQuery in this situation will
      return the primary  SMTP host at the root domain level (home.com).


      The MXQuery Method may not return a valid SMTP host in all scenarios.
      If your app uses this method it would be prudent to provide an
      alternative method for the user to enter the SMTP host in the event
      the MXQuery Method is not able to resolve a usable host.








EVENTS


The following Events are available only if the vbSendMail component is
declared ‘Withevents’ in your application, e.g. Private WithEvents
poSendMail as vbSendMail.clsSendMail . Your application must supply the
handler routines for these events.



SendSuccesful


      Public Event SendSuccesful()


      When the SMTP hosts responds with a "Mail Received" message, the
      vbSendMail.dll will raise this event.  Reasons to process this event
      include reporting success to the user and logging successful delivery.


           ‘ Example code in your application:
           Private Sub poSendMail_SendSuccesful()


                 ‘ your code here …
                 MsgBox ("Mail Sent OK!”)


           End Sub




SendFailed


      Public Event SendFailed(Explanation As String)


      When the sending of the message fails (whether due to invalid values
      for one of the properties or an error reported by the SMTP server),
      the component will raise this event. The reason for the failure is
      contained in the Explanation parameter. Reasons to process this event
      include reporting failure to the user and logging failed deliveries.


            ‘ Example code in your application:
           Private Sub poSendMail_SendFailed(Explanation As String)


                 ‘ your code here …
                 MsgBox ("Mail Failed!” & vbCrLf & Explanation)


           End Sub







Status


      Public Event Status(Status As String)


      At various points the process of sending mail, the component will
      raise the status event, with the status of the Send (e.g., "Attaching
      File", "Sending Message") indicated by the Status parameter.  If you
      want to trap this event, you can display the status to the user in
      your application's front end.


           ‘ Example code in your application:
           Private Sub poSendMail_Status(Status As String)


                 ‘ your code here …
                 lblStatus.Caption = Status


           End Sub


Progress


      Public Event Progress(PercentComplete As Long)


      The progress event can be used to drive a progress bar or other
      indicator to
      display the current progress of the mail session. The example client
      included with the component uses a simple label control to display a
      percent complete message.


           ‘ Example code in your application:
           Private Sub poSendMail_Progress(lPercentCompete As Long)


                 ‘ your code here …
                 pgBar.Value = lPercentCompete


           End Sub





TROUBLE SHOOTING



Distribution Issues


      The following two files MUST be installed and properly registered on
      any target machine where you intend to run vbSendMail:
           1. vbSendMail.dll
           2. mswinsck.ocx


      If you use the Package and Deployment Wizard to create an installation
      for your target machines, verify that it includes these two files.  If
       not, you must add them manually. As provided, vbSendMail is compiled
      with  VB6.0, Service Pack 4. If your version is different, you may
      need to recompile the dll on your system.





Run time error 429


      If you get the error ”Run time error 429: ActiveX component can't
      create object” when you run your application, the vbSendMail.dll
      either is not installed or not properly registered. Verify that the
      file is installed and manually run regsvr32.exe to register the dll.
      If you get a "LoadLibrary ("vbSendMail.dll") failed” message, check
      for a missing or incorrect version of the mswinsck.ocx.  It has been
      reported that in some rare cases, manually registering the component
      does not resolve this issue. In those cases, building an installation
      package with the Package and Deployment Wizard, has solved the
      problem.



License Error


      If you get an error to the effect that you don't have a license to use
      this component when you try to run a client of the component, you
      should recompile vbSendMail.vbp and register the .dll via regsvr32.








VbSendMail Error Messages


      The following errors might be generated by vbSendMail when attempting
      to set properties or send mail:
            • "Invalid Host Name"
            • "Invalid Remote Port"
            • "Missing or Invalid Recipient E-mail Address"
            • "No Recipient E-mail Address Specified"
            • "Invalid Cc: Recipient E-mail Address"
            • "Invalid Bcc: Recipient E-mail Address"
            • "Missing or Invalid Sender E-mail Address"
            • "Timeout occurred: The SMTP Host did not respond to the
              request"
            • "The file you tried to attach does not exist"
            • "Too many recipients"
            • "Sending HTML requires MIME encoding"




SMTP Server Errors


      vbSendMail will echo errors reported by the SMTP host via the Status
      Event. The SMTP server can send any number of errors that may require
      resolution before you can successfully send mail. If you receive any
      of the following errors, your sever is not configured to accept mail
      from unknown or un-trusted machines. You will need to contact your
      server administrator to resolve these issues (or try a different SMTP
      server).
            • Relaying is prohibited
            • Relaying denied
            • Connection is forcefully rejected


      If you find that you can send mail to recipients within your own
      company but you get errors or bounced mail when sending to addresses
      outside your company,  your SMTP server is not configured to forward
      or relay mail. You will need to contact your system administrator to
      change the server configuration.





Dial Up Networking


      VbSendMail does not explicitly open or close the Windows Dial up
      Networking applet. Windows does this when vbSendMail attempts to open
      a connection to a network resource.





ASP Errors


      VbSendMail causes an error with CreateObject on an ASP page:
      “set poSendMail=server.CreateObject("vbSendMail.clsSendMail").
      Upgrade to version 3.0 or higher. Previous versions are not ASP
      compatible.



What’s Regsvr32.exe ?




   Regsvr32.exe is a Windows component that is used to register other
   components (DLL’s, OCX’s. etc.) so they are available for use by Windows
   applications. When you install an application that includes several
   different DLL/OCX components the installer will normally handle the
   registration for you.  If you are copying files to a new machine you will
   need to perform this registration manually. Regsvr32.exe is normally
   found in the Windows System directory.


   If you are upgrading vbSendMail or installing it for the first time on a
   machine, you will need to register the DLL with regsvr32.exe before your
   application will work.







SMTP Server Configuration Issues



   If you are experiencing problems getting your SMTP server to send mail,
   here are a few things to check:


   Relaying / Transfer Mode – Make sure inbound/outbound transfer is enabled
   for all hosts.


   Accept Connections – Make sure there are no restrictions on SMTP
   connections.


   Client Authentication -  Make sure the server allows your client to
   connect via a supported authentication mode or turn off authentication.


   Mail Routing – Verify SMTP & POP3 routing configuration.


   Routing Restrictions – Make sure there are no SMTP, POP3 or host routing
   restrictions and that anything required for SMTP/POP3 is enabled.





Spam and Mail Bomb Issues


      Some severs have spam settings that can block email sent by
      vbSendMail. These filters are usually set to trigger on the number of
      emails sent over a period of  time, e.g. 30 emails in 10 seconds,
      which vbSendMail can easily do. If you find your server blocking you
      email, look for a ‘spam’ or ‘mail bomb’ setting on the server.




UPDATE HISTORY



    • Original version and updates up to version 1.75 done by
      FreeVBCode.com, except where noted.
    • Updates beginning with version 2.0 done by Dean Dusenbery


Version 3.65 Released 9/05/2003




    • Added MaxRecipients Property
    • Fixed time/date formatting error on certain language settings
    • Changed login authentication code to improve compatibility
    • Removed extra blank line from the beginning of the message body
    • Updated top domain list
    • Other minor bug fixes



Version 3.54 Released 3/23/2002




    • Fixed username/password authentication issue on some servers that
      would timeout waiting for password.
    • Fixed issue with DNS lookup not finding local Domain on some Windows
      XP configurations.
    • Minor correction in documentation.



Version 3.52 Released 1/24/2002


    • Added support for ‘POP first’ servers like Yahoo.com that require POP3
      authentication prior to sending SMTP mail.
    • Added POP3Host and UsePOP3Authentication Properties
    • Fixed bug in MXQuery, thanks to Nick Young for pointing out the issue.
    • Changed Error handling in Send Sub; To, Cc & Bcc must all be null to
      raise a ‘No Recipients’ error.
    • Changed the default Connect Timeout to 30 seconds instead of 10.
    • Updated sample program to demonstrate new features.




Version 3.50 Released 7/21/2001


    • Fixed issue affecting network bandwidth utilization when reading file
      attachments from Netware servers.
    • Fixed time zone offset handling of Daylight vs. Standard time.
    • Fixed ‘Wrong protocol or connection state for the requested
      transaction or request’ error that occurred when the SMTP host
      rejected a malformed email address.
    • Added support for accentuated characters in the From, To, CC & Subject
      headers. Supports both ‘B’ and ‘Q’ encoding. Uses method that yields
      the smallest string size.
    • Added support for sending embedded images within HTML mail. See the
      AsHTML and Attachment Properties for more information.
    • Added support for automatically detecting the SMTP host through name
      server MX lookup. See the SMTPHost Property and the MXQuery Method for
      additional information.


Version 3.04 Released 3/21/2001




      Fixed date formatting problem with non-English systems.


Version 3.03 Released 2/16/2001




    • Fixed a bug in the Ping Sub that occasionally returned the wrong
      remote host address.
    • Changed the time out methodology used in the Send Sub to better
      accommodate sending large attachments via slow connections.




Version 3.02 Released 1/12/2001


   Fixed a small bug that prevented version 3.0 from running on non-
   development machines.



Version 3.0 Released 1/3/2001


   Version 3.0 is binary compatible with previous versions however there are
   some functional differences that may require changes to programs that
   utilize the component.


   Starting with version 2.5, vbSendMail supported any combination of the
   semicolon and comma as delimiters for properties that support multiple
   entries. This release introduces the Delimiter Property that allows
   setting any desired character as the delimiter character (the default is
   the semicolon), however only a single delimiter character is supported.
   If your code relied on the components ability to use either of two
   delimiters at the same time, you will need to make the appropriate
   changes to your code.


   The new Connect and Disconnect Methods enhance the functionality of the
   Send Method.   While you can use the Send method as before, you  may want
   to take advantage of the increased performance available using the
   Connect & Disconnect methods when sending a large number of messages. The
   performance increase will depend on your particular setup and varies
   significantly depending on the speed of your connection and the size of
   the email but  the performance increase is typically in the range of 50%
   to 100%. Your results may vary.

      Bug fixes:
      • Fixed minor time/date formatting problem that was incompatible with
        some email clients including Eudora Light.
      • Fixed a bug that prevented the component from working correctly
        with ASP


      Additions / enhancements:
      • Added Connect Method.
      • Added Disconnect Method.
      • Added the Delimiter Property.
      • Added the Priority Property.
      • Added the Receipt Property.
      • Added a client example project demonstrating the Connect and
        Disconnect methods.
      • Rearranged the internal program layout.
      • Efficiency improvements resulting in smaller, faster code.





Version 2.71 Released 09/04/2000


      • Added support for blind (Bcc) recipients.





Version 2.70 Released 08/05/00


      • New base 64 encoder that is double byte character set (DBCS)
        compliant.  This fixes a bug that caused file attachment corruption
        on Chinese and other DBCS OS's.
      • The file attachment encoder is nearly twice as fast as the previous
        version.
      • The MIME Content-Type parameter is now read from the system
        registry for each attached file. This resolves issues with some
        email clients (Yahoo for one) not properly displaying attached



Version 2.61 Released 06/12/00


      • Minor bug fixes
      • ASCII value limitation of 1 to 127 no longer enforced; replaced by
        intelligent support for 8-bit ASCII.

Version 2.6 Released 06/04/00


      • Added AsHMTL and ContentBase properties.
      •  Added Improved Error Handling, and different error handling
        depending on whether the component is running in the IDE or not.



Version 2.5 Released 5/31/00

      Bug Fixes:
      • A MIME formatting error that caused each attachment to be displayed
        within another "Untitled Attachment" on some systems has been
        corrected.
      • A bug whereby the component didn't properly unload on some systems
        has been corrected.
      • The mail formatter now enforces an ASCII value limitation of 1 to
        127.

      Additions / enhancements:
      • Added the following properties, methods, and events.  See above for
        description.


               EncodeType
               Username as String
               Password as String
               UseAuthentication
               Progress


      • Various speed improvements, now 10x faster at sending attachments
        than original v1.x (on a Lan connection, your mileage may vary).
      • Added support for both comma and semicolon delimiters for all
        properties that support multiple inputs.





Version 2.0 Released 04/18/00


A major upgrade, requiring the breaking of Binary Compatibility. Below are
some of the more salient features of this upgrade:

      Bug Fixes:
      • Attachment file size is now correct, was 1 to 2 characters too long
      • Mail message body is now properly formatted per RFC 821, see
        FormatMail Sub for details
      • Bug whereby the component would fail if a client form is unloaded
        then reloaded is  fixed.
      • A QUIT message is now sent to the SMTP host after each e-mail, per
        RFC 821.
      • Name changed from SendMail.dll to vbSendMail.dll, in order to avoid
        a conflict with a Microsoft component included with Internet
        Explorer

      Additions / enhancements:


      • The following properties/methods were added or publicly exposed:


            CCRecipient
            CCDisplayName
            PersistentSettings
            ConnectRetry
            IsValidEmailAddress
            GetIPAddress
            GetIPHost
            Ping




      • Sending attachments is 25% to 300% faster depending on your
        connection speed
      • Executable is 12K smaller
      • Support for multiple recipients & recipient names added
      • Support for multiple 'Cc:' recipients & names added



Version 1.75 Released 03/20/00


      Support for Multiple File Attachments added by Lance Petersen (see
      Credits, above).



Version 1.6.1 Released 03/09/00


      Fixed a small bug in the EncodeandSendFile method.  You would had only
      run across this bug if your application had a file open at the time
      you are trying to attach a file.  Also tightened version control by
      actually marking the .dll's version (Previously, if you looked at
      version 1.6's version in the file's properties, it would have shown
      1.0).


Version 1.6: Released 12/12/1999


      Bug Fixes:
      • Large file attachments no longer fail, as long as MessageTimeout
        property is set to an appropriately large value.
      • Bug whereby an incorrect time stamp was added to messages has been
        fixed.


      Additions/Enhancements:
      • ConnectTimeout property added
      • MessageTimeout property added
      • EmailAddressValidation property added.
      • SMTPHostValidation property added.


Version 1.5: Released 10/25/1999.

      Upgraded to support file attachments







Version 1.0: Released 9/8/1999







KNOWN ISSUES


1. If you are upgrading this program from a previous version, use regsvr32
   to register the .dll.  This resolves various issues that may occur due to
   the upgrade.

2. In some instances, you may need to recompile as well as re-register.  In
   particular, if you get an error to the effect that you don't have a
   license to use this component when you try to run a client of the
   component, you should recompile vbSendMail.vbp and register the .dll via
   regsvr32.

3. Requires the mswinsck.ocx file.

4. The automatic SMTP host look up through DNS (MXQuery) may not work for
   all versions of Windows and will not work if your ISP does not use MX
   records to identify its mail server (rare).  It has been successfully
   tested with Windows  XP, Windows 2000, Windows NT 4.0, Windows ME and
   Windows 98SE. It may or may not work with the various versions of Windows
   95 depending on the version and how the IP protocol is configured.  It is
   highly recommended that applications provide a backup method for the user
   to enter the SMTP host information in the event that MXQuery is unable to
   resolve a host.



