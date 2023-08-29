---
title: "simulation resource type"
description: "Represents an attack simulation training campaign in a tenant."
author: "Gopal-MSFT"
ms.localizationpriority: medium
ms.prod: "security"
doc_type: resourcePageType
---

# simulation resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents an attack simulation training campaign in a tenant.

Attack simulation and training is a service available as part of [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365?view=o365-worldwide&preserve-view=true). This service lets users in a tenant experience a realistic benign phishing attack and learn from it. The service enables tenant administrators to simulate, assign trainings, and read derived insights into online behaviors of users in the phishing simulations. The service provides attack simulation reports that help tenants identify security knowledge gaps, so that they can further train their users to decrease their susceptibility to attacks.

The attack simulation and training API enables tenant administrators to list launched **simulation** exercises and trainings, and get [reports](report-m365defender-reports-overview.md) on derived insights into online behaviors of users in the phishing simulations.

## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[List simulations](../api/attacksimulationroot-list-simulations.md)|[simulation](../resources/simulation.md) collection|Get a list of the [simulation](../resources/simulation.md) objects and their properties.|

## Properties
|Property|Type|Description|
|:---|:---|:---|
|attackTechnique|[simulationAttackTechnique](#simulationattacktechnique-values)|The social engineering technique used in the attack simulation and training campaign. Supports `$filter` and `$orderby`. Possible values are: `unknown`, `credentialHarvesting`, `attachmentMalware`, `driveByUrl`, `linkInAttachment`, `linkToMalwareFile`, `unknownFutureValue`. For more information on the types of social engineering attack techniques, see [simulations](/microsoft-365/security/office-365-security/attack-simulation-training-get-started?view=o365-worldwide&preserve-view=true#simulations).|
|attackType|[simulationAttackType](#simulationattacktype-values)|Attack type of the attack simulation and training campaign. Supports `$filter` and `$orderby`. Possible values are: `unknown`, `social`, `cloud`, `endpoint`, `unknownFutureValue`.|
|automationId|String|Unique identifier for the attack simulation automation.|
|completionDateTime|DateTimeOffset|Date and time of completion of the attack simulation and training campaign. Supports `$filter` and `$orderby`.|
|createdBy|[emailIdentity](../resources/emailidentity.md)|Identity of the user who created the attack simulation and training campaign.|
|createdDateTime|DateTimeOffset|Date and time of creation of the attack simulation and training campaign.|
|description|String|Description of the attack simulation and training campaign.|
|displayName|String|Display name of the attack simulation and training campaign. Supports `$filter` and `$orderby`.|
|id|String|Unique identifier for the attack simulation and training campaign.|
|isAutomated|Boolean|Flag representing if the attack simulation and training campaign was created from a simulation automation flow. Supports `$filter` and `$orderby`. |
|lastModifiedBy|[emailIdentity](../resources/emailidentity.md)|Identity of the user who most recently modified the attack simulation and training campaign.|
|lastModifiedDateTime|DateTimeOffset|Date and time of the most recent modification of the attack simulation and training campaign.|
|launchDateTime|DateTimeOffset|Date and time of the launch/start of the attack simulation and training campaign. Supports `$filter` and `$orderby`.|
|payloadDeliveryPlatform|payloadDeliveryPlatform|Method of delivery of the phishing payload used in the attack simulation and training campaign. Possible values are: `unknown`, `sms`, `email`, `teams`, `unknownFutureValue`.|
|report|[simulationReport](../resources/simulationreport.md)|Report of the attack simulation and training campaign.|
|status|[simulationStatus](#simulationstatus-values)|Status of the attack simulation and training campaign. Supports `$filter` and `$orderby`. Possible values are: `unknown`, `draft`, `running`, `scheduled`, `succeeded`, `failed`, `cancelled`, `excluded`, `unknownFutureValue`.|

### simulationStatus values

|Member|Description |
|:---|:---|
|unknown| The simulation status is not defined. |
|draft| The simulation is in draft mode. |
|running| The simulation is running. |
|scheduled| The simulation is scheduled. |
|succeeded| The simulation has succeeded. |
|failed| The simulation has failed. |
|cancelled| The simulation is cancelled. |
|excluded| The simulation is excluded. |
|unknownFutureValue| Evolvable enumeration sentinel value. Do not use. |

### simulationAttackTechnique values

|Member|Description |
|:---|:---|
|unknown| Attack technique not defined. |
|credentialHarvesting| Attack technique that involves an end user supplying credentials. |
|attachmentMalware| Attack technique that involves an end user clicking an attachment. |
|driveByUrl| Attack technique that involves an end user clicking a URL link in the phishing payload. |
|linkInAttachment| Attack technique that involves an end user clicking a URL link in an attachment. |
|linkToMalwareFile| Attack technique that involves an end user clicking a URL link to a malware file. |
|unknownFutureValue| Evolvable enumeration sentinel value. Do not use. |

### simulationAttackType values

|Member|Description |
|:---|:---|
|unknown| Attack type not identified. |
|social| Attack that uses social skills to manipulate victims psychologically, creating a false sense of curiosity, urgency, or fear. |
|cloud| Attack on a host or user in a cloud environment, for example, denial of service attacks.|
|endpoint| Attack on endpoints of a corporate network, such as desktops, laptops, mobile phones, Internet-of-things devices. |
|unknownFutureValue| Evolvable enumeration sentinel value. Do not use. |

## Relationships
None.

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.simulation",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.simulation",
  "id": "String (identifier)",
  "displayName": "String",
  "description": "String",
  "attackType": "String",
  "attackTechnique": "String",
  "status": "String",
  "createdDateTime": "String (timestamp)",
  "createdBy": {
    "@odata.type": "microsoft.graph.emailIdentity"
  },
  "lastModifiedDateTime": "String (timestamp)",
  "lastModifiedBy": {
    "@odata.type": "microsoft.graph.emailIdentity"
  },
  "launchDateTime": "String (timestamp)",
  "completionDateTime": "String (timestamp)",
  "isAutomated": "Boolean",
  "automationId": "String",
  "payloadDeliveryPlatform": "String",
  "report": {
    "@odata.type": "microsoft.graph.simulationReport"
  }
}
```


## See also
- [Simulate a phishing attack](/microsoft-365/security/office-365-security/attack-simulation-training?view=o365-worldwide&preserve-view=true)
- [Get started using attack simulation training](/microsoft-365/security/office-365-security/attack-simulation-training-get-started?view=o365-worldwide&preserve-view=true#simulations).
