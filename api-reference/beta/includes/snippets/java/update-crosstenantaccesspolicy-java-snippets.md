---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

CrossTenantAccessPolicy crossTenantAccessPolicy = new CrossTenantAccessPolicy();
LinkedList<String> allowedCloudEndpointsList = new LinkedList<String>();
allowedCloudEndpointsList.add("microsoftonline.us");
allowedCloudEndpointsList.add("partner.microsoftonline.cn");
crossTenantAccessPolicy.allowedCloudEndpoints = allowedCloudEndpointsList;

graphClient.policies().crossTenantAccessPolicy()
	.buildRequest()
	.patch(crossTenantAccessPolicy);

```