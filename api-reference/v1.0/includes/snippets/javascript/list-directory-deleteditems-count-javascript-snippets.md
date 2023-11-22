---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let group = await client.api('/directory/deletedItems/microsoft.graph.group')
	.header('ConsistencyLevel','eventual')
	.select('id,displayName,deletedDateTime')
	.orderby('deletedDateTime asc')
	.get();

```