---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const attachment = {
    '@odata.type': '#microsoft.graph.fileAttachment',
    name: 'menu.txt',
    contentBytes: 'base64bWFjIGFuZCBjaGVlc2UgdG9kYXk='   
};

await client.api('/me/events/AAMkAGI1AAAt9AHjAAA=/attachments')
	.post(attachment);

```