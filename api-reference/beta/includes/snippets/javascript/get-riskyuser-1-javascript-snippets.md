---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let riskyUser = await client.api('/riskyUsers/c2b6c2b9-dddc-acd0-2b39-d519d803dbc3')
	.version('beta')
	.get();

```