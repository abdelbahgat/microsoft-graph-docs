---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let appliesTo = await client.api('/policies/appManagementPolicies/{id}/appliesTo')
	.select('id,appId,displayName,createdDateTime')
	.get();

```