---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

LinkedResource_v2 linkedResource_v2 = new LinkedResource_v2();
linkedResource_v2.webUrl = "https://microsoft.com";
linkedResource_v2.applicationName = "Microsoft";
linkedResource_v2.displayName = "Microsoft";
linkedResource_v2.externalId = "dk9cddce2-dce2-f9dd-e2dc-cdf9e2dccdf9";

graphClient.me().tasks().lists("AAMkADliMmU5YjJlLTVmMmQtNGQzNS1iYjA0LTdmZTA2NTI0MTE5YwAuAAAAAADdOMUbUmCfTKa7OC-fqjkdAQBnu3olF7NfToRyJ2f__TNcAAAAAAESAAA=").tasks("AAkALgAAAAAAHYQDEapmEc2byACqAC-EWg0AZ7t6JRezX06Ecidn-vkzXAABPDii4gAA").linkedResources()
	.buildRequest()
	.post(linkedResource_v2);

```