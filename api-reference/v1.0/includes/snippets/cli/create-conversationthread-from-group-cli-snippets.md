---
description: "Automatically generated file. DO NOT MODIFY"
---

```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc groups threads create --group-id {group-id} --body '{\
  "topic": "New Conversation Thread Topic",\
  "posts": [{\
    "body": {\
      "contentType": "html",\
      "content": "this is body content"\
    },\
    "newParticipants": [{\
      "emailAddress": {\
        "name": "Alex Darrow",\
        "address": "alexd@contoso.com"\
      }\
    }]\
  }]\
}\
'

```