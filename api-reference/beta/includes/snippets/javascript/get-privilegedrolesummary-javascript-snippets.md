---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let privilegedRoleSummary = await client.api('/privilegedRoles/{id}/summary')
	.version('beta')
	.get();

```