---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

LinkedList<Option> requestOptions = new LinkedList<Option>();
requestOptions.add(new HeaderOption("ConsistencyLevel", "eventual"));

UserCollectionPage users = graphClient.users()
	.buildRequest( requestOptions )
	.filter("customSecurityAttributes/Marketing/AppCountry ne 'Canada'")
	.select("id,displayName,customSecurityAttributes")
	.get();

```