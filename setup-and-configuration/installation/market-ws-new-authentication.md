---
title: "Market Ws New Authentication"
source: "MARKET WS - New Authentication.docx"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Market Authentication Document information Document details Distribution Revision history Sign off Glossary Scope This document will explai..."
long_description: "This document will explain how Markets can register with Government Gateway and DAERA Online Services. It will give some technical advice on how to integrate the Market software with the new process and explain what Markets will need to have ready to test the new NIFAIS web services."
---

Market Authentication

Document information

Document details

Distribution

Revision history

Sign off

Glossary

Scope

This document will explain how Markets can register with Government Gateway and DAERA Online Services.  It will give some technical advice on how to integrate the Market software with the new process and explain what Markets will need to have ready to test the new NIFAIS web services.

Authentication Process

Background

The process for logging into Government Gateway will involve the user being redirected in their browser to the Government Gateway website and logging in there. Once they log in successfully, they will be able to retrieve the JSON Web Token (JWT) from the response and add it as a Bearer Token in the header of all subsequent requests to the NIFAIS WebServices.

Pre-Requisites

To facilitate authentication each Market will need to provide an application name and a fully qualified return URL address for us to redirect the browser to after authentication. This URL will act as a landing page on the Market web application. This may be different for the test and Production environments.

To allow DAERA to set this up please email NIFAISComms@daera-ni.gov.uk with the following details for your application.

See below example.

Each Market will also need to assign an administrator whose details will be added to the DAERA Customer database and associated to the appropriate Market organisation. Once completed the Admin can then register for a Government Gateway account.

This will allow the admin user to register for a new Government gateway account that can then be linked to the Market Organisation they are representing. This link can be created by the admin on first logging into DAERA Online Services. If the admin is linked to only one Organisation then the process is automatic.

The admin user can also then create multiple accounts via the Government Gateway web site for other employees in the Market organisation. Their accounts can also be used to log in and use the NIFAIS Web Services as the Market Organisation. DAERA do not need to know any details about the “other” employees.

Implementation

To authenticate users the Market Web Application will need to redirect the user to a URL. This URL will be specific to each third party and contain the application name that the Market provided to DAERA. 

Example: https://pptref.daera-ni.gov.uk/AuthWeb/auth/login/MarketOne/

This URL redirect will allow the user to choose a preferred Authentication provider. All third-party users of the NIFAIS Web Services are currently using Government Gateway and should continue to do so as they represent a Market Organisation. The NIFAIS Web Services will only accept a Government Gateway token.

The User will then be redirected back to the URL that the Market has specified. The Market will also be presented with a JWT and can be accessed from the form data in the response.

var token = request.Form[TOKEN];

Example Token
token:

eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2IiwidHlwIjoiSldUIn0..LqpV-cybQvd-lWrrMWGUmw.fhbA_BODQIzFVXSSqgAJcLnpR9NWosLIN3KtHKzSHvXTZvD6UXrUqM0zPbp0hsvMJcSl0Cbn-eFj1DJ5ymnOViMEWakQqjotcLjOER5URBZ8fL96kNMX6dMMZHd6juLSpjvxAQzelrmCT_fird2BHHbhTjnEopWYPUWEFqgk2DXNYppcCoctDYCyLfX9gBvFbA5N3uJhaxbBwpxuZ2euxE_HHgigecunGF752eUwRxEvzxa9HHt_A1OximNXaL2IxR-sVA8WmYLTWM6sQwWn84QLfPGu-dcdrONPtyKyYraShcxrtz9BcD1HzfXGYgMEGVeOq0qLWhao5qJ57EeyZIrt2J9mdQXQwhFRmCNb8OR7rG3baAWrC6deZU7B0PWg2A_mNEfbqqMeWtIq-SNKAgyLx6SbEsLKlpCsTTCc-w0r-ckrtI_uE9nNC4bIvgPiwQ7DiTU5N7hP5ouuMZLdogacF9FlHh93vvj29ywJ78d-O5Ckce_kcv92YN4INVXm_weouXk4Skzb3Cz0woMfiTRR1E7uFudGP23rNNrzmqtCWzvy8xxPrUzXTRLs-UirpuypYj_aiXwXBQ0F4eRyBzZ1IiExl7owAClTLXplntrkqlFMetv-iIkXC0JC-PcZ7xHfp0Dc-giJZqUNtfHIcv-_545qWwz5ado58azWUtxLEwhwa5ng3_j_cKdpsmypei6RaXl4GWkHBDDxkliMmjcbV7dhpqIsbK8QP5UV6BONMI0gk76x1MVPYruAQBE0-l1EnyN-GUlrVbqdVNgAsLPm2AxEbmQFongweNo9xLD2kFvoLQtZVr0m5I6zrcNvVKc6V6wGeECjoSJ9X1I.NNTH2-2iz7ZLNFc46ESKHA

This token should then be added as a Bearer Token to each subsequent request to an NIFAIS Web Service - see example code below.

HttpClient client = new HttpClient();

client.DefaultRequestHeaders.Accept.Clear();

client.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue("Bearer", token);

Refresh Tokens

In the event that a Token expires then there is an option for the client application to get a refresh token. When a token is expired the NIFAIS application will return a 419 response and include a “RefreshId” in the response content. The Client application should extract that “refreshId” and send it through to the Refresh API call.

Note: the token will expire after 60 minutes. The refresh can be used for each token up to a maximum of 24 times before a new token needs to be generated by logging in again.

Pre-Production: https://pptref.dardni.gov.uk/AuthWeb/api/token/GetRefreshById/{refreshID}