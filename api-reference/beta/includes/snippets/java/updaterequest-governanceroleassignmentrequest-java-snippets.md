---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

graphClient.privilegedAccess("azureResources").roleAssignmentRequests("7c53453e-d5a4-41e0-8eb1-32d5ec8bfdee")
	.updateRequest(GovernanceRoleAssignmentRequestUpdateRequestParameterSet
		.newBuilder()
		.withDecision(null)
		.withAssignmentState(null)
		.withSchedule(null)
		.withReason(null)
		.build())
	.buildRequest()
	.post();

```