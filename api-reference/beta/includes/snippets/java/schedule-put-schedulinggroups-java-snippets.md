---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

LinkedList<Option> requestOptions = new LinkedList<Option>();
requestOptions.add(new HeaderOption("Prefer", "return=representation"));

SchedulingGroup schedulingGroup = new SchedulingGroup();
schedulingGroup.displayName = "Cashiers";
schedulingGroup.isActive = true;
LinkedList<String> userIdsList = new LinkedList<String>();
userIdsList.add("c5d0c76b-80c4-481c-be50-923cd8d680a1");
userIdsList.add("2a4296b3-a28a-44ba-bc66-0274b9b95851");
schedulingGroup.userIds = userIdsList;

graphClient.teams("{teamId}").schedule().schedulingGroups("{schedulingGroupId}")
	.buildRequest( requestOptions )
	.put(schedulingGroup);

```