---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let event = await client.api('/me/events/AAMkADAGAADDdm4NAAA=/')
	.version('beta')
	.select('subject,body,bodyPreview,organizer,attendees,start,end,location,locations')
	.get();

```