---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const workbookWorksheet = {
  position: 99,
  name: 'name-value',
  visibility: 'visibility-value'
};

await client.api('/me/drive/items/{id}/workbook/worksheets/{id|name}')
	.update(workbookWorksheet);

```