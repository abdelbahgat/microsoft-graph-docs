---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let outlookTaskGroup = await client.api('/me/outlook/taskGroups/AAMkADIyAAAhrbe-AAA=')
	.version('beta')
	.get();

```