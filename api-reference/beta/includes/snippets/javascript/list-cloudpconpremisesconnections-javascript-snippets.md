---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let onPremisesConnections = await client.api('/deviceManagement/virtualEndpoint/onPremisesConnections')
	.version('beta')
	.get();

```