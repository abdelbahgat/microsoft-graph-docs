---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let personAnnotation = await client.api('/me/profile/notes/{id}')
	.version('beta')
	.get();

```