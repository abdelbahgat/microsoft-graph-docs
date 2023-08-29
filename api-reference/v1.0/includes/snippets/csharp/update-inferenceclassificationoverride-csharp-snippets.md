---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var inferenceClassificationOverride = new InferenceClassificationOverride
{
	ClassifyAs = InferenceClassificationType.Focused
};

await graphClient.Me.InferenceClassification.Overrides["{inferenceClassificationOverride-id}"]
	.Request()
	.UpdateAsync(inferenceClassificationOverride);

```