---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let personInterest = await client.api('/me/profile/interests/{id}')
	.version('beta')
	.get();

```