---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

let bookingCustomer = await client.api('/bookingBusinesses/contosolunchdelivery@contoso.onmicrosoft.com/customers/8bb19078-0f45-4efb-b2c5-da78b860f73a')
	.version('beta')
	.get();

```