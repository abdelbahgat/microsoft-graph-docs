---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

BrowserSiteList browserSiteList = graphClient.admin().edge().internetExplorerMode().siteLists("e370d818-f650-5ab1-499e-5915e83f4573")
	.buildRequest()
	.get();

```