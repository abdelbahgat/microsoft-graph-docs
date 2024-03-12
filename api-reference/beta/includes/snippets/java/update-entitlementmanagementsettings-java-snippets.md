---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

EntitlementManagementSettings entitlementManagementSettings = new EntitlementManagementSettings();
entitlementManagementSettings.externalUserLifecycleAction = "None";

graphClient.identityGovernance().entitlementManagement().settings()
	.buildRequest()
	.patch(entitlementManagementSettings);

```