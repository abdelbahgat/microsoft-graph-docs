---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

HybridAgentUpdaterConfiguration hybridAgentUpdaterConfiguration = new HybridAgentUpdaterConfiguration();
hybridAgentUpdaterConfiguration.allowUpdateConfigurationOverride = false;

graphClient.customRequest("/onPremisesPublishingProfiles/provisioning/hybridAgentUpdaterConfiguration", HybridAgentUpdaterConfiguration.class)
	.buildRequest()
	.patch(hybridAgentUpdaterConfiguration);

```