---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

LinkedList<Option> requestOptions = new LinkedList<Option>();
requestOptions.add(new HeaderOption("ConsistencyLevel", "eventual"));

DeviceCollectionPage devices = graphClient.devices()
	.buildRequest( requestOptions )
	.filter("extensionAttributes/extensionAttribute1 eq 'BYOD-Device'")
	.get();

```