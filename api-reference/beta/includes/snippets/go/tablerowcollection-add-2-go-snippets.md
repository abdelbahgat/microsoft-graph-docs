---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphdrives "github.com/microsoftgraph/msgraph-beta-sdk-go/drives"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphdrives.NewAddPostRequestBody()
index := null
requestBody.SetIndex(&index) 
values := []graphmodels.Jsonable {
	json := []graphmodels.Numberable {
 := int32(1)
requestBody.Set(&) 
 := int32(2)
requestBody.Set(&) 
 := int32(3)
requestBody.Set(&)
	}
	json := []graphmodels.Numberable {
 := int32(4)
requestBody.Set(&) 
 := int32(5)
requestBody.Set(&) 
 := int32(6)
requestBody.Set(&)
	}
}
requestBody.SetValues(values)

add, err := graphClient.Drives().ByDriveId("drive-id").Items().ByDriveItemId("driveItem-id").Workbook().Tables().ByWorkbookTableId("workbookTable-id").Rows().Add().Post(context.Background(), requestBody, nil)


```