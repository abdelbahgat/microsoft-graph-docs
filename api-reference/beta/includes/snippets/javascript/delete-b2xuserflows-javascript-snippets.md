---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

await client.api('/identity/b2xUserFlows/{id}')
	.version('beta')
	.delete();

```