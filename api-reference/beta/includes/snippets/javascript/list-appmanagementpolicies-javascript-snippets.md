---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let appManagementPolicies = await client.api('/policies/appManagementPolicies')
	.version('beta')
	.get();

```