---
title: "orgContact resource type"
description: "Here is a JSON representation of the resource"
ms.localizationpriority: medium
author: "dkershaw10"
ms.prod: "identity-and-sign-in"
doc_type: resourcePageType
---

# orgContact resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents an organizational contact. Organizational contacts are managed by an organization's administrators and are different from [personal contacts](contact.md). Additionally, organizational contacts are either synchronized from on-premises directories or from Exchange Online, and are read-only in Microsoft Graph.

Inherits from [directoryObject](directoryobject.md).

This resource supports using [delta query](/graph/delta-query-overview) to track incremental additions, deletions, and updates, by providing a [delta](../api/orgcontact-delta.md) function. This resource is an open type that allows other properties to be passed in.

## Methods

| Method | Return Type | Description |
| ------ | ----------- | ----------- |
| **Organizational contacts** |
| [List organizational contacts](../api/orgcontact-list.md) | [orgContact](orgcontact.md) collection | List properties of organizational contacts. |
| [Get organizational contact](../api/orgcontact-get.md) | [orgContact](orgcontact.md) | Read properties and relationships of orgContact object. |
| **Organizational hierarchy** |
| [Get manager](../api/orgcontact-get-manager.md) | [directoryObject](directoryobject.md) | Get the contact's manager. |
| [Get transitiveReports](../api/orgcontact-get-transitivereports.md) | Integer | Get the count of transitive reports for an organization contact from the transitiveReports navigation property. |
| [List directReports](../api/orgcontact-list-directreports.md) | [directoryObject](directoryobject.md) collection | List the contact's direct reports. |
| [List memberOf](../api/orgcontact-list-memberof.md) | [directoryObject](directoryobject.md) collection | Get a memberOf object collection. |
| [checkMemberGroups](../api/directoryobject-checkmembergroups.md) | String collection | Check for group membership. |
| [getMemberGroups](../api/directoryobject-getmembergroups.md) | String collection | Return all the groups that the specified contact is a member of. |
| [checkMemberObjects](../api/directoryobject-checkmemberobjects.md) | String collection | Check for membership in groups, administrative units, and directory roles. |
| [getMemberObjects](../api/directoryobject-getmemberobjects.md) | String collection | Get the list of groups, administrative units, and directory roles the contact is a member of. |

## Properties

> [!IMPORTANT]
> Specific usage of `$filter` and the `$search` query parameter is supported only when you use the **ConsistencyLevel** header set to `eventual` and `$count`. For more information, see [Advanced query capabilities on Azure AD directory objects](/graph/aad-advanced-queries#organizational-contacts-properties).

| Property | Type | Description |
| -------- | ---- | ----------- |
| addresses | [physicalOfficeAddress](physicalofficeaddress.md) collection | Postal addresses for this organizational contact. For now a contact can only have one physical address. |
| companyName | String | Name of the company that this organizational contact belong to. Supports `$filter` (`eq`, `ne`, `not`, `ge`, `le`, `in`, `startsWith`, and `eq` on `null` values). |
| department | String | The name for the department in which the contact works. Supports `$filter` (`eq`, `ne`, `not`, `ge`, `le`, `in`, `startsWith`, and `eq` on `null` values). |
| displayName | String | Display name for this organizational contact. Supports `$filter` (`eq`, `ne`, `not`, `ge`, `le`, `in`, `startsWith`, and `eq` on `null` values), `$search`, and `$orderBy`.  |
| givenName | String | First name for this organizational contact. Supports `$filter` (`eq`, `ne`, `not`, `ge`, `le`, `in`, `startsWith`, and `eq` on `null` values).  |
| id | String | Unique identifier for this organizational contact. Supports `$filter` (`eq`, `ne`, `not`, `in`). |
| jobTitle | String | Job title for this organizational contact. Supports `$filter` (`eq`, `ne`, `not`, `ge`, `le`, `in`, `startsWith`, and `eq` on `null` values). |
| mail | String | The SMTP address for the contact, for example, "jeff@contoso.onmicrosoft.com". Supports `$filter` (`eq`, `ne`, `not`, `ge`, `le`, `in`, `startsWith`, and `eq` on `null` values). |
| mailNickname | String | Email alias (portion of email address pre-pending the @ symbol) for this organizational contact. Supports `$filter` (`eq`, `ne`, `not`, `ge`, `le`, `in`, `startsWith`, and `eq` on `null` values). |
| onPremisesLastSyncDateTime | DateTimeOffset | Date and time when this organizational contact was last synchronized from on-premises AD. The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`. Supports `$filter` (`eq`, `ne`, `not`, `ge`, `le`, `in`). |
| onPremisesProvisioningErrors | [onPremisesProvisioningError](onpremisesprovisioningerror.md) collection | List of any synchronization provisioning errors for this organizational contact. Supports `$filter` (`eq`, `not`). |
| onPremisesSyncEnabled | Boolean | **true** if this object is synced from an on-premises directory; **false** if this object was originally synced from an on-premises directory but is no longer synced and now mastered in Exchange; **null** if this object has never been synced from an on-premises directory (default). <br/> <br/>Supports `$filter` (`eq`, `ne`, `not`, `in`, and `eq` on `null` values). |
| phones | [phone](phone.md) collection | List of phones for this organizational contact. Phone types can be mobile, business, and businessFax. Only one of each type can ever be present in the collection. Supports `$filter` (`eq`, `ne`, `not`, `in`). |
| proxyAddresses | String collection | For example: "SMTP: bob@contoso.com", "smtp: bob@sales.contoso.com". The **any** operator is required for filter expressions on multi-valued properties. Supports `$filter` (`eq`, `not`, `ge`, `le`, `startsWith`, and counting empty collections). |
| surname | String | Last name for this organizational contact. Supports `$filter` (`eq`, `ne`, `not`, `ge`, `le`, `in`, `startsWith`, and `eq` on `null` values) |

## Relationships

| Relationship | Type | Description |
| ------------ | ---- | ----------- |
| directReports | [directoryObject](directoryobject.md) collection | The contact's direct reports. (The users and contacts that have their manager property set to this contact.) Read-only. Nullable. Supports `$expand`. |
| manager | [directoryObject](directoryobject.md) | The user or contact that is this contact's manager. Read-only. Supports `$expand`. |
| memberOf | [directoryObject](directoryobject.md) collection | Groups that this contact is a member of. Read-only. Nullable. Supports `$expand`. |
| transitiveReports | [directoryObject](directoryobject.md) collection | The transitive reports for a contact. Read-only. |

## JSON representation

Here is a JSON representation of the resource

<!-- {
  "blockType": "resource",
  "optionalProperties": [
    "directReports",
    "manager",
    "memberOf"
  ],
  "keyProperty": "id",
  "baseType":"microsoft.graph.entity",
  "@odata.type": "microsoft.graph.orgContact"
}-->

``` json
{
  "addresses": [{"@odata.type": "microsoft.graph.physicalOfficeAddress"}],
  "companyName": "string",
  "department": "string",
  "displayName": "string",
  "givenName": "string",
  "id": "string (identifier)",
  "jobTitle": "string",
  "mail": "string",
  "mailNickname": "string",
  "onPremisesLastSyncDateTime": "string (timestamp)",
  "onPremisesProvisioningErrors": [{"@odata.type": "microsoft.graph.onPremisesProvisioningError"}],
  "onPremisesSyncEnabled": true,
  "phones": [{"@odata.type": "microsoft.graph.phone"}],
  "proxyAddresses": ["string"],
  "surname": "string"
}
```
