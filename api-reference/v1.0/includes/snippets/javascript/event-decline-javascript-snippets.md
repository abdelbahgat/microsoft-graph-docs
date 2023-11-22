---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const decline = {
  comment: 'I won\'t be able to make this week. How about next week?',
  sendResponse: true,
  proposedNewTime: {
      start: { 
          dateTime: '2019-12-02T18:00:00', 
          timeZone: 'Pacific Standard Time' 
      }, 
      end: { 
          dateTime: '2019-12-02T19:00:00', 
          timeZone: 'Pacific Standard Time' 
      }     
  }
};

await client.api('/me/events/{id}/decline')
	.post(decline);

```