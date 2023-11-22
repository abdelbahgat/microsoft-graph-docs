---
title: "reportRoot resource type"
description: "Represents a container for Microsoft Entra ID reporting resources."
author: "egreenberg14"
ms.localizationpriority: medium
ms.prod: "identity-and-access-reports"
doc_type: resourcePageType
---

# reportRoot resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents a container for Microsoft Entra ID reporting resources.

## Methods

| Method                                                                                                | Return type                                                                                       | Description                                                                                                                                       |
| :---------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------ | :------------------------------------------------------------------------------------------------------------------------------------------------ |
| [List applicationSignInDetailedSummary](../api/reportroot-list-applicationsignindetailedsummary.md)   | [applicationSignInDetailedSummary](applicationsignindetailedsummary.md) collection                | Retrieve **applicationSignInDetailedSummary** objects.                                                                                            |
| [Get applicationSignInDetailedSummary](../api/applicationsignindetailedsummary-get.md)                | [applicationSignInDetailedSummary](applicationsignindetailedsummary.md)                           | Read the properties and relationships of an **applicationSignInDetailedSummary** object.                                                          |
| [getAzureADApplicationSignInSummary](../api/reportroot-getazureadapplicationsigninsummary.md)         | [applicationSignInSummary](applicationsigninsummary.md)                                           | Read the properties and relationships of an **applicationSignInSummary** object.                                                                  |
| [List credentialUserRegistrationDetails](../api/reportroot-list-credentialuserregistrationdetails.md) | [credentialUserRegistrationDetails](../resources/credentialuserregistrationdetails.md) collection | Get the details of credentialUserRegistrationDetails objects for a given tenant.                                                                  |
| [List userCredentialUsageDetails](../api/reportroot-list-usercredentialusagedetails.md)               | [userCredentialUsageDetails](../resources/usercredentialusagedetails.md) collection               | Get the userCredentialUsageDetails objects for a given tenant. Details include user information, status of the reset, and the reason for failure. |
<!--Temporarily hide these functions until we document them and others.
|[getAzureADLicenseUsage](../api/reportroot-getazureadlicenseusage.md)|[azureADLicenseUsage](../resources/azureadlicenseusage.md) collection|**TODO: Add Description**|
|[getAzureADUserFeatureUsage](../api/reportroot-getazureaduserfeatureusage.md)|[azureADUserFeatureUsage](../resources/azureaduserfeatureusage.md) collection|**TODO: Add Description**|
|[getAzureADFeatureUsage](../api/reportroot-getazureadfeatureusage.md)|[azureADFeatureUsage](../resources/azureadfeatureusage.md) collection|**TODO: Add Description**|
|[getAzureADApplicationSignInSummary](../api/reportroot-getazureadapplicationsigninsummary.md)|[applicationSignInSummary](../resources/applicationsigninsummary.md) collection|**TODO: Add Description**|
|[getCredentialUserRegistrationCount](../api/reportroot-getcredentialuserregistrationcount.md)|[credentialUserRegistrationCount](../resources/credentialuserregistrationcount.md) collection|**TODO: Add Description**|
|[getCredentialUsageSummary](../api/reportroot-getcredentialusagesummary.md)|[credentialUsageSummary](../resources/credentialusagesummary.md) collection|**TODO: Add -->

## Properties
None.

## Relationships
| Relationship                      | Type                                                                                              | Description                                                                                                         |
| :-------------------------------- | :------------------------------------------------------------------------------------------------ | :------------------------------------------------------------------------------------------------------------------ |
| appCredentialSignInActivities     | [appCredentialSignInActivity](../resources/appcredentialsigninactivity.md) collection             | Represents a collection of sign-in activities of application credentials.                                             |
| applicationSignInDetailedSummary  | [applicationSignInDetailedSummary](../resources/applicationsignindetailedsummary.md) collection   | Represents a detailed summary of an application sign-in.                                                            |
| authenticationMethods             | [authenticationMethodsRoot](../resources/authenticationmethodsroot.md)                            | Container for navigation properties for Microsoft Entra authentication methods resources.                                  |
| credentialUserRegistrationDetails | [credentialUserRegistrationDetails](../resources/credentialuserregistrationdetails.md) collection | Details of the usage of self-service password reset and multi-factor authentication (MFA) for all registered users. |
| dailyPrintUsageByPrinter | [printUsageByPrinter](../resources/printusagebyprinter.md) collection | Retrieve a list of daily print usage summaries, grouped by printer. | 
| dailyPrintUsageByUser | [printUsageByUser](../resources/printusagebyuser.md) collection | Retrieve a list of daily print usage summaries, grouped by user. |
| monthlyPrintUsageByPrinter | [printUsageByPrinter](../resources/printusagebyprinter.md) collection | Retrieve a list of monthly print usage summaries, grouped by printer. |
| monthlyPrintUsageByUser | [printUsageByUser](../resources/printusagebyuser.md) collection | Retrieve a list of monthly print usage summaries, grouped by user. |
| security                          | [securityReportsRoot](../resources/securityreportsroot.md)                                        | Provides the ability to launch a realistically simulated phishing attack that organizations can learn from.             |
| servicePrincipalSignInActivities  | [servicePrincipalSignInActivity](../resources/serviceprincipalsigninactivity.md) collection       | Represents a collection of sign-in activities of service principals.                                                   |
| userCredentialUsageDetails        | [userCredentialUsageDetails](../resources/usercredentialusagedetails.md) collection               | Represents the self-service password reset (SSPR) usage for a given tenant.                                         |
| sla                               | [serviceLevelAgreementRoot](../resources/servicelevelagreementroot.md)                            | A placeholder to allow for the desired URL path for SLA.                                                            |
| serviceActivity                               | [serviceActivity](../resources/serviceactivity.md)                            | A placeholder to the Microsoft Entra service activity.                                                            |

## JSON representation
The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.reportRoot",
  "baseType": "microsoft.graph.entity",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.reportRoot"
}
```
