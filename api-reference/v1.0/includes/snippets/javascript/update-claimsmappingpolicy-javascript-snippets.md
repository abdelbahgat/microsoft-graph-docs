---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const claimsMappingPolicy = {
    displayName: 'UpdateClaimsPolicy'
};

await client.api('/policies/claimsMappingPolicies/{id}')
	.update(claimsMappingPolicy);

```