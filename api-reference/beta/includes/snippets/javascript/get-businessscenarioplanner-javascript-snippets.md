---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let businessScenarioPlanner = await client.api('/solutions/businessScenarios/c5d514e6c6864911ac46c720affb6e4d/planner')
	.version('beta')
	.get();

```