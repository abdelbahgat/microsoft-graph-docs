---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

ProgramControlCollectionPage controls = graphClient.programs("673a7379-9c38-4f01-bd9d-4fda7260b807").controls()
	.buildRequest()
	.get();

```