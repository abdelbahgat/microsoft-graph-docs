---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let itemPatent = await client.api('/me/profile/patents/{id}')
	.version('beta')
	.get();

```