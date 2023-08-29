---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

LinkedList<Option> requestOptions = new LinkedList<Option>();
requestOptions.add(new HeaderOption("Prefer", "odata.maxpagesize=2"));

ContactFolderDeltaCollectionPage delta = graphClient.me().contactFolders()
	.delta()
	.buildRequest( requestOptions )
	.get();

```