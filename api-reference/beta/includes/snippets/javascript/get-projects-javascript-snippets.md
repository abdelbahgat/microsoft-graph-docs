---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let projects = await client.api('/me/profile/projects')
	.version('beta')
	.get();

```