---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let riskyUsers = await client.api('/riskyUsers')
	.version('beta')
	.get();

```