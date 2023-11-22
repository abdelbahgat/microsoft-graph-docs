---
title: "domainDnsRecord resource type"
description: "The domainDnsRecord entity is used to present DNS records."
ms.localizationpriority: medium
author: "adimitui"
ms.prod: "directory-management"
doc_type: resourcePageType
---

# domainDnsRecord resource type

Namespace: microsoft.graph

For each [domain](domain.md) in the tenant, you may be required to add DNS record(s) to the DNS zone file of the domain before the domain can be used by Microsoft Online Services. These DNS records are represented

The **domainDnsRecord** resource type is used to present such DNS records as exposed through the **serviceConfigurationRecords** and **verificationDnsRecords**. This resource type is the base entity for the following resources:
+ [domainDnsCnameRecord](domaindnscnamerecord.md)
+ [domainDnsMxRecord](domaindnsmxrecord.md)
+ [domainDnsSrvRecord](domaindnssrvrecord.md)
+ [domainDnsTxtRecord](domaindnstxtrecord.md)
+ [domainDnsUnavailableRecord](domaindnsunavailablerecord.md)

## Methods

None.

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|String| Unique identifier assigned to this entity. Not nullable, Read-only.|
|isOptional|Boolean| If `false`, this record must be configured by the customer at the DNS host for Microsoft Online Services to operate correctly with the domain. |
|label|String| Value used when configuring the name of the DNS record at the DNS host. |
|recordType|String| Indicates what type of DNS record this entity represents. The value can be `CName`, `Mx`, `Srv`, or `Txt`. |
|supportedService|String| Microsoft Online Service or feature that has a dependency on this DNS record. Can be one of the following values: `null`, `Email`, `Sharepoint`, `EmailInternalRelayOnly`, `OfficeCommunicationsOnline`, `SharePointDefaultDomain`, `FullRedelegation`, `SharePointPublic`, `OrgIdAuthentication`, `Yammer`, `Intune`.|
|ttl|Int32| Value to use when configuring the time-to-live (ttl) property of the DNS record at the DNS host. Not nullable. |

## Relationships
None

## JSON representation
Here's a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "baseType": "microsoft.graph.entity",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.domainDnsRecord"
}-->

```json
{
  "id": "String (identifier)",
  "isOptional": true,
  "label": "String",
  "recordType": "String",
  "supportedService": "String",
  "ttl": 1024
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "domainDnsRecord resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

