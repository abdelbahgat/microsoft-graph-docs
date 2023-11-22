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


requestBody := graphmodels.NewAuthenticationMethodsPolicy()
registrationEnforcement := graphmodels.NewRegistrationEnforcement()
authenticationMethodsRegistrationCampaign := graphmodels.NewAuthenticationMethodsRegistrationCampaign()
snoozeDurationInDays := int32(1)
authenticationMethodsRegistrationCampaign.SetSnoozeDurationInDays(&snoozeDurationInDays) 
enforceRegistrationAfterAllowedSnoozes := true
authenticationMethodsRegistrationCampaign.SetEnforceRegistrationAfterAllowedSnoozes(&enforceRegistrationAfterAllowedSnoozes) 
state := graphmodels.ENABLED_ADVANCEDCONFIGSTATE 
authenticationMethodsRegistrationCampaign.SetState(&state) 
excludeTargets := []graphmodels.ExcludeTargetable {

}
authenticationMethodsRegistrationCampaign.SetExcludeTargets(excludeTargets)


authenticationMethodsRegistrationCampaignIncludeTarget := graphmodels.NewAuthenticationMethodsRegistrationCampaignIncludeTarget()
id := "3ee3a9de-0a86-4e12-a287-9769accf1ba2"
authenticationMethodsRegistrationCampaignIncludeTarget.SetId(&id) 
targetType := graphmodels.GROUP_AUTHENTICATIONMETHODTARGETTYPE 
authenticationMethodsRegistrationCampaignIncludeTarget.SetTargetType(&targetType) 
targetedAuthenticationMethod := "microsoftAuthenticator"
authenticationMethodsRegistrationCampaignIncludeTarget.SetTargetedAuthenticationMethod(&targetedAuthenticationMethod) 

includeTargets := []graphmodels.AuthenticationMethodsRegistrationCampaignIncludeTargetable {
	authenticationMethodsRegistrationCampaignIncludeTarget,
}
authenticationMethodsRegistrationCampaign.SetIncludeTargets(includeTargets)
registrationEnforcement.SetAuthenticationMethodsRegistrationCampaign(authenticationMethodsRegistrationCampaign)
requestBody.SetRegistrationEnforcement(registrationEnforcement)
reportSuspiciousActivitySettings := graphmodels.NewReportSuspiciousActivitySettings()
state := graphmodels.ENABLED_ADVANCEDCONFIGSTATE 
reportSuspiciousActivitySettings.SetState(&state) 
includeTarget := graphmodels.NewIncludeTarget()
targetType := graphmodels.GROUP_AUTHENTICATIONMETHODTARGETTYPE 
includeTarget.SetTargetType(&targetType) 
id := "all_users"
includeTarget.SetId(&id) 
reportSuspiciousActivitySettings.SetIncludeTarget(includeTarget)
voiceReportingCode := int32(0)
reportSuspiciousActivitySettings.SetVoiceReportingCode(&voiceReportingCode) 
requestBody.SetReportSuspiciousActivitySettings(reportSuspiciousActivitySettings)

authenticationMethodsPolicy, err := graphClient.Policies().AuthenticationMethodsPolicy().Patch(context.Background(), requestBody, nil)


```