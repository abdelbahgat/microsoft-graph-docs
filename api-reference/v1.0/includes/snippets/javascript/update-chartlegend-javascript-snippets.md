---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const workbookChartLegend = {
  visible: true,
  position: 'position-value',
  overlay: true
};

await client.api('/me/drive/items/{id}/workbook/worksheets/{id|name}/charts/{name}/legend')
	.update(workbookChartLegend);

```