---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let attachments = await client.api('/me/messages/{id}/attachments')
	.version('beta')
	.get();

```