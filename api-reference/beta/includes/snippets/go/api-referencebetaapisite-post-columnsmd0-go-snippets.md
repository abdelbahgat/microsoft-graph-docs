---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewColumnDefinition()
description := "test"
requestBody.SetDescription(&description) 
enforceUniqueValues := false
requestBody.SetEnforceUniqueValues(&enforceUniqueValues) 
hidden := false
requestBody.SetHidden(&hidden) 
indexed := false
requestBody.SetIndexed(&indexed) 
name := "Title"
requestBody.SetName(&name) 
text := graphmodels.NewTextColumn()
allowMultipleLines := false
text.SetAllowMultipleLines(&allowMultipleLines) 
appendChangesToExistingText := false
text.SetAppendChangesToExistingText(&appendChangesToExistingText) 
linesForEditing := int32(0)
text.SetLinesForEditing(&linesForEditing) 
maxLength := int32(255)
text.SetMaxLength(&maxLength) 
requestBody.SetText(text)

result, err := graphClient.SitesById("site-id").Columns().Post(requestBody)


```