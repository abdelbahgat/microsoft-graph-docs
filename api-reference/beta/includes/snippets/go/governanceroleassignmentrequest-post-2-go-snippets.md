---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewGovernanceRoleAssignmentRequest()
roleDefinitionId := "8b4d1d51-08e9-4254-b0a6-b16177aae376"
requestBody.SetRoleDefinitionId(&roleDefinitionId) 
resourceId := "e5e7d29d-5465-45ac-885f-4716a5ee74b5"
requestBody.SetResourceId(&resourceId) 
subjectId := "918e54be-12c4-4f4c-a6d3-2ee0e3661c51"
requestBody.SetSubjectId(&subjectId) 
assignmentState := "Active"
requestBody.SetAssignmentState(&assignmentState) 
type := "UserAdd"
requestBody.SetType(&type) 
reason := "Activate the owner role"
requestBody.SetReason(&reason) 
schedule := graphmodels.NewGovernanceSchedule()
type := "Once"
schedule.SetType(&type) 
startDateTime , err := time.Parse(time.RFC3339, "2018-05-12T23:28:43.537Z")
schedule.SetStartDateTime(&startDateTime) 
duration := "PT9H"
schedule.SetDuration(&duration) 
requestBody.SetSchedule(schedule)
linkedEligibleRoleAssignmentId := "e327f4be-42a0-47a2-8579-0a39b025b394"
requestBody.SetLinkedEligibleRoleAssignmentId(&linkedEligibleRoleAssignmentId) 

result, err := graphClient.PrivilegedAccessById("privilegedAccess-id").RoleAssignmentRequests().Post(requestBody)


```