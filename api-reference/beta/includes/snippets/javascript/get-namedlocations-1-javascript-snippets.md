---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let namedLocations = await client.api('/identity/conditionalAccess/namedLocations')
	.version('beta')
	.get();

```