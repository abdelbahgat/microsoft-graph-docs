---
title: "crossTenantAccessPolicyConfigurationPartner resource type"
description: "The partner-specific configuration that is defined for inbound and outbound settings of Microsoft Entra B2B collaboration and B2B direct connect."
author: "jkdouglas"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: resourcePageType
---

# crossTenantAccessPolicyConfigurationPartner resource type

Namespace: microsoft.graph

The partner-specific configuration that is defined for inbound and outbound settings of Microsoft Entra B2B and B2B direct connect collaboration.

For any partner-specific property that is `null`, these settings inherit the behavior configured in your [default cross tenant access settings](../resources/crosstenantaccesspolicyconfigurationdefault.md).

## Methods

|Method|Return type|Description|
|:---|:---|:---|
| [List partners](../api/crosstenantaccesspolicy-list-partners.md) | [crossTenantAccessPolicyConfigurationPartner](../resources/crosstenantaccesspolicyconfigurationpartner.md) collection | Get a list of all partner-specific configurations. |
| [Create crossTenantAccessPolicyConfigurationPartner](../api/crosstenantaccesspolicy-post-partners.md) | [crossTenantAccessPolicyConfigurationPartner](../resources/crosstenantaccesspolicyconfigurationpartner.md) | Create a new partner-specific configuration. |
| [Get crossTenantAccessPolicyConfigurationPartner](../api/crosstenantaccesspolicyconfigurationpartner-get.md) | [crossTenantAccessPolicyConfigurationPartner](../resources/crosstenantaccesspolicyconfigurationpartner.md) | Read the partner-specific configuration settings. |
| [Update crossTenantAccessPolicyConfigurationPartner](../api/crosstenantaccesspolicyconfigurationpartner-update.md) | [crossTenantAccessPolicyConfigurationPartner](../resources/crosstenantaccesspolicyconfigurationpartner.md) | Update the properties of a partner-specific configuration. |
| [Delete crossTenantAccessPolicyConfigurationPartner](../api/crosstenantaccesspolicyconfigurationpartner-delete.md) | None | Delete the partner-specific configuration. |

## Properties

|Property|Type|Description|
|:---|:---|:---|
| automaticUserConsentSettings | [inboundOutboundPolicyConfiguration](../resources/inboundoutboundpolicyconfiguration.md) | Determines the partner-specific configuration for automatic user consent settings. Unless specifically configured, the **inboundAllowed** and **outboundAllowed** properties are `null` and inherit from the default settings, which is always `false`. |
| b2bCollaborationInbound | [crossTenantAccessPolicyB2BSetting](../resources/crosstenantaccesspolicyb2bsetting.md) | Defines your partner-specific configuration for users from other organizations accessing your resources via Microsoft Entra B2B collaboration. |
| b2bCollaborationOutbound | [crossTenantAccessPolicyB2BSetting](../resources/crosstenantaccesspolicyb2bsetting.md) | Defines your partner-specific configuration for users in your organization going outbound to access resources in another organization via Microsoft Entra B2B collaboration. |
| b2bDirectConnectInbound | [crossTenantAccessPolicyB2BSetting](../resources/crosstenantaccesspolicyb2bsetting.md) | Defines your partner-specific configuration for users from other organizations accessing your resources via Azure B2B direct connect. |
| b2bDirectConnectOutbound | [crossTenantAccessPolicyB2BSetting](../resources/crosstenantaccesspolicyb2bsetting.md) | Defines your partner-specific configuration for users in your organization going outbound to access resources in another organization via Microsoft Entra B2B direct connect. |
| inboundTrust | [crossTenantAccessPolicyInboundTrust](../resources/crosstenantaccesspolicyinboundtrust.md) | Determines the partner-specific configuration for trusting other Conditional Access claims from external Microsoft Entra organizations. |
| isServiceProvider | Boolean | Identifies whether the partner-specific configuration is a Cloud Service Provider for your organization. |
| tenantId | String | The tenant identifier for the partner Microsoft Entra organization. Read-only. Key.|

## Relationships

|Relationship|Type|Description|
|:---|:---|:---|
|identitySynchronization|[crossTenantIdentitySyncPolicyPartner](../resources/crosstenantidentitysyncpolicypartner.md)|Defines the cross-tenant policy for the synchronization of users from a partner tenant. Use this user synchronization policy to streamline collaboration between users in a multitenant organization by automating the creation, update, and deletion of users from one tenant to another.|

## JSON representation

Here's a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "tenantId",
  "@odata.type": "microsoft.graph.crossTenantAccessPolicyConfigurationPartner",
  "openType": false
}
-->

``` json
{
  "@odata.type": "#microsoft.graph.crossTenantAccessPolicyConfigurationPartner",
  "automaticUserConsentSettings": {"@odata.type": "microsoft.graph.inboundOutboundPolicyConfiguration"},
  "b2bCollaborationInbound": {"@odata.type": "microsoft.graph.crossTenantAccessPolicyB2BSetting"},
  "b2bCollaborationOutbound": {"@odata.type": "microsoft.graph.crossTenantAccessPolicyB2BSetting"},
  "b2bDirectConnectInbound": {"@odata.type": "microsoft.graph.crossTenantAccessPolicyB2BSetting"},
  "b2bDirectConnectOutbound": {"@odata.type": "microsoft.graph.crossTenantAccessPolicyB2BSetting"},
  "inboundTrust": {"@odata.type": "microsoft.graph.crossTenantAccessPolicyInboundTrust"},
  "isServiceProvider": "Boolean",
  "tenantId": "String (identifier)"
}
```
