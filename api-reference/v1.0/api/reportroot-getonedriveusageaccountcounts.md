---
title: "reportRoot: getOneDriveUsageAccountCounts"
description: "Get the trend in the number of active OneDrive for Business sites. Any site on which users viewed, modified, uploaded, downloaded, shared, or synced files is considered an active site."
ms.localizationpriority: medium
ms.prod: "reports"
author: "sarahwxy"
doc_type: apiPageType
---

# reportRoot: getOneDriveUsageAccountCounts

Namespace: microsoft.graph

Get the trend in the number of active OneDrive for Business sites. Any site on which users viewed, modified, uploaded, downloaded, shared, or synced files is considered an active site.

> **Note:** For details about different report views and names, see [Microsoft 365 reports - OneDrive for Business usage](https://support.office.com/client/OneDrive-for-Business-usage-0de3b312-c4e8-4e4b-a02d-32b2f726a680).

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
| :------------------------------------- | :--------------------------------------- |
| Delegated (work or school account)     | Reports.Read.All                         |
| Delegated (personal Microsoft account) | Not supported.                           |
| Application                            | Reports.Read.All                         |

**Note**: For delegated permissions to allow apps to read service usage reports on behalf of a user, the tenant administrator must have assigned the user the appropriate Azure AD limited administrator role. For more details, see [Authorization for APIs to read Microsoft 365 usage reports](/graph/reportroot-authorization).

## HTTP request


<!-- { "blockType": "ignored" } --> 

```http
GET /reports/getOneDriveUsageAccountCounts(period='{period_value}')
```

## Function parameters

In the request URL, provide the following parameter with a valid value.

| Parameter | Type   | Description                              |
| :-------- | :----- | :--------------------------------------- |
| period    | string | Specifies the length of time over which the report is aggregated. The supported values for {period_value} are: D7, D30, D90, and D180. These values follow the format D*n* where *n* represents the number of days over which the report is aggregated. Required. |

## Request headers

| Name          | Description                              |
| :------------ | :--------------------------------------- |
| Authorization | Bearer {token}. Required.                |
| If-None-Match | If this request header is included and the eTag provided matches the current tag on the file, a `304 Not Modified` response code is returned. Optional. |

## Response

If successful, this method returns a `302 Found` response that redirects to a preauthenticated download URL for the report. That URL can be found in the `Location` header in the response.

Preauthenticated download URLs are only valid for a short period of time (a few minutes) and do not require an `Authorization` header.

The CSV file has the following headers for columns.

- Report Refresh Date
- Site Type
- Total
- Active
- Report Date
- Report Period

## Example

#### Request

The following is an example of the request.


<!--{
  "blockType": "ignored",
  "isComposable": true,
  "name": "reportroot_getonedriveusageaccountcounts"
}-->

```http
GET https://graph.microsoft.com/v1.0/reports/getOneDriveUsageAccountCounts(period='D7')
```


#### Response

The following is an example of the response.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.report"
} -->

```http
HTTP/1.1 302 Found
Content-Type: text/plain
Location: https://reports.office.com/data/download/JDFKdf2_eJXKS034dbc7e0t__XDe
```

Follow the 302 redirection and the CSV file that downloads will have the following schema.

<!-- { "blockType": "ignored" } --> 

```http
HTTP/1.1 200 OK
Content-Type: application/octet-stream

Report Refresh Date,Site Type,Total,Active,Report Date,Report Period
```
<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79 
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Example",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}-->

