---
title: "cloudPcProvisioningPolicy resource type"
description: "Represents a Cloud PC provisioning policy."
author: "AshleyYangSZ"
ms.localizationpriority: medium
ms.prod: "cloud-pc"
doc_type: resourcePageType
---

# cloudPcProvisioningPolicy resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents a Cloud PC provisioning policy.

## Methods

|Method|Return type|Description|
|:---|:---|:---|
|[List provisioningPolicies](../api/virtualendpoint-list-provisioningpolicies.md)|[cloudPcProvisioningPolicy](../resources/cloudpcprovisioningpolicy.md) collection|List properties and relationships of the [cloudPcProvisioningPolicy](../resources/cloudpcprovisioningpolicy.md) objects.|
|[Get cloudPcProvisioningPolicy](../api/cloudpcprovisioningpolicy-get.md)|[cloudPcProvisioningPolicy](../resources/cloudpcprovisioningpolicy.md)|Read the properties and relationships of a [cloudPcProvisioningPolicy](../resources/cloudpcprovisioningpolicy.md) object.|
|[Create cloudPcProvisioningPolicy](../api/virtualendpoint-post-provisioningpolicies.md)|[cloudPcProvisioningPolicy](../resources/cloudpcprovisioningpolicy.md)|Create a new [cloudPcProvisioningPolicy](../resources/cloudpcprovisioningpolicy.md) object.|
|[Update cloudPcProvisioningPolicy](../api/cloudpcprovisioningpolicy-update.md)|[cloudPcProvisioningPolicy](../resources/cloudpcprovisioningpolicy.md)|Update the properties of a [cloudPcProvisioningPolicy](../resources/cloudpcprovisioningpolicy.md) object.|
|[Delete cloudPcProvisioningPolicy](../api/cloudpcprovisioningpolicy-delete.md)|None|Delete a [cloudPcProvisioningPolicy](../resources/cloudpcprovisioningpolicy.md) object.|
|[Assign cloudPcProvisioningPolicy](../api/cloudpcprovisioningpolicy-assign.md)|None |Assign a [cloudPcProvisioningPolicy](../resources/cloudpcprovisioningpolicy.md) to user groups.|

## Properties

|Property|Type|Description|
|:---|:---|:---|
|alternateResourceUrl|String|The URL of the alternate resource that links to this provisioning policy. Read-only.|
|cloudPcGroupDisplayName|String|The display name of the Cloud PC group that the Cloud PCs reside in. Read-only.|
|description|String|The provisioning policy description.|
|displayName|String|The display name for the provisioning policy.|
|domainJoinConfiguration|[cloudPcDomainJoinConfiguration](../resources/cloudpcdomainjoinconfiguration.md)|Specifies how Cloud PCs will join Azure Active Directory.|
|enableSingleSignOn|Boolean|`True` if the provisioned Cloud PC can be accessed by single sign-on. `False` indicates that the provisioned Cloud PC doesn't support this feature. Default value is `false`. Windows 365 users can use single sign-on to authenticate to Azure Active Directory (Azure AD) with passwordless options (for example, FIDO keys) to access their Cloud PC. Optional.|
|gracePeriodInHours|Int32|The number of hours to wait before reprovisioning/deprovisioning happens. Read-only.|
|id|String|Unique identifier for the Cloud PC provisioning policy. Read-only.|
|imageDisplayName|String|The display name for the OS image you’re provisioning.|
|imageId|String|The ID of the OS image you want to provision on Cloud PCs. The format for a gallery type image is: {publisher_offer_sku}. Supported values for each of the parameters are as follows:<ul><li>publisher: Microsoftwindowsdesktop.</li> <li>offer: windows-ent-cpc.</li> <li>sku: 21h1-ent-cpc-m365, 21h1-ent-cpc-os, 20h2-ent-cpc-m365, 20h2-ent-cpc-os, 20h1-ent-cpc-m365, 20h1-ent-cpc-os, 19h2-ent-cpc-m365 and 19h2-ent-cpc-os.</li></ul>|
|imageType|cloudPcProvisioningPolicyImageType|The type of OS image (custom or gallery) you want to provision on Cloud PCs. Possible values are: `gallery`, `custom`.|
|localAdminEnabled|Boolean|Indicates whether the local admin option is enabled. If the local admin option is enabled, the end user can be an admin of the Cloud PC device. Read-only.|
|managedBy|[cloudPcManagementService](../resources/cloudpconpremisesconnection.md#cloudpcmanagementservice-values)|Specifies which services manage the Azure network connection. Possible values are: `windows365`, `devBox`, `unknownFutureValue`, `rpaBox`. Note that you must use the `Prefer: include-unknown-enum-members` request header to get the following value(s) in this [evolvable enum](/graph/best-practices-concept#handling-future-members-in-evolvable-enumerations): `rpaBox`. Read-only.|
|microsoftManagedDesktop|[microsoftManagedDesktop](../resources/microsoftManagedDesktop.md)|The specific settings for the Microsoft Managed Desktop, which enables customers to get a managed device experience for the Cloud PC. Before you can enable Microsoft Managed Desktop, an admin must configure it.|
|onPremisesConnectionId|String|The ID of the cloudPcOnPremisesConnection. To ensure that Cloud PCs have network connectivity and that they domain join, choose a connection with a virtual network that’s validated by the Cloud PC service.|
|provisioningType|[cloudPcProvisioningType](../resources/cloudpcprovisioningpolicy.md#cloudpcprovisioningtype-values)|Specifies the type of license used when provisioning Cloud PCs using this policy. By default, the license type is `dedicated` if the **provisioningType** isn't specified when you create the **cloudPcProvisioningPolicy**. You can't change this property after the **cloudPcProvisioningPolicy** was created. Possible values are: `dedicated`, `shared`, `unknownFutureValue`.|
|windowsSettings|[cloudPcWindowsSettings](../resources/cloudpcwindowssettings.md)|Specific Windows settings to configure while creating Cloud PCs for this provisioning policy.|

### cloudPcProvisioningType values

| Member              | Description                                                                           |
|:--------------------|:--------------------------------------------------------------------------------------|
| dedicated           | Indicates that a dedicated license is used for provisioning Cloud PCs. Default value. |
| shared              | Indicates that a shared license is used for provisioning Cloud PCs.                   |
| unknownFutureValue  | Evolvable enumeration sentinel value. Do not use.                                     |

## Relationships

|Relationship|Type|Description|
|:---|:---|:---|
|assignments|[cloudPcProvisioningPolicyAssignment](../resources/cloudpcprovisioningpolicyassignment.md) collection|A defined collection of provisioning policy assignments. Represents the set of Microsoft 365 groups and security groups in Azure AD that have provisioning policy assigned. Returned only on `$expand`. For an example about how to get the assignments relationship, see [Get cloudPcProvisioningPolicy](../api/cloudpcprovisioningpolicy-get.md). |

## JSON representation

The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.cloudPcProvisioningPolicy",
  "baseType": "microsoft.graph.entity",
  "openType": false
}
-->

``` json
{
  "@odata.type": "#microsoft.graph.cloudPcProvisioningPolicy",
  "alternateResourceUrl": "String",
  "cloudPcGroupDisplayName": "String",
  "description": "String",
  "displayName": "String",
  "domainJoinConfiguration": {
    "@odata.type": "microsoft.graph.cloudPcDomainJoinConfiguration"
  },
  "enableSingleSignOn": "Boolean",
  "gracePeriodInHours": "Int32",
  "id": "String (identifier)",
  "imageDisplayName": "String",
  "imageId": "String",
  "imageType": "String",
  "localAdminEnabled": "Boolean",
  "managedBy": "String",
  "microsoftManagedDesktop": {
    "@odata.type": "microsoft.graph.microsoftManagedDesktop"
  },
  "onPremisesConnectionId": "String",
  "provisioningType": "String",
  "windowsSettings": {
    "@odata.type": "microsoft.graph.cloudPcWindowsSettings"
  }
}
```
