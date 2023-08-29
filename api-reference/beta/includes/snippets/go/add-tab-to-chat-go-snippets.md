---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewTeamsTab()
displayName := "My Contoso Tab"
requestBody.SetDisplayName(&displayName) 
configuration := graphmodels.NewTeamsTabConfiguration()
entityId := "2DCA2E6C7A10415CAF6B8AB6661B3154"
configuration.SetEntityId(&entityId) 
contentUrl := "https://www.contoso.com/Orders/2DCA2E6C7A10415CAF6B8AB6661B3154/tabView"
configuration.SetContentUrl(&contentUrl) 
websiteUrl := "https://www.contoso.com/Orders/2DCA2E6C7A10415CAF6B8AB6661B3154"
configuration.SetWebsiteUrl(&websiteUrl) 
removeUrl := "https://www.contoso.com/Orders/2DCA2E6C7A10415CAF6B8AB6661B3154/uninstallTab"
configuration.SetRemoveUrl(&removeUrl) 
requestBody.SetConfiguration(configuration)
additionalData := map[string]interface{}{
	"teamsApp@odata.bind" : "https://graph.microsoft.com/beta/appCatalogs/teamsApps/06805b9e-77e3-4b93-ac81-525eb87513b8", 
}
requestBody.SetAdditionalData(additionalData)

result, err := graphClient.ChatsById("chat-id").Tabs().Post(requestBody)


```