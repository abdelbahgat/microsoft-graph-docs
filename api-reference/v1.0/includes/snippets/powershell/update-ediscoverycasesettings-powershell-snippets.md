---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Security

$params = @{
	"@odata.type" = "#microsoft.graph.security.ediscoveryCaseSettings"
	RedundancyDetection = @{
		"@odata.type" = "microsoft.graph.security.redundancyDetectionSettings"
	}
	TopicModeling = @{
		"@odata.type" = "microsoft.graph.security.topicModelingSettings"
	}
	Ocr = @{
		"@odata.type" = "microsoft.graph.security.ocrSettings"
	}
}

Update-MgSecurityCaseEdiscoveryCaseSetting -EdiscoveryCaseId $ediscoveryCaseId -BodyParameter $params

```