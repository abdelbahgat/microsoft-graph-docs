---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewGrantPostRequestBody()


driveRecipient := graphmodels.NewDriveRecipient()
email := "john@contoso.com"
driveRecipient.SetEmail(&email) 
driveRecipient1 := graphmodels.NewDriveRecipient()
email := "ryan@external.com"
driveRecipient1.SetEmail(&email) 

recipients := []graphmodels.DriveRecipientable {
	driveRecipient,
	driveRecipient1,

}
requestBody.SetRecipients(recipients)
roles := []String {
	"read",

}
requestBody.SetRoles(roles)

result, err := graphClient.SharesById("sharedDriveItem-id").Permission().Grant(sharedDriveItem-id).Post(requestBody)


```