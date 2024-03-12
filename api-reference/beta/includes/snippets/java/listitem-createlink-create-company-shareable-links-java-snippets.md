---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

String type = "edit";

String scope = "organization";

graphClient.sites("{siteId}").lists("{listId}").items("{itemId}")
	.createLink(ListItemCreateLinkParameterSet
		.newBuilder()
		.withType(type)
		.withScope(scope)
		.withExpirationDateTime(null)
		.withPassword(null)
		.withRecipients(null)
		.withRetainInheritedPermissions(null)
		.withSendNotification(null)
		.build())
	.buildRequest()
	.post();

```