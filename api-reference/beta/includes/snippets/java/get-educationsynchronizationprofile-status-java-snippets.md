---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

EducationSynchronizationProfileStatus educationSynchronizationProfileStatus = graphClient.education().synchronizationProfiles("{id}").profileStatus()
	.buildRequest()
	.get();

```