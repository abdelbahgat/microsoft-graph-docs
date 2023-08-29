---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewConditionalAccessPolicy()
displayName := "Demo app for documentation"
requestBody.SetDisplayName(&displayName) 
state := graphmodels.DISABLED_CONDITIONALACCESSPOLICYSTATE 
requestBody.SetState(&state) 
conditions := graphmodels.NewConditionalAccessConditionSet()
signInRiskLevels := []graphmodels.RiskLevelable {
	"high",
	"medium",

}
conditions.SetSignInRiskLevels(signInRiskLevels)
clientAppTypes := []graphmodels.ConditionalAccessClientAppable {
	"mobileAppsAndDesktopClients",
	"exchangeActiveSync",
	"other",

}
conditions.SetClientAppTypes(clientAppTypes)
applications := graphmodels.NewConditionalAccessApplications()
includeApplications := []String {
	"All",

}
applications.SetIncludeApplications(includeApplications)
excludeApplications := []String {
	"499b84ac-1321-427f-aa17-267ca6975798",
	"00000007-0000-0000-c000-000000000000",
	"de8bc8b5-d9f9-48b1-a8ad-b748da725064",
	"00000012-0000-0000-c000-000000000000",
	"797f4846-ba00-4fd7-ba43-dac1f8f63013",
	"05a65629-4c1b-48c1-a78b-804c4abdd4af",
	"7df0a125-d3be-4c96-aa54-591f83ff541c",

}
applications.SetExcludeApplications(excludeApplications)
includeUserActions := []string {

}
applications.SetIncludeUserActions(includeUserActions)
conditions.SetApplications(applications)
users := graphmodels.NewConditionalAccessUsers()
includeUsers := []String {
	"a702a13d-a437-4a07-8a7e-8c052de62dfd",

}
users.SetIncludeUsers(includeUsers)
excludeUsers := []String {
	"124c5b6a-ffa5-483a-9b88-04c3fce5574a",
	"GuestsOrExternalUsers",

}
users.SetExcludeUsers(excludeUsers)
includeGroups := []string {

}
users.SetIncludeGroups(includeGroups)
excludeGroups := []string {

}
users.SetExcludeGroups(excludeGroups)
includeRoles := []String {
	"9b895d92-2cd3-44c7-9d02-a6ac2d5ea5c3",
	"cf1c38e5-3621-4004-a7cb-879624dced7c",
	"c4e39bd9-1100-46d3-8c65-fb160da0071f",

}
users.SetIncludeRoles(includeRoles)
excludeRoles := []String {
	"b0f54661-2d74-4c50-afa3-1ec803f12efe",

}
users.SetExcludeRoles(excludeRoles)
conditions.SetUsers(users)
platforms := graphmodels.NewConditionalAccessPlatforms()
includePlatforms := []graphmodels.ConditionalAccessDevicePlatformable {
	"all",

}
platforms.SetIncludePlatforms(includePlatforms)
excludePlatforms := []graphmodels.ConditionalAccessDevicePlatformable {
	"iOS",
	"windowsPhone",

}
platforms.SetExcludePlatforms(excludePlatforms)
conditions.SetPlatforms(platforms)
locations := graphmodels.NewConditionalAccessLocations()
includeLocations := []String {
	"AllTrusted",

}
locations.SetIncludeLocations(includeLocations)
excludeLocations := []String {
	"00000000-0000-0000-0000-000000000000",
	"d2136c9c-b049-47ae-b9cf-316e04ef7198",

}
locations.SetExcludeLocations(excludeLocations)
conditions.SetLocations(locations)
requestBody.SetConditions(conditions)
grantControls := graphmodels.NewConditionalAccessGrantControls()
operator := "OR"
grantControls.SetOperator(&operator) 
builtInControls := []graphmodels.ConditionalAccessGrantControlable {
	"mfa",
	"compliantDevice",
	"domainJoinedDevice",
	"approvedApplication",
	"compliantApplication",

}
grantControls.SetBuiltInControls(builtInControls)
customAuthenticationFactors := []string {

}
grantControls.SetCustomAuthenticationFactors(customAuthenticationFactors)
termsOfUse := []String {
	"ce580154-086a-40fd-91df-8a60abac81a0",
	"7f29d675-caff-43e1-8a53-1b8516ed2075",

}
grantControls.SetTermsOfUse(termsOfUse)
requestBody.SetGrantControls(grantControls)
sessionControls := graphmodels.NewConditionalAccessSessionControls()
applicationEnforcedRestrictions := null
sessionControls.SetApplicationEnforcedRestrictions(&applicationEnforcedRestrictions) 
persistentBrowser := null
sessionControls.SetPersistentBrowser(&persistentBrowser) 
cloudAppSecurity := graphmodels.NewcloudAppSecurity()
cloudAppSecurityType := graphmodels.BLOCKDOWNLOADS_CLOUDAPPSECURITYSESSIONCONTROLTYPE 
cloudAppSecurity.SetCloudAppSecurityType(&cloudAppSecurityType) 
isEnabled := true
cloudAppSecurity.SetIsEnabled(&isEnabled) 
sessionControls.SetCloudAppSecurity(cloudAppSecurity)
signInFrequency := graphmodels.NewsignInFrequency()
value := int32(4)
signInFrequency.SetValue(&value) 
type := graphmodels.HOURS_SIGNINFREQUENCYTYPE 
signInFrequency.SetType(&type) 
isEnabled := true
signInFrequency.SetIsEnabled(&isEnabled) 
sessionControls.SetSignInFrequency(signInFrequency)
requestBody.SetSessionControls(sessionControls)

result, err := graphClient.Identity().ConditionalAccess().Policies().Post(requestBody)


```