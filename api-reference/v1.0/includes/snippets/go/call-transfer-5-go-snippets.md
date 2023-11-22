---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphcommunications "github.com/microsoftgraph/msgraph-sdk-go/communications"
	  graphmodels "github.com/microsoftgraph/msgraph-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphcommunications.NewTransferPostRequestBody()
transferTarget := graphmodels.NewInvitationParticipantInfo()
identity := graphmodels.NewIdentitySet()
user := graphmodels.NewIdentity()
id := "550fae72-d251-43ec-868c-373732c2704f"
user.SetId(&id) 
displayName := "Heidi Steen"
user.SetDisplayName(&displayName) 
identity.SetUser(user)
transferTarget.SetIdentity(identity)
additionalData := map[string]interface{}{
	"endpointType" : "default", 
}
transferTarget.SetAdditionalData(additionalData)
requestBody.SetTransferTarget(transferTarget)
transferee := graphmodels.NewParticipantInfo()
identity := graphmodels.NewIdentitySet()
user := graphmodels.NewIdentity()
id := "751f6800-3180-414d-bd94-333364659951"
user.SetId(&id) 
additionalData := map[string]interface{}{
	"tenantId" : "72f988bf-86f1-41af-91ab-2d7cd011db47", 
}
user.SetAdditionalData(additionalData)
identity.SetUser(user)
transferee.SetIdentity(identity)
participantId := "909c6581-5130-43e9-88f3-fcb3582cde37"
transferee.SetParticipantId(&participantId) 
requestBody.SetTransferee(transferee)

graphClient.Communications().Calls().ByCallId("call-id").Transfer().Post(context.Background(), requestBody, nil)


```