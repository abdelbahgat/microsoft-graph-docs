---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

CloudPcProvisioningPolicy cloudPcProvisioningPolicy = graphClient.deviceManagement().virtualEndpoint().provisioningPolicies("{id}")
	.buildRequest()
	.expand("assignments")
	.get();

```