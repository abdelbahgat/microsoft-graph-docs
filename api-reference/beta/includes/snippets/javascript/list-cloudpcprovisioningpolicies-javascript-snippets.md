---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let provisioningPolicies = await client.api('/deviceManagement/virtualEndpoint/provisioningPolicies')
	.version('beta')
	.get();

```