---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let thumbnails = await client.api('/me/drive/items/{item-id}/thumbnails')
	.version('beta')
	.get();

```