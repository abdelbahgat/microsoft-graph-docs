---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let accessPackageAssignmentResourceRole = await client.api('/identityGovernance/entitlementManagement/accessPackageAssignmentResourceRoles/{id}')
	.version('beta')
	.get();

```