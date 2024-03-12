---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

LinkedList<String> groupIdsList = new LinkedList<String>();
groupIdsList.add("fee2c45b-915a-4a64b130f4eb9e75525e");
groupIdsList.add("4fe90ae065a-478b9400e0a0e1cbd540");

graphClient.me()
	.checkMemberGroups(DirectoryObjectCheckMemberGroupsParameterSet
		.newBuilder()
		.withGroupIds(groupIdsList)
		.build())
	.buildRequest()
	.post();

```