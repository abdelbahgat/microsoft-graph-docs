---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let securityAction = await client.api('/security/securityActions/{id}')
	.version('beta')
	.get();

```