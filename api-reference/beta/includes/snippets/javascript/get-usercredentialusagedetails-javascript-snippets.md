---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let userCredentialUsageDetails = await client.api('/reports/userCredentialUsageDetails')
	.version('beta')
	.get();

```