---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Identity.SignIns

$params = @{
	"@odata.id" = " https://graph.microsoft.com/beta/directoryObjects/2441b489-4f12-4882-b039-8f6006bd66da"
}

New-MgBetaPolicyFeatureRolloutPolicyApplyToByRef -FeatureRolloutPolicyId $featureRolloutPolicyId -BodyParameter $params

```