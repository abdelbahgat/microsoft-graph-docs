---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const workbookTableColumn = {
  index: {
  }
};

await client.api('/me/drive/items/{id}/workbook/tables/{id|name}/columns/ItemAt')
	.version('beta')
	.post(workbookTableColumn);

```