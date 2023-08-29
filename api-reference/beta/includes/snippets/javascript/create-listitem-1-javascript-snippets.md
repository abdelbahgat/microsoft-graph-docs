---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const listItem = {
  fields: {
    Title: 'Widget',
    Color: 'Purple',
    Weight: 32
  }
};

await client.api('/sites/{site-id}/lists/{list-id}/items')
	.version('beta')
	.post(listItem);

```