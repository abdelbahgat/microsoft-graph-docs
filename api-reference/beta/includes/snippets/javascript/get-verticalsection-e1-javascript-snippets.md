---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let verticalSection = await client.api('/sites/{sitesId}/pages/{sitePageId}/canvasLayout/verticalSection')
	.version('beta')
	.get();

```