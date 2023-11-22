---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewAgreement()
displayName := "Contoso ToU for guest users"
requestBody.SetDisplayName(&displayName) 
isViewingBeforeAcceptanceRequired := true
requestBody.SetIsViewingBeforeAcceptanceRequired(&isViewingBeforeAcceptanceRequired) 


agreementFileLocalization := graphmodels.NewAgreementFileLocalization()
fileName := "TOU.pdf"
agreementFileLocalization.SetFileName(&fileName) 
language := "en"
agreementFileLocalization.SetLanguage(&language) 
isDefault := true
agreementFileLocalization.SetIsDefault(&isDefault) 
fileData := graphmodels.NewAgreementFileData()
data := []byte("sGVsbG8gd29ybGQ=//truncated-binary")
fileData.SetData(&data) 
agreementFileLocalization.SetFileData(fileData)

files := []graphmodels.AgreementFileLocalizationable {
	agreementFileLocalization,
}
requestBody.SetFiles(files)

agreements, err := graphClient.IdentityGovernance().TermsOfUse().Agreements().Post(context.Background(), requestBody, nil)


```