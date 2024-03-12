---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

WorkbookFilterCriteria criteria = new WorkbookFilterCriteria();
criteria.criterion1 = "criterion1-value";
criteria.criterion2 = "criterion2-value";
criteria.color = "color-value";
String operator = new String();
criteria.operator = operator;
WorkbookIcon icon = new WorkbookIcon();
icon.set = "set-value";
icon.index = 99;
criteria.icon = icon;
criteria.dynamicCriteria = "dynamicCriteria-value";
JsonElement values = new JsonObject();
criteria.values = values;
criteria.filterOn = "filterOn-value";

graphClient.me().drive().items("{id}").workbook().tables("{id|name}").columns("{id|name}").filter()
	.apply(WorkbookFilterApplyParameterSet
		.newBuilder()
		.withCriteria(criteria)
		.build())
	.buildRequest()
	.post();

```