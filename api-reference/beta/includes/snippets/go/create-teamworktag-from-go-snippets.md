---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewTeamworkTag()
displayName := "Finance"
requestBody.SetDisplayName(&displayName) 


teamworkTagMember := graphmodels.NewTeamworkTagMember()
userId := "92f6952f-61ca-4a94-8910-508a240bc167"
teamworkTagMember.SetUserId(&userId) 
teamworkTagMember1 := graphmodels.NewTeamworkTagMember()
userId := "085d800c-b86b-4bfc-a857-9371ad1caf29"
teamworkTagMember1.SetUserId(&userId) 

members := []graphmodels.TeamworkTagMemberable {
	teamworkTagMember,
	teamworkTagMember1,

}
requestBody.SetMembers(members)

result, err := graphClient.TeamsById("team-id").Tags().Post(requestBody)


```