---
description: "Automatically generated file. DO NOT MODIFY"
---

```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc users messages create --user-id {user-id} --body '{\
    "subject":"Did you see last night's game?",\
    "importance":"Low",\
    "body":{\
        "contentType":"HTML",\
        "content":"They were <b>awesome</b>!"\
    },\
    "toRecipients":[\
        {\
            "emailAddress":{\
                "address":"AdeleV@contoso.onmicrosoft.com"\
            }\
        }\
    ]\
}\
'

```