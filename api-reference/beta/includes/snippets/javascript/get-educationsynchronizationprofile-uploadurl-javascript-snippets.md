---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let string = await client.api('/education/synchronizationProfiles/{id}/uploadUrl')
	.version('beta')
	.get();

```