---
description: "Automatically generated file. DO NOT MODIFY"
---

```bash

// THE CLI IS IN PREVIEW. NON-PRODUCTION USE ONLY
mgc users get --user-id {user-id} --select "id,displayName" --expand "manager(\$levels=max;\$select=id,displayName)" --consistency-level "eventual"

```