---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const identitySecurityDefaultsEnforcementPolicy = {
  isEnabled: false
};

await client.api('/policies/identitySecurityDefaultsEnforcementPolicy')
	.update(identitySecurityDefaultsEnforcementPolicy);

```