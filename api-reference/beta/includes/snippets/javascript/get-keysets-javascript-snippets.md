---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let keySets = await client.api('/trustFramework/keySets')
	.version('beta')
	.get();

```