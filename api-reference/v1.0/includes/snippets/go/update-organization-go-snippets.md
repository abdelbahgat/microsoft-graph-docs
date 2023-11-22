---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewOrganization()
marketingNotificationEmails := []string {
	"marketing@contoso.com",
}
requestBody.SetMarketingNotificationEmails(marketingNotificationEmails)
privacyProfile := graphmodels.NewPrivacyProfile()
contactEmail := "alice@contoso.com"
privacyProfile.SetContactEmail(&contactEmail) 
statementUrl := "https://contoso.com/privacyStatement"
privacyProfile.SetStatementUrl(&statementUrl) 
requestBody.SetPrivacyProfile(privacyProfile)
securityComplianceNotificationMails := []string {
	"security@contoso.com",
}
requestBody.SetSecurityComplianceNotificationMails(securityComplianceNotificationMails)
securityComplianceNotificationPhones := []string {
	"(123) 456-7890",
}
requestBody.SetSecurityComplianceNotificationPhones(securityComplianceNotificationPhones)
technicalNotificationMails := []string {
	"tech@contoso.com",
}
requestBody.SetTechnicalNotificationMails(technicalNotificationMails)

organization, err := graphClient.Organization().ByOrganizationId("organization-id").Patch(context.Background(), requestBody, nil)


```