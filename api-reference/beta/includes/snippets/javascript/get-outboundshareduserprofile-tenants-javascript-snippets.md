---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let tenants = await client.api('/directory/outboundSharedUserProfiles/c228b2ae-c4fb-4eda-9620-7e73dddd1cac/tenants')
	.version('beta')
	.get();

```