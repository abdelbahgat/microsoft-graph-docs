---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let recommendations = await client.api('/directory/recommendations')
	.version('beta')
	.get();

```