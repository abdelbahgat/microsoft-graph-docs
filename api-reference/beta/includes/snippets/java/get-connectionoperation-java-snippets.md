---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

ConnectionOperation connectionOperation = graphClient.external().connections("contosohr").operations("3ed1595a-4bae-43c2-acda-ef973e581323")
	.buildRequest()
	.get();

```