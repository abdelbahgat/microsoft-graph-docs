---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let children = await client.api('/me/drive/items/{item-id}/children')
	.version('beta')
	.expand('thumbnails')
	.get();

```