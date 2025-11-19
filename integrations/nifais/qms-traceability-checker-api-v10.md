---
title: "Qms Traceability Checker Api V1.0"
source: "QMS_Traceability_Checker_API_v1.0.pdf"
tags: [Export Assembly Centre (EAC) Operations]
version: "1.0"
last_updated: "2025-11-17"
short_description: "QMS Traceability Checker API V.1.0 Endpoint The following endpoints are available: Test https://api.test.scoteid.co..."
long_description: "QMS Traceability Checker API V.1.0"
---

QMS Traceability Checker API
V.1.0

Endpoint
The following endpoints are available:


Test                              https://api.test.scoteid.com/traceability/qms/members.json

Production                        https://api.scoteid.com/traceability/qms/members.json



Authentication
Authentication is via HTTP basic auth header containing ScotEID username and password
(same as existing ScotEID SOAP webservices) for the appropriate environment (e.g. test,
production)



JSON Schema
The JSON Schema defining the response format is downloadable from
https://api.test.scoteid.com/traceability/qms/schema.json



Sample Request
An empty POST request can be submitted to the endpoint above which will return the entire
member / history dataset.

Alternatively an individual member can be queried by submitting a query as a JSON request,
structured as shown in the following example:

{
​       "query": {
​       ​      "membershipNumber": "00010"
​       ​      "postcode": "AB1 2FB",
​       ​      "cph": "66/001/0001"
​       }
}


One of “membershipNumber”, “postcode” and “cph” can be populated. May return multiple
results if multiple members have supplied the same CPH.
Sample Response
{
    "members": [
      {
        "membershipNumber": "000010",
        "businessName": "J BLOGGS & SONS",
        "address1": "Home Farm",
        "address2": "Region - County",
        "postcode": "AB1 2FB",

            "dateJoined": "1991-05-08",
            "dateAssessed": "2025-03-02",

            "status": "J",

            "holdings": [

                /* Primary Holding */
                {
                   "cph": "65/001/1234",
                   "is_primary": true,
                   "statuses": [
                     {
                       "date_in": "1991-05-08",
                       "status": "J"
                     }
                   ]
                },

                /* Additional Holding */
                {
                  "cph": "65/001/1235",
                  "statuses": [
                    {
                       "date_in": "1991-05-08",
                       "date_out": "2025-04-01", /* Starts out Beef & Lamb */
                       "status": "J"
                    },
                    {
                       "date_in": "2025-04-01",
                       "status": "L" /* Now Lamb Only */
                    }
                  ]
                }

            ]
        }

    ]
}




Response Data
Each member in the response contains the following:
membershipNumber           Membership number formatted as 6 digits

businessName               Business name

address1                   First line of address

address2                   Remainder of the address, may be multiple lines separated by a “-”
                           character

postcode                   Postcode

dateJoined                 Date the member first joined

dateAssessed               Last assessed date

status                     The current status of the member:
                           B - Beef
                           L - Lamb
                           J - Joint (Beef + Lamb)
                           O - Out

holdings                   Holdings / status history



   Each holding element contains the following:


cph                 CPH Number formatted CC/PPP/HHHH

is_primary          Is this the members primary holding?

statuses            List of statuses, each status contains:


                     date_in                                   Date the holding became assured

                     date_out                                  Date the holding went out (may not be
                                                               present if still assured)

                     status                                    The status of the member/holding for
                                                               this period (may be B, L or J as
                                                               above)
