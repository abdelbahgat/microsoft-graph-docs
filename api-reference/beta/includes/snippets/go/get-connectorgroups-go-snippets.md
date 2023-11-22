---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)



connectorGroups, err := graphClient.OnPremisesPublishingProfiles().ByOnPremisesPublishingProfileId("onPremisesPublishingProfile-id").ConnectorGroups().Get(context.Background(), nil)


```