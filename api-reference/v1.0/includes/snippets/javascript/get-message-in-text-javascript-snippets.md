---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let message = await client.api('/me/messages/AAMkAGI1AAAoZCfHAAA=/')
	.header('Prefer','outlook.body-content-type="text"')
	.select('subject,body,bodyPreview,uniqueBody')
	.get();

```