---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)


result, err := graphClient.PrivilegedAccessById("privilegedAccess-id").RoleAssignmentRequestsById("governanceRoleAssignmentRequest-id").UpdateRequest(privilegedAccess-id, governanceRoleAssignmentRequest-id).Post()


```