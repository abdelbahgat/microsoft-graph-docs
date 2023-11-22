---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)



graphClient.IdentityGovernance().EntitlementManagement().Catalogs().ByAccessPackageCatalogId("accessPackageCatalog-id").CustomWorkflowExtensions().ByCustomCalloutExtensionId("customCalloutExtension-id").Delete(context.Background(), nil)


```