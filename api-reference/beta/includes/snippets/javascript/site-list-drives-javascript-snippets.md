---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let drives = await client.api('/sites/{siteId}/drives')
	.version('beta')
	.get();

```