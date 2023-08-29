---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const permissionGrantPolicy = {
  id: 'my-custom-consent-policy',
  displayName: 'Custom application consent policy',
  description: 'A custom permission grant policy to customize conditions for granting consent.'
};

await client.api('/policies/permissionGrantPolicies')
	.version('beta')
	.post(permissionGrantPolicy);

```