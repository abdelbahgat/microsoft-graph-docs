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


requestBody := graphcommunications.NewInvitePostRequestBody()


invitationParticipantInfo := graphmodels.NewInvitationParticipantInfo()
identity := graphmodels.NewIdentitySet()
user := graphmodels.NewIdentity()
id := "278405a3-f568-4b3e-b684-009193463064"
user.SetId(&id) 
additionalData := map[string]interface{}{
	"identityProvider" : "AAD", 
}
user.SetAdditionalData(additionalData)
identity.SetUser(user)
invitationParticipantInfo.SetIdentity(identity)
participantId := "a7ebfb2d-871e-419c-87af-27290b22e8db"
invitationParticipantInfo.SetParticipantId(&participantId) 

participants := []graphmodels.InvitationParticipantInfoable {
	invitationParticipantInfo,
}
requestBody.SetParticipants(participants)
clientContext := "f2fa86af-3c51-4bc2-8fc0-475452d9764f"
requestBody.SetClientContext(&clientContext) 

invite, err := graphClient.Communications().Calls().ByCallId("call-id").Participants().Invite().Post(context.Background(), requestBody, nil)


```