---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const onlineMeeting = {
  startDateTime: '2020-09-09T14:33:30.8546353-07:00',
  endDateTime: '2020-09-09T15:03:30.8566356-07:00',
  subject: 'Patch Meeting Subject'
};

await client.api('/me/onlineMeetings/MSpkYzE3Njc0Yy04MWQ5LTRhZGItYmZi')
	.update(onlineMeeting);

```