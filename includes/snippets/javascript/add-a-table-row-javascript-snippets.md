---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const workbookTableRow = {
  values: [[“east”, “pear”, 4]]
};

await client.api('/me/drive/items/{id}/workbook/tables/Table1/rows/add')
	.post(workbookTableRow);

```