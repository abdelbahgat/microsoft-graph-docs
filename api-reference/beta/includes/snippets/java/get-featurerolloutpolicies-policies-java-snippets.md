---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

FeatureRolloutPolicyCollectionPage featureRolloutPolicies = graphClient.policies().featureRolloutPolicies()
	.buildRequest()
	.get();

```