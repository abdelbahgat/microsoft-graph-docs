---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let languageProficiency = await client.api('/me/profile/languages/{id}')
	.version('beta')
	.get();

```