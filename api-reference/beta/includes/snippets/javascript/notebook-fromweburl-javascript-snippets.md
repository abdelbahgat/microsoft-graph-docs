---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const copyNotebookModel = {webUrl: 'webUrl value'};

await client.api('/me/onenote/notebooks/GetNotebookFromWebUrl')
	.version('beta')
	.post(copyNotebookModel);

```