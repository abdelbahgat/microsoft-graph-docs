---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)


graphClient.Security().Cases().EdiscoveryCasesById("ediscoveryCase-id").NoncustodialDataSourcesById("ediscoveryNoncustodialDataSource-id").ApplyHold(ediscoveryCase-id, ediscoveryNoncustodialDataSource-id).Post()


```