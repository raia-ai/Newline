---
title: "Bill Chq Tpl Fields"
source: "BILL CHQ TPL FIELDS.doc"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "INVOICES PageHeader (PutPageHeaderToBuffer) Details (GetFieldValueThatsNotInGrid) Figures (GenerateBottomLineInBuffer) PAGE HEADER: \"NameAddr\" ..."
long_description: "PageHeader (PutPageHeaderToBuffer) Details (GetFieldValueThatsNotInGrid) Figures (GenerateBottomLineInBuffer)"
---




INVOICES

PageHeader (PutPageHeaderToBuffer)
Details (GetFieldValueThatsNotInGrid)
Figures (GenerateBottomLineInBuffer)

PAGE HEADER:

"NameAddr"

"AccNo"

"Paddle"

"SaleAt"

"Date"

"ItemType"

"ItemNo"

"ItemDate"

"FANo"

"VATMessage"

"Luck"

"HerdNo"

"FlockNo"

"Agent"

"Comments"

"CustVatNo"

"MarkHoldNo"

"MarkVatNo"

"LotHeader"





LOT DETAILS:



"FANo"

"Vendor"

"NewLotDesc"

"LotNo", "Lot"

"LotQty", "Qty"

"Price"

"Amount"





BOTTOM LINE:



"Gross"

"GoodsVAT"

"Charges"

"ChargesVAT"

"Net"

"Paid"

"PaidDebts"

"SectAverages"

"SectCounts"

"InHoNumber"

"InHaulierNo"

"InHoAddr"

"InHaulier"

"TotalDue"

"Payments"

"PayTypeDisOrCharge"

"PayDis"

"InvMessage"

"MoveMessage"



CHEQUES

HEADER:

"NameAddr"

"AccNo"

"Paddle"

"SaleAt"

"Date"

"ItemType"

"ItemNo"

"ItemDate"

"CustVatNo"

"FANo"

"VATMessage"

"CustInfo"

"BACSNote"

"BACSDate"

"HerdNo"

"FlockNo"

"LotHeader"



LOT DETAILS:

"FANo"

"Purchaser"

"D.O.B."      <-   superceded by the NewLotDesc field

"LotQty", "Qty"

"NewLotDesc"

"Price"

"Amount", "Total"

"LotNo", "Lot"







BOTTOM LINE:



"Gross"

"GrossExVat"

"IRSubTotal"

"GoodsVAT"

"Charges"

"VatableCharges"

"NonVatableCharges"

"ChargesVAT"

"IRVat"

"IRExtraVat"

"Contra"

"Cash"

"Net"

"Paid"

"SectAverages"

"InHoNumber"

"InHoAddr"

"ChqMessage"

"MoveMessage"

"BACSNote"

"BACSDate"



"VATMessage"









CHEQUE STUB:



"ChequeDate"

"ChequeDateLong"

"ChequeNo"

"ChequeName"

"ChequeNameAdd"

"ChequeAmt"

"ChequeAmtWords"

"AmtHT"

"AmtTT"

"AmtThousands"

"AmtHundreds"

"AmtTens"

"AmtUnits"

"ChequeAmtSentence"

"ChequeAuth"



- Added new template field "ContraDetail" to the cheque template, which
prints detail of which debts the contra pays off.

 - Added new template field "ContraBalance" to the cheque template, which
will print the customer's outstanding balance if a contra has taken the
cheque total to zero.


