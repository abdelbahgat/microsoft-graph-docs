---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let drive = await client.api('/users/{idOrUserPrincipalName}/drive')
	.version('beta')
	.get();

```