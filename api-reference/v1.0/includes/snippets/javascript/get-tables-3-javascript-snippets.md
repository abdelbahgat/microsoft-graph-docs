---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let tables = await client.api('/me/drive/items/{id}/workbook/worksheets/{id|name}/tables')
	.get();

```