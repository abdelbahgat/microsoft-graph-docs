---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let rubrics = await client.api('/education/me/rubrics')
	.version('beta')
	.get();

```