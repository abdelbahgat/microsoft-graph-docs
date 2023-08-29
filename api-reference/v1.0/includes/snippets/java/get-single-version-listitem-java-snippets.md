---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

LinkedList<Option> requestOptions = new LinkedList<Option>();
requestOptions.add(new QueryOption("expand", "fields"));

ListItemVersion listItemVersion = graphClient.sites("{site-id}").lists("{list-id}").items("{item-id}").versions("{version-id}")
	.buildRequest( requestOptions )
	.get();

```