---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

CustomCalloutExtension customCalloutExtension = graphClient.identityGovernance().entitlementManagement().accessPackageCatalogs("32efb28c-9a7a-446c-986b-ca6528c6669d").accessPackageCustomWorkflowExtensions("78ffaec5-ae8e-4902-a434-5ffc5d3d3cd0")
	.buildRequest()
	.get();

```