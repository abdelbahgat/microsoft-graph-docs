---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

await client.api('/policies/crossTenantAccessPolicy/templates/multiTenantOrganizationIdentitySynchronization/resetToDefaultSettings')
	.version('beta')
	.post();

```