---
title: "Eac Table Notes"
source: "EAC - table notes.txt"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Main tables and fields are: TABLE eaccollections: This table holds the collections that have been set up, the current collection should be the lat..."
long_description: "TABLE eaccollections: This table holds the collections that have been set up, the current collection should be the latest record in here and the EACOpen field would be set to Y"
---

Main tables and fields are:

TABLE eaccollections:
This table holds the collections that have been set up, the current collection should be the latest record in here and the EACOpen field
would be set to Y

EACID will be the number of the collection.

TABLE eidmarketmovements:
Like the UK software, this table holds the actual tag information. 

The Saledate field will be the date of the collection.
The Saleno will be the number of the collection.
PenNo is the number of the batch this tag is in.
MS2NO is the (inward) permit number this tag is on
OffPermitNo is the (outward) permit number if this tag/animal is then moved out of the collection.






