---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let connectionOperation = await client.api('/external/connections/contosohr/operations/3ed1595a-4bae-43c2-acda-ef973e581323')
	.version('beta')
	.get();

```