---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

Attachment attachment = graphClient.me().messages("AAMkADA1M-zAAA=").attachments("AAMkADA1M-CJKtzmnlcqVgqI=")
	.buildRequest()
	.expand("itemattachment/item")
	.get();

```