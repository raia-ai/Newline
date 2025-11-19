---
title: "Govservices Debugging Query"
source: "GovServices debugging query.txt"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "select * FROM govservicesrequests LEFT JOIN govservicesrequestdata ON govservicesrequests.requestid=govservicesrequestdata.requestid LEFT JO..."
long_description: "select * FROM govservicesrequests LEFT JOIN govservicesrequestdata ON govservicesrequests.requestid=govservicesrequestdata.requestid LEFT JOIN govservicesresults ON govservicesrequests.requestid=govservicesresults.requestid LEFT JOIN govservicesresultdata ON govservicesresults.resultid=govservicesresultdata.resultid order by requesttimestamp desc"
---

select * FROM govservicesrequests 
  LEFT JOIN govservicesrequestdata ON govservicesrequests.requestid=govservicesrequestdata.requestid  
  LEFT JOIN govservicesresults ON govservicesrequests.requestid=govservicesresults.requestid
  LEFT JOIN govservicesresultdata ON govservicesresults.resultid=govservicesresultdata.resultid
order by requesttimestamp desc 



key fields for debugging will be "externalrequest" and "externalresponse"