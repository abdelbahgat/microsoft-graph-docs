---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

UnifiedRoleManagementPolicyAssignmentCollectionPage roleManagementPolicyAssignments = graphClient.policies().roleManagementPolicyAssignments()
	.buildRequest()
	.filter("scopeId eq '/' and scopeType eq 'Directory'")
	.get();

```