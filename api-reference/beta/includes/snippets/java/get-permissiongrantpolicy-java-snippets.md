---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

PermissionGrantPolicy permissionGrantPolicy = graphClient.policies().permissionGrantPolicies("microsoft-user-default-low")
	.buildRequest()
	.get();

```