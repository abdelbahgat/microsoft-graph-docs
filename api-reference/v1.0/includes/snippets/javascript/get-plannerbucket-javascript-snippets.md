---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let plannerBucket = await client.api('/planner/buckets/{bucket-id}')
	.get();

```