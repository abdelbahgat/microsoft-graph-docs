---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let trending = await client.api('/me/insights/trending')
	.version('beta')
	.get();

```