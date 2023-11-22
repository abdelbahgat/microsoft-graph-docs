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


requestBody := graphmodels.NewAccessPackageAssignmentPolicy()
accessPackageId := "88203d16-0e31-41d4-87b2-dd402f1435e9"
requestBody.SetAccessPackageId(&accessPackageId) 
displayName := "Specific users"
requestBody.SetDisplayName(&displayName) 
description := "Specific users can request assignment"
requestBody.SetDescription(&description) 
accessReviewSettings := null
requestBody.SetAccessReviewSettings(&accessReviewSettings) 
durationInDays := int32(30)
requestBody.SetDurationInDays(&durationInDays) 
requestorSettings := graphmodels.NewRequestorSettings()
scopeType := "SpecificDirectorySubjects"
requestorSettings.SetScopeType(&scopeType) 
acceptRequests := true
requestorSettings.SetAcceptRequests(&acceptRequests) 


userSet := graphmodels.NewSingleUser()
isBackup := false
userSet.SetIsBackup(&isBackup) 
id := "007d1c7e-7fa8-4e33-b678-5e437acdcddc"
userSet.SetId(&id) 
description := "Requestor1"
userSet.SetDescription(&description) 

allowedRequestors := []graphmodels.UserSetable {
	userSet,
}
requestorSettings.SetAllowedRequestors(allowedRequestors)
requestBody.SetRequestorSettings(requestorSettings)
requestApprovalSettings := graphmodels.NewApprovalSettings()
isApprovalRequired := false
requestApprovalSettings.SetIsApprovalRequired(&isApprovalRequired) 
isApprovalRequiredForExtension := false
requestApprovalSettings.SetIsApprovalRequiredForExtension(&isApprovalRequiredForExtension) 
isRequestorJustificationRequired := false
requestApprovalSettings.SetIsRequestorJustificationRequired(&isRequestorJustificationRequired) 
approvalMode := "NoApproval"
requestApprovalSettings.SetApprovalMode(&approvalMode) 
approvalStages := []graphmodels.ApprovalStageable {

}
requestApprovalSettings.SetApprovalStages(approvalStages)
requestBody.SetRequestApprovalSettings(requestApprovalSettings)

accessPackageAssignmentPolicies, err := graphClient.IdentityGovernance().EntitlementManagement().AccessPackageAssignmentPolicies().Post(context.Background(), requestBody, nil)


```