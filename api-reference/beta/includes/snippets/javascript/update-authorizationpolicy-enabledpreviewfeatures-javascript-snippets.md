---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const authorizationPolicy = {
   enabledPreviewFeatures: [
      'assignGroupsToRoles'
   ]
};

await client.api('/policies/authorizationPolicy/authorizationPolicy')
	.version('beta')
	.update(authorizationPolicy);

```