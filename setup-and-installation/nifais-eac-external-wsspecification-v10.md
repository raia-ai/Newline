---
title: "Nifais Eac External Wsspecification V1.0"
source: "NIFAIS_EAC_External_WSSpecification_v1.0.docx"
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

This document describes the web services to be exposed by NIFAIS to external Export Collection Centres.

The NIFAIS API is a REST (Representational State Transfer) interface. The API consists of resource URLs that use built-in HTTP verbs and response codes.

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

EAC Services

Request Movement Documents

Movements

Sheep EAC EID Batch

EID Retrieve Data

Flock List

Unconfirmed Documents

Request Movement Documents

This Web Service will allow an external EAC operator to request new movement documents.

Movements

This Web Service will allow an external EAC to record movements into the EAC.

The web service will also allow the EAC to record movements out of the EAC.  These moves are for animals that were not exported and can be to an ordinary animal group or lairage.

Sheep EAC EID Batch

The webservice will be used to manage the batching of animals in a current active assembly in an EAC.

The web service will operate in one of three modes:

BATCH: Will allow EIDs to be assigned to a batch

CLEAR: Will allow all or specified EIDs to be removed from a batch

SEARCH: Will retrieve a list of EIDs assigned to a specified batch and a list of other EIDs that are currently resident in EAC.

Note:

It will only be possible to manage batches in a EAC with a current active assembly.

It will only be possible to add\remove EIDs to\from a batch while the batch remains in the EAC.  Once the batch is confirmed as exported no further amendments will be possible.

It will only be possible to add\remove EIDs that are currently resident in the EAC.  If an EID is invalid it will not be added\removed

EID Retrieve Data

This webservice will be used by external EACs to retrieve the data used to populate the various drop downs on their front-end application.

The data retrieved will include:

A list of age classifications for OVN/CAP

A list of breeds for OVN/CAP

A list of types of trade for OVN/CAP

Flock List

This webservice will be used by external EACs to retrieve a list of EIDs currently residing in the EAC.

Inpu

t A

Unconfirmed Documents

This web service will be used by externals EACs to retrieve a list of G documents which correspond to intentions to moves to the EAC which have not yet been used to move animals into the EAC.

Input AGN Object