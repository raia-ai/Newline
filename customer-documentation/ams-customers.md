---
title: "Ams Customers"
source: "AMS Customers.docx"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "AMS Setups for NAS customers: Halls (marketno 82): Halls show vatable items with a v next to them and margin items appear as blank"
long_description: "Halls show vatable items with a v next to them and margin items appear as blank. They do not have a note on the invoice about margin items."
---

AMS Setups for NAS customers:

Halls (marketno 82):

Halls show vatable items with a v next to them and margin items appear as blank. They do not have a note on the invoice about margin items.

Seller Side

No lots marked with VAT flag.

No mention of AMS in sysinfo.

PUGH

Pugh show margin items with an m next to them and not it in the note at the bottom of the invoice.

Not sure why I shown here (but note date could be old error?)

They appear to show vat items with a v.

GATEWAY

Gateway show zero rated with z, but not sure what triggers this? There is no country code against this customer. Think this involves itemtype set as N VAT rather than C for check seller.

They show for export with an e. What triggers this? Think it is the country code.

CHEFFINS

Is VB vendors BACS?

Cheffins shows margin items with an m, vat items with a v and zero rated with a z.

CODE:

Public Function GetTrxVatStatus(trx As TransactionType, hf As HeadFileType, custDataPath As String, markEntry As MarkNameFileEntryType) As String

Dim he As HeadFileSectionEntryType

he = GetHeadEntryFromXType(trx.Xtype, hf)

Select Case AMSSystemNo

Case "100"

GetTrxVatStatus = gtvs_Cheffins(trx, he, custDataPath, markEntry)

Case "111"

GetTrxVatStatus = gtvs_Gateway(trx, he, custDataPath, markEntry)

Case Else

GetTrxVatStatus = gtvs_Standard(trx, he, custDataPath, markEntry)

End Select

gtvs_Standard

If MarkNameEntry.AMSMarket = "Y" Then

' ams market

If venRec.AMSVendor = "Y" Then

' this lot should be under the AMS

If he.Vatable = "Y" Or (he.Vatable = "C" And Not Trim$(venBackRec.VatReg) = "") Then

' standard rate..

gtvs_Standard = "m"

ElseIf he.Vatable = "N" Then

gtvs_Standard = "n"

ElseIf he.Vatable = "I" Then

gtvs_Standard = "i"

End If

Else

' vendor not under AMS

If he.Vatable = "Y" Or (he.Vatable = "C" And Not Trim$(venBackRec.VatReg) = "") Then

' standard rate..

gtvs_Standard = "v"

ElseIf he.Vatable = "N" Then

gtvs_Standard = " "

ElseIf he.Vatable = "I" Then

gtvs_Standard = "i"

End If

End If

How do I setup AMS to trigger this standard?