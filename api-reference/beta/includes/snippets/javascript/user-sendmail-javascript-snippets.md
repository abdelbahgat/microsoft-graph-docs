---
description: "Automatically generated file. DO NOT MODIFY"
---

```javascript

const options = {
	authProvider,
};

const client = Client.init(options);

const sendMail = {
  message: {
    subject: 'Meet for lunch?',
    body: {
      contentType: 'Text',
      content: 'The new cafeteria is open.'
    },
    toRecipients: [
      {
        emailAddress: {
          address: 'samanthab@contoso.onmicrosoft.com'
        }
      }
    ],
    ccRecipients: [
      {
        emailAddress: {
          address: 'danas@contoso.onmicrosoft.com'
        }
      }
    ]
  },
  saveToSentItems: 'false'
};

await client.api('/me/sendMail')
	.version('beta')
	.post(sendMail);

```