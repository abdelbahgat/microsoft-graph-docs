---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let group = await client.api('/groups/45b7d2e7-b882-4a80-ba97-10b7a63b8fa4')
	.version('beta')
	.get();

```