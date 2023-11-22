---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

String name = "name-value";

graphClient.me().drive().items("{id}").workbook().worksheets()
	.add(WorkbookWorksheetAddParameterSet
		.newBuilder()
		.withName(name)
		.build())
	.buildRequest()
	.post();

```