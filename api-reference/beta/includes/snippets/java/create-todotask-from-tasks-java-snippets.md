---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

TodoTask todoTask = new TodoTask();
todoTask.title = "A new task";
LinkedList<String> categoriesList = new LinkedList<String>();
categoriesList.add("Important");
todoTask.categories = categoriesList;
LinkedList<LinkedResource> linkedResourcesList = new LinkedList<LinkedResource>();
LinkedResource linkedResources = new LinkedResource();
linkedResources.webUrl = "http://microsoft.com";
linkedResources.applicationName = "Microsoft";
linkedResources.displayName = "Microsoft";
linkedResourcesList.add(linkedResources);
LinkedResourceCollectionResponse linkedResourceCollectionResponse = new LinkedResourceCollectionResponse();
linkedResourceCollectionResponse.value = linkedResourcesList;
LinkedResourceCollectionPage linkedResourceCollectionPage = new LinkedResourceCollectionPage(linkedResourceCollectionResponse, null);
todoTask.linkedResources = linkedResourceCollectionPage;

graphClient.me().todo().lists("AQMkADAwATM0MDAAMS0yMDkyLWVjMzYtM").tasks()
	.buildRequest()
	.post(todoTask);

```