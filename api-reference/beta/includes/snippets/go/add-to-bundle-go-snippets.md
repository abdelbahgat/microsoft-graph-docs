---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := msgraphsdk.New()
requestBody.SetAdditionalData(map[string]interface{}{
	"id": "123456!87",
}
options := &msgraphsdk.ChildrenRequestBuilderPostOptions{
	Body: requestBody,
}
driveItemId := "driveItem-id"
graphClient.Drive().BundlesById(&driveItemId).Children().Post(options)


```