---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let horizontalSections = await client.api('/sites/{sitesId}/pages/{sitePageId}/canvasLayout/horizontalSections')
	.version('beta')
	.get();

```