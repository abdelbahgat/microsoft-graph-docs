---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const workbookNamedItem = {
  type: 'type-value',
  scope: 'scope-value',
  comment: 'comment-value',
  value: {
  },
  visible: true
};

await client.api('/me/drive/items/{id}/workbook/names/{name}')
	.version('beta')
	.update(workbookNamedItem);

```