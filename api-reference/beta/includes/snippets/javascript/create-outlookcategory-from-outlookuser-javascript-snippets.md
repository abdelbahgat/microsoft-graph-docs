---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const outlookCategory = {
   displayName: 'Project expenses',
   color: 'preset9'
};

await client.api('/me/outlook/masterCategories')
	.version('beta')
	.post(outlookCategory);

```