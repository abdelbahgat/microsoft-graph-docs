---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewExportPostRequestBody()
outputName := "Export reviewset query via API"
requestBody.SetOutputName(&outputName) 
description := "Export for the Contoso investigation 2"
requestBody.SetDescription(&description) 
exportOptions := graphmodels.ORIGINALFILES,FILEINFO,TAGS_EXPORTOPTIONS 
requestBody.SetExportOptions(&exportOptions) 
exportStructure := graphmodels.DIRECTORY_EXPORTFILESTRUCTURE 
requestBody.SetExportStructure(&exportStructure) 

graphClient.Security().Cases().EdiscoveryCasesById("ediscoveryCase-id").ReviewSetsById("ediscoveryReviewSet-id").QueriesById("ediscoveryReviewSetQuery-id").Export(ediscoveryCase-id, ediscoveryReviewSet-id, ediscoveryReviewSetQuery-id).Post(requestBody)


```