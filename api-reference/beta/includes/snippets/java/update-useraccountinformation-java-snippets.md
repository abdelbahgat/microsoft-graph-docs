---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

UserAccountInformation userAccountInformation = new UserAccountInformation();
userAccountInformation.countryCode = "NO";

graphClient.me().profile().account("{id}")
	.buildRequest()
	.patch(userAccountInformation);

```