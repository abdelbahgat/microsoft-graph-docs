---
description: "Automatically generated file. DO NOT MODIFY"
---

```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc groups threads posts reply post --group-id {group-id} --conversation-thread-id {conversationThread-id} --post-id {post-id} --body '{\
  "post": {\
    "body": {\
      "contentType": "",\
      "content": "content-value"\
    },\
    "receivedDateTime": "datetime-value",\
    "hasAttachments": true,\
    "from": {\
      "emailAddress": {\
        "name": "name-value",\
        "address": "address-value"\
      }\
    },\
    "sender": {\
      "emailAddress": {\
        "name": "name-value",\
        "address": "address-value"\
      }\
    },\
    "conversationThreadId": "conversationThreadId-value",\
    "newParticipants": [\
      {\
        "emailAddress": {\
          "name": "name-value",\
          "address": "address-value"\
        }\
      }\
    ],\
    "conversationId": "conversationId-value",\
    "createdDateTime": "datetime-value",\
    "lastModifiedDateTime": "datetime-value",\
    "changeKey": "changeKey-value",\
    "categories": [\
      "categories-value"\
    ],\
    "id": "id-value",\
    "inReplyTo": {\
    },\
    "attachments": [\
      {\
        "@odata.type": "#microsoft.graph.fileAttachment",\
        "lastModifiedDateTime": "datetime-value",\
        "name": "name-value",\
        "contentType": "contentType-value",\
        "size": 99,\
        "isInline": true,\
        "id": "id-value"\
      }\
    ]\
  }\
}\
'

```