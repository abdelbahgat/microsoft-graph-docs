---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let search = await client.api('/me/drive/search(q='Contoso Project')')
	.version('beta')
	.get();

```