---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

PersonName personName = new PersonName();
personName.nickname = "Kesha";

graphClient.me().profile().names("{id}")
	.buildRequest()
	.patch(personName);

```