---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewUnassignTagPostRequestBody()
tenantIds := []String {
	"String",

}
requestBody.SetTenantIds(tenantIds)

result, err := graphClient.TenantRelationships().ManagedTenants().TenantTagsById("tenantTag-id").UnassignTag(tenantTag-id).Post(requestBody)


```