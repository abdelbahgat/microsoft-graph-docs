---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Applications

$params = @{
	KeyId = "f0b0b335-1d71-4883-8f98-567911bfdca6"
	Proof = "eyJ0eXAiOiJ..."
}

Remove-MgApplicationKey -ApplicationId $applicationId -BodyParameter $params

```