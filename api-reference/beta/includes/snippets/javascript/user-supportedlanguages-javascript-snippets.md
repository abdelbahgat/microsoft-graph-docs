---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let supportedLanguages = await client.api('/me/outlook/supportedLanguages')
	.version('beta')
	.get();

```