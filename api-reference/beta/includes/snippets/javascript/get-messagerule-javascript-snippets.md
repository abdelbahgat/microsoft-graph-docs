---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let messageRule = await client.api('/me/mailfolders/inbox/messagerules('AQAAAJ5dZqA=')')
	.version('beta')
	.get();

```