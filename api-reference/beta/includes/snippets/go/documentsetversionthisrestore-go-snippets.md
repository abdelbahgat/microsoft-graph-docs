---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)


graphClient.SitesById("site-id").ListsById("list-id").ItemsById("listItem-id").DocumentSetVersionsById("documentSetVersion-id").Restore(site-id, list-id, listItem-id, documentSetVersion-id).Post()


```