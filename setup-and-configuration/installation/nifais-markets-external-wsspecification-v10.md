---
title: "Nifais Markets External Wsspecification V1.0"
source: "NIFAIS_Markets_External_WSSpecification_v1.0.docx"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "DOCUMENT CONTROL Confidentiality Title, copyright and all other propriety rights in this document shall remain vested in Capita PLC"
long_description: "Title, copyright and all other propriety rights in this document shall remain vested in Capita PLC. This document shall however be considered to be Documentation as defined in the Northern Ireland Farm Animal Information System (NIFAIS) contract made between the Department of Agriculture, Environment and Rural Affairs (DAERA), the Authority and AMT-Sybex, dated 21 April 2016 (the “Contract”)."
---

DOCUMENT CONTROL

Confidentiality

Title, copyright and all other propriety rights in this document shall remain vested in Capita PLC.  This document shall however be considered to be Documentation as defined in the Northern Ireland Farm Animal Information System (NIFAIS) contract made between the Department of Agriculture, Environment and Rural Affairs (DAERA), the Authority and AMT-Sybex, dated 21 April 2016 (the “Contract”).

In August 2021 the Authority, Capita Business Services Limited and AMT-Sybex Limited entered into a Deed of Novation in order to novate the Original Agreement from AMT-Sybex Limited to Capita Business Services Limited.

Capita PLC therefore hereby grants to DAERA, a licence to use this document in accordance with the terms of the Contract. This document shall also be considered to be Confidential Information as defined in the Contract and DAERA shall comply with its obligations under the Contract in this regard.

Change Control

This document is the responsibility of the Project Leader.  It is subject to formal change control after the initial approved release (i.e. issue no. 1.0).  Changes must be recorded in the Historical Reference Section.

Historical Reference

Introduction

This document describes the web services to be exposed by NIFAIS to external market providers.

The NIFAIS Market API is a REST (Representational State Transfer) interface. The API consists of resource URLs that use built-in HTTP verbs and response codes.

Requests

The API will use HTTP Verbs depending on the type of request.

GET – To retrieve a resource or a collection of resources

POST – To create or modify a resource

GET requests use URL parameters to encode specific data inputs. POST requests include JSON payloads in specific formats. Mandatory input fields are indicated throughout this specification with *.

Responses

Responses are returned in JSON format. This response may be a single JSON object or a JSON array depending on the request.

The API uses standard HTTP status codes to indicate the success, or otherwise, of the request:

	200 OK – Request Succeeded

	400 Bad Request – Could not parse request

	401 Unauthorized – Authentication Failed

	403 Forbidden – Authenticated user not authorised

	404 Not Found – Resource not found

	50X – An internal server error occurred

API Authentication

Third party user login credentials will be authenticated via Government Gateway or NIDA.

The process for logging in will involve the user being redirected in their browser to an agreed website and logging in there. Once they log in successfully they will be able to retrieve the JSON Web Token (JWT) from the response and add it as a Bearer Token in the header of all subsequent requests to the NIFAIS Web Services.

TECHNICAL SPECIFICATION DETAILS

Market Moves Service

– Moves In

– Moves Out

– Document Request

– Sheep EID Check

– End of Day Market Status

Market Movements (In and Out)

This web service will allow an OVN/CAP Market to record a movement into or out of the Market.

Document Request

This Web Service will allow an OVN/CAP Market to request new movement documents.

EID Check

This Web Service will allow a market to check the validity of a move to market before an attempt is made to record the move.

The web service will accept any combination of the following:

Eid list

Movement document number

Animal group number

Any problems that are identified e.g. movement restrictions will be detailed in the web service output.

In addition, the web service will return pertinent information related to the movement and any associated eids.

Reconciliation Check

This Web Service will return market reconciliation data for a specified date.

Two types of reconciliation data may be requested based on specified input:

Appendix A

Example input Payloads

Market Movements In Submit Mode

Using an F document

{

"businessId": 6015,

"operationMode":"submit",

"requestType": "MarketIn",

"movement": {

"fromGroup": {

"animalGroupNumber": "890008"

},

"toGroup": {

"animalGroupNumber": "M06BG"

},

"moveDate": "2024-07-18",

"movementList": [

{

"type": "Goats",

"eids": [

{

"eid": "UK 1779007 00101"

}

],

"lotNumber": "10"

}

],

"comment": "",

"haulierDetails": {

"vehicleReg": "ABC 1234",

"transportName": "transport Name",

"meansTransport": "Truck",

"transportPermit": "PERMIT123"

},

"sellersDocumentNumber": "F000000001"

}

}

Using an A document

{

"businessId": 30000,

"operationMode":"submit",

"requestType": "MarketIn",

"movement": {

"fromGroup": {

"animalGroupNumber": "078957"

},

"toGroup": {

"animalGroupNumber": "M01GS"

},

"moveDate": "2024-07-18",

"movementList": [

{

"type": "Rams",

"eids": [

{

"eid": "UK 1779007 00026"

}

],

"lotNumber": "1"

}

],

"moveType": "M",

"haulierDetails": {

"vehicleReg":"ABC1234",

"transportName": "Transporter Name ",

"meansTransport": "truck",

"transportPermit":"PERMIT123"

},

"sellersDin": "",

"sellersDocumentNumber": "A000001001"

}

}

Market Movements In Edit Mode

{

"businessId": 6015,

"operationMode":"edit",

"requestType": "MarketIn",

"movement": {

"fromGroup": {

"animalGroupNumber": "890008"

},

"toGroup": {

"animalGroupNumber": "M06BG"

},

"moveDate": "2024-07-18",

"movementList": [

{

"type": "Goats",

"eids": [

{

"eid": "UK 1779007 00102"

}

],

"lotNumber": "11"

}

],

"comment": "",

"haulierDetails": {

"vehicleReg": "ABC1234",

"transportName": "Transporter name",

"meansTransport": " EDIT Truck",

"transportPermit": "PERMIT123"

},

"sellersDocumentNumber": "F000000001"

}

}

Market Movements Out Submit Mode

G Dococument out to Farm

{

"businessId": 100300,

"operationMode": "submit",

"requestType": "MarketOut",

"movement": {

"fromGroup": {

"animalGroupNumber": "M06BG"

},

"toGroup": {

"animalGroupNumber": "890009"

},

"moveDate": "2024-07-17",

"sellersDocumentNumber": "G000000051",

"movementList": [

{

"type": "Goats",

"eids": [

{

"eid": "UK 1779007 00101"

“replacement”: "UK 111111 00101"

}

],

"lotNumber": "10"

}

],

"comment": "Comment ",

"haulierDetails": {

"vehicleReg": "ABC 1234",

"transportName": "transporter name",

"meansTransport": "Truck",

"transportPermit": "PERMIT123"

}

}

}

G dococument : out to Abattoir:

{

"businessId": 100300,

"operationMode":"submit",

"requestType": "MarketOut",

"movement": {

"fromGroup": {

"animalGroupNumber": "M06BG"

},

"toGroup": {

"animalGroupNumber": "08100G"

},

"moveDate": "2024-07-17",

"sellersDocumentNumber": "G000000051",

"movementList": [

{

"type": "Goats",

"eids": [

{

"eid": "UK 1779007 00101"

}

],

"lotNumber": "10"

}

],

"comment": "Comment ",

"haulierDetails": {

"vehicleReg":"ABC1223",

"transportName": "transporter name",

"meansTransport": "Truck",

"transportPermit":"PERMIT123"

}

}

}

G dococument : out to SCC

{

"businessId": 100300,

"operationMode": "submit",

"requestType": "MarketOut",

"movement": {

"fromGroup": {

"animalGroupNumber": "M06BG"

},

"toGroup": {

"animalGroupNumber": "890009"

},

"moveDate": "2024-07-16",

"sellersDocumentNumber": "G000000051",

"movementList": [

{

"type": "Goats",

"eids": [

{

"eid": "UK 1779007 00101"

}

],

"lotNumber": "10"

}

],

"comment": "Comment ",

"haulierDetails": {

"vehicleReg": "ABC 1234",

"transportName": "Transporter Name",

"meansTransport": "Truck",

"transportPermit": "PERMIT123"

}

}

}

G dococument : out to EAC

{

"businessId": 100300,

"operationMode": "submit",

"requestType": "MarketOut",

"movement": {

"fromGroup": {

"animalGroupNumber": "M06BG"

},

"exportDetails": {

"eac": "890009",

"country": "BELGIUM",

"typeOfTrade": "DIRECT SLAUGHTER"

},

"moveDate": "2024-07-16",

"sellersDocumentNumber": "G000000051",

"movementList": [

{

"type": "Goats",

"eids": [

{

"eid": "UK 1779007 00101"

}

],

"lotNumber": "10"

}

],

"comment": "Comment ",

"haulierDetails": {

"vehicleReg": "ABC 1234",

"transportName": "transport name",

"meansTransport": "Truck",

"transportPermit": "PERMIT123"

}

}

}