---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

SynchronizationJob synchronizationJob = graphClient.servicePrincipals("{id}").synchronization().jobs("{jobId}")
	.buildRequest()
	.get();

```