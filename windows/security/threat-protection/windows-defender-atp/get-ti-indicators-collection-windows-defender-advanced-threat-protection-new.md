---
title: List TiIndicators API
description: Use this API to create calls related to get TiIndicators collection
keywords: apis, public api, supported apis, TiIndicators collection
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance 
ms.topic: article
ms.date: 12/08/2017
---

# List TiIndicators API

[!include[Prerelease information](prerelease.md)]

>[!Note]
> Currently this API is supported only for AppOnly context requests. (See [Get access without a user](exposed-apis-create-app-webapp.md) for more information)


**Applies to:**

- Windows Defender Advanced Threat Protection (Windows Defender ATP)

 Gets collection of TI Indicators.
 Get TI Indicators collection API supports [OData V4 queries](https://www.odata.org/documentation/).

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Use Windows Defender ATP APIs](apis-intro.md)

Permission type |	Permission	|	Permission display name
:---|:---|:---
Application |	Ti.ReadWrite |	'Read and write TI Indicators'


## HTTP request
```
GET https://api.securitycenter.windows.com/api/tiindicators
```

[!include[Improve request performance](improverequestperformance-new.md)]

## Request headers

Name | Type | Description
:---|:---|:---
Authorization | String | Bearer {token}. **Required**.


## Request body
Empty

## Response
If successful, this method returns 200, Ok response code with a collection of [TI Indicator](ti-indicator-windows-defender-advanced-threat-protection-new.md) entities.

>[!Note]
> The response will only include TI Indicators that submitted by the calling Application. 


## Example

**Request**

Here is an example of a request that gets all TI Indicators

```
GET https://api.securitycenter.windows.com/api/tiindicators
```

**Response**

Here is an example of the response.

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.windows.com/api/$metadata#TiIndicators",
    "value": [
        {
            "indicator": "12.13.14.15",
            "indicatorType": "IpAddress",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T11:15:35.3688259Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "action": "AlertAndBlock",
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "test"
        },
        {
            "indicator": "220e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "action": "AlertAndBlock",
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST"
        }
    ]
}
```
