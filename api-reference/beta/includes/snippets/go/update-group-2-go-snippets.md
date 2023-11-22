---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewGroup()


assignedLabel := graphmodels.NewAssignedLabel()
labelId := "45cd0c48-c540-4358-ad79-a3658cdc5b88"
assignedLabel.SetLabelId(&labelId) 

assignedLabels := []graphmodels.AssignedLabelable {
	assignedLabel,
}
requestBody.SetAssignedLabels(assignedLabels)

groups, err := graphClient.Groups().ByGroupId("group-id").Patch(context.Background(), requestBody, nil)


```