---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let auditEvent = await client.api('/tenantRelationships/managedTenants/auditEvent')
	.version('beta')
	.get();

```