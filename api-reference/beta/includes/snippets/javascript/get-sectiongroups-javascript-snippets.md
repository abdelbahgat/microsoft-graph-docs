---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let sectionGroups = await client.api('/me/onenote/sectionGroups/{id}/sectionGroups')
	.version('beta')
	.get();

```