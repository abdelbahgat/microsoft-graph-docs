---
title: "riskDetection resource type"
description: "Represents all risk detections in AzureAD tenants."
author: "cloudhandler"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: resourcePageType
---
# riskDetection resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents information about a detected risk in an Azure AD tenant. 

Azure AD continually evaluates [user risks](riskyuser.md) and app or user [sign-in](signin.md) risks based on various signals and machine learning. This API provides programmatic access to all risk detections in your Azure AD environment.

For more information about risk events, see [Azure Active Directory Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection).

>[!NOTE]
> 1. You must have an Azure AD Premium P1 or P2 license to use the risk detection API.
> 2. The availability of risk detection data is governed by the [Azure AD data retention policies](/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data).

## Methods

| Method   | Return Type|Description|
|:---------------|:--------|:----------|
|[List riskDetection](../api/riskdetection-list.md) | [riskDetection](riskdetection.md) collection|List risk detections and their properties.|
|[Get riskDetection](../api/riskdetection-get.md) | [riskDetection](riskdetection.md)|Get a specific risky detection and its properties.|

## Properties

| Property   | Type|Description|
|:---------------|:--------|:----------|
|id|string|Unique ID of the risk detection. |
|requestId|string|Request ID of the sign-in associated with the risk detection. This property is null if the risk detection is not associated with a sign-in.|
|correlationId|string|Correlation ID of the sign-in associated with the risk detection. This property is null if the risk detection is not associated with a sign-in. |
|riskEventType|string|The type of risk event detected. The possible values are `unlikelyTravel`, `anonymizedIPAddress`, `maliciousIPAddress`, `unfamiliarFeatures`, `malwareInfectedIPAddress`, `suspiciousIPAddress`, `leakedCredentials`, `investigationsThreatIntelligence`, `generic`,`adminConfirmedUserCompromised`, `mcasImpossibleTravel`, `mcasSuspiciousInboxManipulationRules`, `investigationsThreatIntelligenceSigninLinked`, `maliciousIPAddressValidCredentialsBlockedIP`, and `unknownFutureValue`. <br/> For more information about each value, see [riskEventType values](#riskeventtype-values).|
|riskState|riskState|The state of a detected risky user or sign-in. The possible values are `none`, `confirmedSafe`, `remediated`, `dismissed`, `atRisk`, `confirmedCompromised`, and `unknownFutureValue`. |
|riskLevel|riskLevel|Level of the detected risk. The possible values are `low`, `medium`, `high`, `hidden`, `none`, `unknownFutureValue`. <br />**Note:** Details for this property are only available for Azure AD Premium P2 customers. P1 customers will be returned `hidden`.|
|riskDetail|riskDetail|Details of the detected risk. The possible values are `none`, `adminGeneratedTemporaryPassword`, `userPerformedSecuredPasswordChange`, `userPerformedSecuredPasswordReset`, `adminConfirmedSigninSafe`, `aiConfirmedSigninSafe`, `userPassedMFADrivenByRiskBasedPolicy`, `adminDismissedAllRiskForUser`, `adminConfirmedSigninCompromised`, `hidden`, `adminConfirmedUserCompromised`, `unknownFutureValue`. <br />**Note:** Details for this property are only available for Azure AD Premium P2 customers. P1 customers will be returned `hidden`.|
|source|string|Source of the risk detection. For example, `activeDirectory`. |
|detectionTimingType|riskDetectionTimingType|Timing of the detected risk (real-time/offline). The possible values are `notDefined`, `realtime`, `nearRealtime`, `offline`, `unknownFutureValue`. |
|activity|activityType|Indicates the activity type the detected risk is linked to. The possible values are `signin`, `user`, `unknownFutureValue`. |
|tokenIssuerType|tokenIssuerType|Indicates the type of token issuer for the detected sign-in risk. The possible values are `AzureAD`, `ADFederationServices`, and `unknownFutureValue`. |
|ipAddress|string|Provides the IP address of the client from where the risk occurred. |
|location|[signInLocation](signinlocation.md)|Location of the sign-in. |
|activityDateTime|DateTimeOffset|Date and time that the risky activity occurred. The DateTimeOffset type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`|
|detectedDateTime|DateTimeOffset|Date and time that the risk was detected. The DateTimeOffset type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z` |
|lastUpdatedDateTime|DateTimeOffset|Date and time that the risk detection was last updated. |
|userId|string|Unique ID of the user.  The DateTimeOffset type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`|
|userDisplayName|string|Name of the user. |
|userPrincipalName|string|The user principal name (UPN) of the user. |
|additionalInfo|string|Additional information associated with the risk detection in JSON format. |
|riskType (deprecated)|riskEventType|List of risk event types.<br />**Note:** This property is deprecated. Use **riskEventType** instead. |

### riskEventType values

| Member | Description |
|--|--|
| unlikelyTravel | Identifies two sign-ins originating from geographically distant locations, where at least one of the locations may also be atypical for the user, given past behavior.  |
| anonymizedIPAddress | Indicates sign-ins from an anonymous IP address, for example, using an anonymous browser or VPN. |
| maliciousIPAddress | Indicates sign-ins from IP addresses known to be malicious. Deprecated and no longer generated for new detections. |
| unfamiliarFeatures | Indicates sign-ins with characteristics that deviate from past sign-in properties. |
| malwareInfectedIPAddress | Indicates sign-ins from IP addresses infected with malware |
| suspiciousIPAddress | Identifies logins from IP addresses that are known to be malicious at the time of the sign in. |
| leakedCredentials | Indicates that the user's valid credentials have been leaked. This sharing is typically done by posting publicly on the dark web, paste sites, or by trading and selling the credentials on the black market. When the Microsoft leaked credentials service acquires user credentials from the dark web, paste sites, or other sources, they are checked against Azure AD users' current valid credentials to find valid matches. |
| investigationsThreatIntelligence | Indicates a sign-in activity that is unusual for the given user or is consistent with known attack patterns based on Microsoft's internal and external threat intelligence sources. |
| generic | Indicates that the user was not enabled for Identity Protection. |
| adminConfirmedUserCompromised | Indicates that an administrator has [confirmed the user is compromised](../api/riskyusers-confirmcompromised.md). |
| mcasImpossibleTravel | Discovered by Microsoft Defender for Cloud Apps (MDCA). Identifies two user activities (a single or multiple sessions) originating from geographically distant locations within a time period shorter than the time it would have taken the user to travel from the first location to the second, indicating that a different user is using the same credentials. |
| mcasSuspiciousInboxManipulationRules | Discovered by Microsoft Defender for Cloud Apps (MDCA). Identifies suspicious email forwarding rules, for example, if a user created an inbox rule that forwards a copy of all emails to an external address.|
| investigationsThreatIntelligenceSigninLinked | Identifies activity that is unusual with known attack patterns based on threat intelligence |
| maliciousIPAddressValidCredentialsBlockedIP | Indicates that sign-in was made with valid credentials from a malicious IP address. |
| unknownFutureValue | Evolvable enumeration sentinel value. Do not use. |


## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.riskDetection"
}-->

```json
{
 "id": "string",
    "requestId": "string",
    "correlationId": "string",
    "riskType": {"@odata.type": "microsoft.graph.riskEventType"},
    "riskState": {"@odata.type": "microsoft.graph.riskState"},
    "riskLevel": {"@odata.type": "microsoft.graph.riskLevel"},
    "riskDetail": {"@odata.type": "microsoft.graph.riskDetail"},
    "source": "string",
    "detectionTimingType": {"@odata.type": "microsoft.graph.riskDetectionTimingType"},
    "activity": {"@odata.type": "microsoft.graph.riskUserActivity"},
    "tokenIssuerType": {"@odata.type": "microsoft.graph.tokenIssuerType"},
    "ipAddress": "string",
    "location": {"@odata.type": "microsoft.graph.signInLocation"},
    "activityDateTime": "string (timestamp)",
    "detectedDateTime": "string (timestamp)",
    "lastUpdatedDateTime": "string (timestamp)",
    "userId": "string",
    "userDisplayName": "string",
    "userPrincipalName": "string",
    "additionalInfo": "string"
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "riskDetections resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
