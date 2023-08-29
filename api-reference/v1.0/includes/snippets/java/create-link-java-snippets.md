---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

String type = "view";

String password = "ThisIsMyPrivatePassword";

String scope = "anonymous";

graphClient.me().drive().items("{item-id}")
	.createLink(DriveItemCreateLinkParameterSet
		.newBuilder()
		.withType(type)
		.withScope(scope)
		.withExpirationDateTime(null)
		.withPassword(password)
		.withMessage(null)
		.withRetainInheritedPermissions(null)
		.build())
	.buildRequest()
	.post();

```