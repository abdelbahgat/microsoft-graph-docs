---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let group = await client.api('/groups/{id}/transitiveMembers/microsoft.graph.group')
	.header('ConsistencyLevel','eventual')
	.get();

```