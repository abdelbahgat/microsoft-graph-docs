---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let registeredOwners = await client.api('/devices/{id}/registeredOwners')
	.version('beta')
	.get();

```