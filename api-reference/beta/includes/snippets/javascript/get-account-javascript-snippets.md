---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let account = await client.api('/me/profile/account')
	.version('beta')
	.get();

```