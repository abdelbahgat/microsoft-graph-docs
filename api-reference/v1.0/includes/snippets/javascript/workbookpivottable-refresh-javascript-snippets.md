---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

await client.api('/me/drive/root/workbook/worksheets/{id}/pivotTables/{id}/refresh')
	.post();

```