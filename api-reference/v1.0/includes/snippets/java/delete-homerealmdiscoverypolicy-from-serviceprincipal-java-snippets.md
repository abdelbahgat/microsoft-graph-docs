---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

graphClient.servicePrincipals("{id}").homeRealmDiscoveryPolicies("{id}").reference()
	.buildRequest()
	.delete();

```