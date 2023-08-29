---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const bookingService = {
    '@odata.type':'#microsoft.graph.bookingService',
    defaultDuration: 'PT30M'
};

await client.api('/bookingBusinesses/Contosolunchdelivery@contoso.onmicrosoft.com/services/57da6774-a087-4d69-b0e6-6fb82c339976')
	.version('beta')
	.update(bookingService);

```