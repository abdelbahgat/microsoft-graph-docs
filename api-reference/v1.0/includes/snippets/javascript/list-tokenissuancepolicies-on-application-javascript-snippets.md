---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let tokenIssuancePolicies = await client.api('/applications/{id}/tokenIssuancePolicies')
	.get();

```