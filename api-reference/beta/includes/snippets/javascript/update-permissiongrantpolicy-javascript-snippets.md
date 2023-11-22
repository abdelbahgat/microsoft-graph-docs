---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const permissionGrantPolicy = {
  displayName: 'Custom permission grant policy'
};

await client.api('/policies/permissionGrantPolicies/my-custom-consent-policy')
	.version('beta')
	.update(permissionGrantPolicy);

```