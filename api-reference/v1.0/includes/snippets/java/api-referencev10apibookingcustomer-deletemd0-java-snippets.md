---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

graphClient.solutions().bookingBusinesses("Contosolunchdelivery@contoso.onmicrosoft.com").customers("80b5ddda-1e3b-4c9d-abe2-d606cc075e2e")
	.buildRequest()
	.delete();

```