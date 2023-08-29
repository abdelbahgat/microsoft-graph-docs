---
title: "Enum values"
description: "Microsoft Graph enumeration values"
doc_type: enumPageType
ms.localizationpriority: medium
ms.prod: "non-product-specific"
author: "MSGraphDocsvTeam"
---

# Enum values

Namespace: microsoft.graph


### teamTemplateAudience values 

|Member|
|:---|
|organization|
|user|
|public|
|unknownFutureValue|

### decisionItemPrincipalResourceMembershipType values 

|Member|
|:---|
|direct|
|indirect|
|unknownFutureValue|

### signInFrequencyAuthenticationType values

|Member|
|:---|
|primaryAndSecondaryAuthentication|
|secondaryAuthentication|
|unknownFutureValue|

### signInFrequencyInterval values

|Member|
|:---|
|timeBased|
|everyTime|

#### authenticationProtocol values

|Member|
|:---|
|wsFed|
|saml|
|unknownFutureValue|

#### federatedIdpMfaBehavior values
|Member|
|:---|
|acceptIfMfaDoneByFederatedIdp|
|enforceMfaByFederatedIdp|
|rejectMfaByFederatedIdp|
|unknownFutureValue|

#### promptLoginBehavior values
|Member|
|:---|
|translateToFreshPasswordAuthentication|
|nativeSupport|
|disabled|
|unknownFutureValue|

### bookingsAvailabilityStatus values

|Member|
|:-----|
|available|
|busy|
|slotsAvailable|
|outOfOffice|
|unknownFutureValue|

### accessPackageCustomExtensionHandlerStatus values 

|Member|
|:---|
|requestSent|
|requestReceived|
|unknownFutureValue|

### accessPackageCustomExtensionStage values 

|Member|
|:---|
|assignmentRequestCreated|
|assignmentRequestApproved|
|assignmentRequestGranted|
|assignmentRequestRemoved|
|assignmentFourteenDaysBeforeExpiration|
|assignmentOneDayBeforeExpiration|
|unknownFutureValue|

### accessReviewHistoryStatus values

| Member|
|:-----------------|
|done|
|inprogress|
|error|
|requested|
|unknownFutureValue|

### accessReviewHistoryDecisionFilter values

| Member|
|:-----------------|
|approve|
|deny|
|notReviewed|
|dontKnow|
|notNotified|
|unknownFutureValue|


### accessReviewHistoryStatus values

|Member|
|:---|
|done|
|inprogress|
|error|
|requested|
|unknownFutureValue|

### crossTenantAccessPolicyTargetConfigurationAccessType values

|Member|
|:---|
|allowed|
|blocked|
|unknownFutureValue|

### crossTenantAccessPolicyTargetType values

|Member|
|:---|
|user|
|group|

### accessPackageFilterByCurrentUserOptions values

|Member|
|:---|
|allowedRequestor|
|unknownFutureValue|

### userSignInRecommendationScope values 

|Member|
|:---|
|tenant|
|application|

### incomingTokenType values 

|Member|
|:---|
|none|
|primaryRefreshToken|
|saml11|
|saml20|
|unknownFutureValue|
|remoteDesktopToken|

### protocolType values 

|Member|
|:---|
|none|
|oAuth2|
|ropc|
|wsFederation|
|saml20|
|deviceCode|
|unknownFutureValue|

### accessReviewInstanceDecisionItemFilterByCurrentUserOptions values 

|Member|
|:---|
|reviewer|
|unknownFutureValue|

### accessReviewStageFilterByCurrentUserOptions values 

|Member|
|:---|
|reviewer|
|unknownFutureValue|

### continuousAccessEvaluationMode values 

|Member|
|:---|
|strictEnforcement|
|disabled|
|unknownFutureValue|

### multiFactorAuthConfiguration values

| Member             | Value | Description |
|:-------------------|:------| :------|
| notRequired        | 0     | No multifactor authentication is required for a user to complete device registration.|
| required           | 1     | Multifactor authentication is required for a user to complete device registration.|
| unknownFutureValue | 2     | Evolvable enumeration sentinel value. Do not use.|

### policyScope values

| Member             | Value | Description |
|:-------------------|:------| :------|
| none               | 0     | The policy does not apply to any users or groups in the organization. |
| all                | 1     | The policy applies to all users and groups in the organization. Default value. |
| selected           | 2     | The policy applies to specific users or groups in the organization. |
| unknownFutureValue | 3     | Evolvable enumeration sentinel value. Do not use. |

### appCredentialRestrictionType values

| Member                 |
| :--------------------- |
| passwordAddition       |
| passwordLifetime       |
| symmetricKeyAddition   |
| symmetricKeyLifetime   |
| customPasswordAddition |
| unknownFutureValue     |

### appKeyCredentialRestrictionType values

|Member|
|:-----|
|asymmetricKeyLifetime|
|unknownFutureValue|

### synchronizationSecret values

|Member|
|:----|
|None|
|UserName|
|Password|
|SecretToken|
|AppKey|
|BaseAddress|
|ClientIdentifier|
|ClientSecret|
|SingleSignOnType|
|Sandbox|
|Url|
|Domain|
|ConsumerKey|
|ConsumerSecret|
|TokenKey|
|TokenExpiration|
|Oauth2AccessToken|
|Oauth2AccessTokenCreationTime|
|Oauth2RefreshToken|
|SyncAll|
|InstanceName|
|Oauth2ClientId|
|Oauth2ClientSecret|
|CompanyId|
|UpdateKeyOnSoftDelete|
|SynchronizationSchedule|
|SystemOfRecord|
|SandboxName|
|EnforceDomain|
|SyncNotificationSettings|
|SkipOutOfScopeDeletions|
|Oauth2AuthorizationCode|
|Oauth2RedirectUri|
|ApplicationTemplateIdentifier|
|Server|
|PerformInboundEntitlementGrants|
|HardDeletesEnabled|
|SyncAgentCompatibilityKey|
|SyncAgentADContainer|
|ValidateDomain|
|TestReferences|

### filterMode values

|Member|
|:---|
|include|
|exclude|

### lifecycleEventType values

|Member|
|:---|
|missed|
|subscriptionRemoved|
|reauthorizationRequired|

### changeType values

|Member|
|:---|
|created|
|updated|
|deleted|


### countryLookupMethodType values

|Member|
|:---|
|clientIpAddress|
|authenticatorAppGps|

### approvalState values

|Member|
|:---|
|pending|
|approved|
|denied|
|aborted|
|canceled|

### roleSummaryStatus values

|Member|
|:---|
|ok|
|bad|

### dataPolicyOperationStatus values

|Member|
|:---|
|notStarted|
|running|
|complete|
|failed|
|unknownFutureValue|

### conditionalAccessClientApp values

|Member|
|:---|
|all|
|browser|
|mobileAppsAndDesktopClients|
|exchangeActiveSync|
|easSupported|
|other|

### consentRequestFilterByCurrentUserOptions values

|Member|
|:---|
|reviewer|
|unknownFutureValue|

### attributeType values

|Member|
|:---|
|String|
|Integer|
|Reference|
|Binary|
|Boolean|
|DateTime|

### mutability values

|Member|
|:---|
|ReadWrite|
|ReadOnly|
|Immutable|
|WriteOnly|

### directoryDefinitionDiscoverabilities values

|Member|
|:---|
|None|
|AttributeNames|
|AttributeDataTypes|
|AttributeReadOnly|
|ReferenceAttributes|
|UnknownFutureValue|

### connectorGroupRegion values

|Member|
|:---|
|nam|
|eur|
|aus|
|asia|
|ind|
|unknownFutureValue|

### connectorGroupType values

|Member|
|:---|
|applicationProxy|

### onPremisesPublishingType values

|Member|
|:---|
|applicationProxy|
|exchangeOnline|
|authentication|
|provisioning|
|intunePfx|
|oflineDomainJoin|
|unknownFutureValue|

### agentStatus values

|Member|
|:---|
|active|
|inactive|

### connectorStatus values

|Member|
|:---|
|active|
|inactive|

### callType values

|Member|
|:---|
|unknown|
|groupCall|
|peerToPeer|
|unknownFutureValue|

### tone values

|Member|
|:---|
|tone0|
|tone1|
|tone2|
|tone3|
|tone4|
|tone5|
|tone6|
|tone7|
|tone8|
|tone9|
|star|
|pound|
|a|
|b|
|c|
|d|
|flash|

### callState values

|Member|
|:---|
|incoming|
|establishing|
|ringing|
|established|
|hold|
|transferring|
|transferAccepted|
|redirecting|
|terminating|
|terminated|

### routingPolicy values

|Member|
|:---|
|none|
|noMissedCall|
|disableForwardingExceptPhone|
|disableForwarding|
|preferSkypeForBusiness|
|unknownFutureValue|

### meetingCapabilities values

|Member|
|:---|
|questionAndAnswer|
|unknownFutureValue|

### onlineMeetingRole values

|Member|
|:---|
|attendee|
|presenter|
|producer|
|unknownFutureValue|

### autoAdmittedUsersType values

|Member|
|:---|
|everyoneInCompany|
|everyone|

### mediaState values

|Member|
|:---|
|active|
|inactive|
|unknownFutureValue|

### callDirection values

|Member|
|:---|
|incoming|
|outgoing|

### modality values

|Member|
|:---|
|audio|
|video|
|videoBasedScreenSharing|
|data|
|screenSharing|
|unknownFutureValue|

### endpointType values

|Member|
|:---|
|default|
|voicemail|
|skypeForBusiness|
|skypeForBusinessVoipPhone|
|unknownFutureValue|

### kerberosSignOnMappingAttributeType values

|Member|
|:---|
|userPrincipalName|
|onPremisesUserPrincipalName|
|userPrincipalUsername|
|onPremisesUserPrincipalUsername|
|onPremisesSAMAccountName|

### externalAuthenticationType values

|Member|
|:---|
|passthru|
|aadPreAuthentication|

### recipientScopeType values
|Member|
|:---|
|none|
|internal|
|external|
|externalPartner|
|externalNonPartner|

### appliedConditionalAccessPolicyResult values

|Member|
|:---|
|success|
|failure|
|notApplied|
|notEnabled|
|unknown|
|unknownFutureValue|
|reportOnlySuccess|
|reportOnlyFailure|
|reportOnlyNotApplied|
|reportOnlyInterrupted|


### microsoftAuthenticatorAuthenticationMode values



|Member|
|:---|
|any|
|push|
|deviceBasedPush|


### authenticationMethodFeature values

|Member|
|:---|
|ssprRegistered|
|ssprEnabled|
|ssprCapable|
|passwordlessCapable|
|mfaCapable|


### authMethodsType values

|Member|
|:---|
|email|
|mobileSMS|
|mobilePhone|
|officePhone|
|securityQuestion|
|appNotification|
|appNotificationCode|
|appNotificationAndCode|
|appPassword|
|fido|
|alternateMobilePhone|
|mobilePhoneAndSMS|
|unknownFutureValue|


### defaultMfaMethodType values 



|Member|
|:---|
|none|
|mobilePhone|
|alternateMobilePhone|
|officePhone|
|microsoftAuthenticatorPush|
|softwareOneTimePasscode|
|unknownFutureValue|


### clientCredentialType values 



|Member|
|:---|
|none|
|clientSecret|
|clientAssertion|
|federatedIdentityCredential|
|managedIdentity|
|certificate|
|unknownFutureValue|


### azureADLicenseType values

|Member|
|:---|
|none|
|free|
|basic|
|premiumP1|
|premiumP2|
|unknownFutureValue|

### conditionalAccessConditions values

|Member|
|:---|
|none|
|application|
|users|
|devicePlatform|
|location|
|clientType|
|signInRisk|
|userRisk|
|time|
|deviceState|
|client|
|ipAddressSeenByAzureAD|
|ipAddressSeenByResourceProvider|
|unknownFutureValue|
|servicePrincipals|
|servicePrincipalRisk|

### conditionalAccessStatus values

|Member|
|:---|
|success|
|failure|
|notApplied|
|unknownFutureValue|

### featureType values

|Member|
|:---|
|registration|
|reset|
|unknownFutureValue|

### groupType values

|Member|
|:---|
|unifiedGroups|
|azureAD|
|unknownFutureValue|

### includedUserRoles values

|Member|
|:---|
|all|
|privilegedAdmin|
|admin|
|user|
|unknownFutureValue|

### includedUserTypes values

|Member|
|:---|
|all|
|member|
|guest|
|unknownFutureValue|

### initiatorType values

|Member|
|:---|
|user|
|app|
|system|
|unknownFutureValue|

### migrationStatus values

|Member|
|:---|
|ready|
|needsReview|
|additionalStepsRequired|
|unknownFutureValue|

### networkType values

|Member|
|:---|
|intranet|
|extranet|
|namedNetwork|
|trusted|
|unknownFutureValue|

### operationResult values

|Member|
|:---|
|success|
|failure|
|timeout|
|unknownFutureValue|

### provisioningResult values

|Member|
|:---|
|success|
|failure|
|skipped|
|warning|
|unknownFutureValue|

### provisioningStepType values

|Member|
|:---|
|import|
|scoping|
|matching|
|processing|
|referenceResolution|
|export|
|unknownFutureValue|

### registrationAuthMethod values

|Member|
|:---|
|email|
|mobilePhone|
|officePhone|
|securityQuestion|
|appNotification|
|appCode|
|alternateMobilePhone|
|fido|
|appPassword|
|unknownFutureValue|

### registrationStatusType values

|Member|
|:---|
|registered|
|enabled|
|capable|
|mfaRegistered|
|unknownFutureValue|


### signInIdentifierType values 

|Member|
|:---|
|userPrincipalName|
|phoneNumber|
|proxyAddress|
|qrCode|
|onPremisesUserPrincipalName|
|unknownFutureValue|


### signInUserType values 

|Member|
|:---|
|member|
|guest|
|unknownFutureValue|

### requirementProvider values 


|Member|
|:---|
|user|
|request|
|servicePrincipal|
|v1ConditionalAccess|
|multiConditionalAccess|
|tenantSessionRiskPolicy|
|accountCompromisePolicies|
|v1ConditionalAccessDependency|
|v1ConditionalAccessPolicyIdRequested|
|mfaRegistrationRequiredByIdentityProtectionPolicy|
|baselineProtection|
|mfaRegistrationRequiredByBaselineProtection|
|mfaRegistrationRequiredByMultiConditionalAccess|
|enforcedForCspAdmins|
|securityDefaults|
|mfaRegistrationRequiredBySecurityDefaults|
|proofUpCodeRequest|
|crossTenantOutboundRule|
|gpsLocationCondition|
|riskBasedPolicy|
|unknownFutureValue|


### riskDetail values

|Member|
|:---|
|none|
|internal|
|external|
|externalPartner|
|externalNonPartner|
|adminGeneratedTemporaryPassword|
|userPerformedSecuredPasswordChange|
|userPerformedSecuredPasswordReset|
|adminConfirmedSigninSafe|
|aiConfirmedSigninSafe|
|userPassedMFADrivenByRiskBasedPolicy|
|adminDismissedAllRiskForUser|
|adminConfirmedSigninCompromised|
|hidden|
|adminConfirmedUserCompromised|
|unknownFutureValue|
|adminConfirmedServicePrincipalCompromised|
|adminDismissedAllRiskForServicePrincipal|


<!-- maintenance comment: Do not delete enum delcaration for riskEventType until all properties of this type are marked as deleted. Dec 28, 2021: Pending eventTypes (in riskUserActivity) and riskType (in riskDetection)-->
### riskEventType values

|Member|
|:---|
|unlikelyTravel|
|anonymizedIPAddress|
|maliciousIPAddress|
|unfamiliarFeatures|
|malwareInfectedIPAddress|
|suspiciousIPAddress|
|leakedCredentials|
|investigationsThreatIntelligence|
|generic|
|adminConfirmedUserCompromised|
|mcasImpossibleTravel|
|mcasSuspiciousInboxManipulationRules|
|investigationsThreatIntelligenceSigninLinked|
|maliciousIPAddressValidCredentialsBlockedIP|
|unknownFutureValue|

### usageAuthMethod values

|Member|
|:---|
|email|
|mobileSMS|
|mobileCall|
|officePhone|
|securityQuestion|
|appNotification|
|appCode|
|alternateMobileCall|
|fido|
|appPassword|
|unknownFutureValue|

### authenticationMethodKeyStrength values

|Member|
|:---|
|normal|
|weak|
|unknown|

### authenticationContextDetail values

|Member|
|:---|
|required|
|previouslySatisfied|
|notApplicable|
|unknownFutureValue|

### educationAddedStudentAction values

|Member|
|:---|
|none|
|assignIfOpen|
|unknownFutureValue|

### educationAddToCalendarOptions values
|Member|
|:---|
|none|
|studentsAndPublisher|
|studentsAndTeamOwners|
|unknownFutureValue|
|studentsOnly|

### educationAssignmentStatus values
|Member|
|:---|
|draft|
|published|
|assigned|
|unknownFutureValue|

### educationSubmissionStatus values
|Member|
|:---|
|working|
|submitted|
|released|
|returned|
|unknownFutureValue|
|reassigned|

### educationFeedbackResourceOutcomeStatus values
|Member|
|:---|
|notPublished|
|pendingPublish|
|published|
|failedPublish|
|unknownFutureValue|

### externalEmailOtpState values

|Member|
|:---|
|default|
|enabled|
|disabled|
|unknownFutureValue|

### expirationRequirement values

|Member|
|:---|
|rememberMultifactorAuthenticationOnTrustedDevices|
|tenantTokenLifetimePolicy|
|audienceTokenLifetimePolicy|
|signInFrequencyPeriodicReauthentication|
|ngcMfa|
|signInFrequencyEveryTime|
|unknownFutureValue|


### replyRestriction values

| Member
|:--------------
| everyone
| authorAndModerators
| unknownFutureValue

### userNewMessageRestriction values

| Member
|:--------------
|everyone
|everyoneExceptGuests
|moderators
|unknownFutureValue

### volumeType values

|Member|
|:---|
|operatingSystemVolume|
|fixedDataVolume|
|removableDataVolume|
|unknownFutureValue|

### allowedAudiences values

|Member|
|:---|
|me|
|family|
|contacts|
|groupMembers|
|organization|
|federatedOrganizations|
|everyone|
|unknownFutureValue|

### attestationLevel values

|Member|
|:---|
|attested|
|notAttested|
|unknownFutureValue|

### emailType values

|Member|
|:---|
|unknown|
|work|
|personal|
|main|
|other|

### authenticationMethodSignInState values

|Member|
|:---|
|notSupported|
|notAllowedByPolicy|
|notEnabled|
|phoneNumberNotUnique|
|ready|
|notConfigured|
|unknownFutureValue|

### authenticationPhoneType values

|Member|
|:---|
|mobile|
|alternateMobile|
|office|
|unknownFutureValue|


### authenticationMethodTargetType values

|Member|
|:---|
|user|
|group|

### authenticationMethodState values

|Member|
|:---|
|enabled|
|disabled|

### fido2RestrictionEnforcementType values

|Member|
|:---|
|allow|
|block|
|unknownFutureValue|

### x509CertificateAuthenticationMode values
|Member|
|:---|
|x509CertificateSingleFactor|
|x509CertificateMultiFactor|
|unknownFutureValue|

### x509CertificateRuleType values
|Member|
|:---|
|issuerSubject|
|policyOID|
|unknownFutureValue|

### anniversaryType values

|Member|
|:---|
|birthday|
|wedding|
|unknownFutureValue|

### skillProficiencyLevel values

|Member|
|:---|
|elementary|
|limitedWorking|
|generalProfessional|
|advancedProfessional|
|expert|
|unknownFutureValue|

### languageProficiencyLevel values

|Member|
|:---|
|elementary|
|conversational|
|limitedWorking|
|professionalWorking|
|fullProfessional|
|nativeOrBilingual|
|unknownFutureValue|

### personRelationship values

|Member|
|:---|
|manager|
|colleague|
|directReport|
|dotLineReport|
|assistant|
|dotLineManager|
|alternateContact|
|friend|
|spouse|
|sibling|
|child|
|parent|
|sponsor|
|emergencyContact|
|other|
|unknownFutureValue|

### attachmentType values

| Member
|:--------------
| file
| item
| reference

### analyticsActivityType values

| Member
|:--------------
| call
| chat
| email
| focus
| meeting

### registrationAuthMethod values

|Member|
|:---|
|email|
|mobilePhone|
|officePhone|
|securityQuestion|
|appNotification|
|appCode|
|alternateMobilePhone|

### entityTypes values

|Member|
|:---|
|event|
|message|
|driveItem|
|externalItem|
|site|
|list|
|listItem|
|drive|
|unknownFutureValue|

### searchAlterationType values

| Member |
|:---------------|
|modification|
|suggestion|

### bucketAggregationSortProperty values

|Member|
|:---|
|count|
|keyAsString|
|keyAsNumber|

### contactRelationship values

| Member             | Value | Description                              |
| :----------------- | :---- | :--------------------------------------- |
| parent             | 0     | The user's parent.                       |
| relative           | 1     | The user's relative.                     |
| aide               | 2     | The user's aide.                         |
| doctor             | 3     | The user's doctor.                       |
| guardian           | 4     | The user's guardian.                     |
| child              | 5     | The user's child.                        |
| other              | 6     | An unspecified relationship to the user. |
| unknownFutureValue | 7     | Marker value for future compatibility.   |

### scheduleEntityTheme values

| Member
|:-------------------------
| white
| blue
| green
| purple
| pink
| yellow
| gray
| darkBlue
| darkGreen
| darkPurple
| darkPink
| darkYellow
| unknownFutureValue


### timeOffReasonIconType values

|Member|
|:---|
|none|
|car|
|calendar|
|running|
|plane|
|firstAid|
|doctor|
|notWorking|
|clock|
|juryDuty|
|globe|
|cup|
|phone|
|weather|
|umbrella|
|piggyBank|
|dog|
|cake|
|trafficCone|
|pin|
|sunny|
|unknownFutureValue|

### timeCardState values

|Member|
|:---|
|clockedIn|
|onBreak|
|clockedOut|
|unknownFutureValue|

### scheduleChangeState values

| Member
|:----------------------------
|pending
|approved
|declined
|unknownFutureValue

### scheduleChangeRequestActor values

| Member
|:----------------------------
|sender
|recipient
|manager
|system
|unknownFutureValue

### workforceIntegrationEncryptionProtocol values

| Member
|:----------------------------
|sharedSecret
|unknownFutureValue

### workforceIntegrationSupportedEntities values

|Member|
|:---|
|none|
|shift|
|swapRequest|
|userShiftPreferences|
|openShift|
|openShiftRequest|
|offerShiftRequest|
|unknownFutureValue|
|timeCard|
|timeOffReason|
|timeOff|
|timeOffRequest|

### confirmedBy values

| Member
|:-----------------
| none|
| user|
| manager|
| unknownFutureValue|

### timeZoneStandard values

| Member
|:-----------------
| windows
| iana


### freeBusyStatus values

| Member           | Value |
| :--------------- | :---- |
| free             | 0     |
| tentative        | 1     |
| busy             | 2     |
| oof              | 3     |
| workingElsewhere | 4     |
| unknown          | -1    |


### physicalAddressType values

| Member
|:-------------------------
| unknown
| home
| business
| other


### attendeeType values

| Member
|:-------------------------
| required
| optional
| resource


### externalAudienceScope values

| Member
|:-------------------------
| none
| contactsOnly
| all


### automaticRepliesStatus values

| Member
|:-------------------------
| disabled
| alwaysEnabled
| scheduled


### calendarColor values

| Member      | Value |
| :---------- | :---- |
| auto        | -1    |
| lightBlue   | 0     |
| lightGreen  | 1     |
| lightOrange | 2     |
| lightGray   | 3     |
| lightYellow | 4     |
| lightTeal   | 5     |
| lightPink   | 6     |
| lightBrown  | 7     |
| lightRed    | 8     |
| maxColor    | 9     |


### educationSynchronizationProfileState values

| Member             | Value |
| :----------------- | :---- |
| deleting           | 2     |
| deletionFailed     | 3     |
| provisioningFailed | 5     |
| provisioned        | 6     |
| provisioning       | 7     |
| unknownFutureValue | 8     |


### educationSynchronizationStatus values

| Member             |
| :----------------- |
| paused             |
| inProgress         |
| success            |
| error              |
| validationError    |
| quarantined        |
| unknownFutureValue |
| extracting         |
| validating         |

### educationExternalSource values

| Member
|:-------------------------
| sis
| lms
| manual
| unknownFutureValue

### educationGender values

| Member
|:-------------------------
| female
| male
| other
| unknownFutureValue


### eventType values

| Member
|:-------------------------
| singleInstance
| occurrence
| exception
| seriesMaster


### sensitivity values

| Member
|:-------------------------
| normal
| personal
| private
| confidential


### importance values

| Member
|:-------------------------
| low
| normal
| high


### educationUserRole values
| Member
|:---------------------
| student
| teacher
| faculty


### meetingMessageType values

| Member
|:-----------------
| none
| meetingRequest
| meetingCancelled
| meetingAccepted
| meetingTentativelyAccepted
| meetingDeclined


### followupFlagStatus values

| Member
|:-------------------------
| notFlagged
| complete
| flagged


### inferenceClassificationType values

| Member
|:-----------------
| focused
| other


### iosNotificationAlertType values

| Member
|:-------------------------
| deviceDefault
| banner
| modal
| none

### deviceEnrollmentFailureReason values

| Member
|:-------------
| unknown
| authentication
| authorization
| accountValidation
| userValidation
| deviceNotSupported
| inMaintenance
| badRequest
| featureNotSupported
| enrollmentRestrictionsEnforced
| clientDisconnected


### bodyType values
| Member
|:---------
| text
| html


### locationType values

| Member
|:-------------------------
| default
| conferenceRoom
| homeAddress
| businessAddress
| geoCoordinates
| streetAddress
| hotel
| restaurant
| localBusiness
| postalAddress

### locationUniqueIdType values

| Member
|:-------------------------
| unknown
| locationStore
| directory
| private
| bing


### messageActionFlag values

| Member
|:-------------------------
| any
| call
| doNotForward
| followUp
| fyi
| forward
| noResponseNecessary
| read
| reply
| replyToAll
| review


### onenoteUserRole values

| Member      | Value |
| :---------- | :---- |
| Owner       | 0     |
| Contributor | 1     |
| Reader      | 2     |
| None        | -1    |


### operationStatus values

| Member
|:-----------------
|NotStarted
|Running
|Completed
|Failed


### onenotePatchActionType values

| Member
|:-------------------------
| Replace
| Append
| Delete
| Insert
| Prepend

### onenotePatchInsertPosition values

| Member
|:-------------------------
| After
| Before


### phoneType values

| Member
|:-------------------------
| home
| business
| mobile
| other
| assistant
| homeFax
| businessFax
| otherFax
| pager
| radio


### plannerPreviewType values

| Member
|:-------------------------
| automatic
| noPreview
| checklist
| description
| reference


### status values

| Member
|:-----------------
| active
| updated
| deleted
| ignored
| unknownFutureValue


### weekIndex values

| Member
|:-------------------------
| first
| second
| third
| fourth
| last


### dayOfWeek values

| Member
|:-------------------------
| sunday
| monday
| tuesday
| wednesday
| thursday
| friday
| saturday

### recurrencePatternType values

| Member
|:-------------------------
| daily
| weekly
| absoluteMonthly
| relativeMonthly
| absoluteYearly
| relativeYearly


### recurrenceRangeType values

| Member
|:-------------------------
| endDate
| noEnd
| numbered


### onenoteSourceService values
| Member
|:---------------------
| Unknown
| OneDrive
| OneDriveForBusiness
| OnPremOneDriveForBusiness


### responseType values

| Member
|:-------------------------
| none
| organizer
| tentativelyAccepted
| accepted
| declined
| notResponded


### activityDomain values

| Member
|:-------------------------
| unknown
| work
| personal
| unrestricted


### websiteType values

| Member
|:-------------------------
| other
| home
| work
| blog
| profile


### categoryColor values

| Member   | Value |
| :------- | :---- |
| none     | -1    |
| preset0  | 0     |
| preset1  | 1     |
| preset2  | 2     |
| preset3  | 3     |
| preset4  | 4     |
| preset5  | 5     |
| preset6  | 6     |
| preset7  | 7     |
| preset8  | 8     |
| preset9  | 9     |
| preset10 | 10    |
| preset11 | 11    |
| preset12 | 12    |
| preset13 | 13    |
| preset14 | 14    |
| preset15 | 15    |
| preset16 | 16    |
| preset17 | 17    |
| preset18 | 18    |
| preset19 | 19    |
| preset20 | 20    |
| preset21 | 21    |
| preset22 | 22    |
| preset23 | 23    |
| preset24 | 24    |

### alertFeedback values

Possible feedback values on the alert provided by an analyst.

| Member         | Value | Description               |
| :------------- | :---- | :------------------------ |
| unknown        | 0     | Unknown.                  |
| truePositive   | 1     | Alert is true-positive.   |
| falsePositive  | 2     | Alert is false-positive.  |
| benignPositive | 3     | Alert is benign-positive. |

### fileHashType values

| Member              | Value | Description                    |
| :------------------ | :---- | :----------------------------- |
| unknown             | 0     | Unknown type.                  |
| sha1                | 1     | SHA1 hash type.                |
| sha256              | 2     | SHA256 hash type.              |
| md5                 | 3     | MD5 hash type.                 |
| authenticodeHash256 | 4     | AuthenticodeHash256 hash type. |
| lsHash              | 5     | LsHash hash type.              |
| ctph                | 6     | CTPH hash type.                |
| peSha1              | 7     | PESHA1 hash type.              |
| peSha256            | 8     | PESHA256 hash type.            |

### connectionDirection values

| Member   | Value | Description          |
| :------- | :---- | :------------------- |
| unknown  | 0     | Unknown connection.  |
| inbound  | 1     | Inbound connection.  |
| outbound | 2     | Outbound connection. |

### connectionStatus values

| Member    | Value | Description                |
| :-------- | :---- | :------------------------- |
| unknown   | 0     | Unknown connection status. |
| attempted | 1     | Connection attempted.      |
| succeeded | 2     | Connection succeeded.      |
| blocked   | 3     | Connection blocked.        |
| failed    | 4     | Connection failed.         |

### processIntegrityLevel values

| Member    | Value | Description                   |
| :-------- | :---- | :---------------------------- |
| unknown   | 0     | Unknown.                      |
| untrusted | 10    | Integrity level is Untrusted. |
| low       | 20    | Integrity level is Low.       |
| medium    | 30    | Integrity level is Medium.    |
| high      | 40    | Integrity level is High.      |
| system    | 50    | Integrity level is System.    |

### registryHive values

Enum for registry hives as defined by [Registry Hives](/windows/desktop/sysinfo/registry-hives).

| Member                  | Value | Description                       |
| :---------------------- | :---- | :-------------------------------- |
| unknown                 | 0     | Unknown hive.                     |
| currentConfig           | 1     | HKEY_CURRENT_CONFIG hive.         |
| currentUser             | 2     | HKEY_CURRENT_USER hive.           |
| localMachineSam         | 3     | HKEY_LOCAL_MACHINE\SAM hive.      |
| localMachineSamSoftware | 4     | HKEY_LOCAL_MACHINE\Software hive. |
| localMachineSystem      | 5     | HKEY_LOCAL_MACHINE\System hive.   |
| usersDefault            | 6     | HKEY_USERS\\.DEFAULT hive.        |

### registryOperation values

Operation that changed the registry key name and/or value.

| Member  | Value | Description                  |
| :------ | :---- | :--------------------------- |
| unknown | 0     | Unknown registry value type. |
| create  | 1     | Create registry.             |
| modify  | 2     | Modify registry.             |
| delete  | 3     | Delete registry.             |

### registryValueType values

Enum for registry value types as defined by [Registry value types](/windows/desktop/sysinfo/registry-value-types).

| Member            | Value | Description                                  |
| :---------------- | :---- | :------------------------------------------- |
| unknown           | 0     | Unknown registry value type.                 |
| binary            | 1     | REG_BINARY registry value type.              |
| dword             | 2     | REG_DWORD registry value type.               |
| dwordLittleEndian | 3     | REG_DWORD_LITTLE_ENDIAN registry value type. |
| dwordBigEndian    | 4     | REG_DWORD_BIG_ENDIAN registry value type.    |
| expandSz          | 5     | REG_EXPAND_SZ registry value type.           |
| link              | 6     | REG_LINK registry value type.                |
| multiSz           | 7     | REG_MULTI_SZ registry value type.            |
| none              | 8     | REG_NONE registry value type.                |
| qword             | 9     | REG_QWORD registry value type.               |
| qwordlittleEndian | 10    | REG_QWORD_LITTLE_ENDIAN registry value type. |
| sz                | 11    | REG_SZ registry value type.                  |

### alertSeverity values

Enum for severity of alerts.

| Member        | Value | Description                       |
| :------------ | :---- | :-------------------------------- |
| unknown       | 0     | Severity is unknown.              |
| informational | 1     | Severity is only for information. |
| low           | 2     | Severity is low.                  |
| medium        | 3     | Severity is medium.               |
| high          | 4     | Severity is high.                 |

### alertStatus values

Possible values of an Alert lifecycle status (stage).

| Member     | Value | Description           |
| :--------- | :---- | :-------------------- |
| unknown    | 0     | Unknown status.       |
| newAlert   | 10    | Alert is new.         |
| inProgress | 20    | Alert is in progress. |
| resolved   | 30    | Alert is resolved.    |

### emailRole values

Possible values for email roles.

| Member    | Value | Description             |
| :-------- | :---- | :---------------------- |
| unknown   | 0     | Unknown Role.           |
| sender    | 1     | Sender of the email.    |
| recipient | 2     | Recipient of the email. |

### logonType values

Possible values for the method of user signin.

| Member            | Value | Description                  |
| :---------------- | :---- | :--------------------------- |
| unknown           | -1    | Unknown.                     |
| interactive       | 0     | Logon is interactive.        |
| remoteInteractive | 1     | Logon is remote interactive. |
| network           | 2     | Logon is network.            |
| batch             | 3     | Logon is batch.              |
| service           | 4     | Logon is service.            |

### userAccountSecurityType values

Possible values for user account types (group membership), per Windows definition.

| Member        | Value | Description                     |
| :------------ | :---- | :------------------------------ |
| unknown       | -1    | Unknown.                        |
| standard      | 0     | Member of Standard Users group. |
| power         | 1     | Member of Power Users group.    |
| administrator | 2     | Member of Administrators group. |

### chatMessagePolicyViolationDlpActionType values

| Value |
|:-----------------|
| none |
| NotifySender |
| BlockAccess |
| BlockAccessExternal |

### scopeOperatorMultiValuedComparisonType values

|Member|
|:---|
|all|
|any|

### riskLevel values

|Member|
|:---|
|low|
|medium|
|high|
|hidden|
|none|
|unknownFutureValue|

### riskState values

|Member|
|:---|
|none|
|confirmedSafe|
|remediated|
|dismissed|
|atRisk|
|confirmedCompromised|
|unknownFutureValue|

### advancedConfigState values

|Member|
|:---|
|default|
|enabled|
|disabled|
|unknownFutureValue|

### referenceAttachmentPermission values

|Member|
|:---|
|other|
|view|
|edit|
|anonymousView|
|anonymousEdit|
|organizationView|
|organizationEdit|

### referenceAttachmentProvider values

|Member|
|:---|
|other|
|oneDriveBusiness|
|oneDriveConsumer|
|dropbox|

### networkType values

|Member|
|:---|
|intranet|
|extranet|
|namedNetwork|
|trusted|
|unknownFutureValue|

### exchangeIdFormat values

|Member|
|:---|
|entryId|
|ewsId|
|immutableEntryId|
|restId|
|restImmutableEntryId|

### attributeFlowBehavior values

|Member|
|:---|
|flowWhenChanged|
|flowAlways|

### attributeFlowType values

|Member|
|:---|
|always|
|objectAddOnly|
|multiValueAddOnly|
|restId|

### objectFlowTypes values

| Member | Value |
| :----- | :---- |
| None   | 0     |
| Add    | 1     |
| Update | 2     |
| Delete | 4     |

### chatMessageType values

|Member|
|:---|
|message|
|chatEvent |
|typing |
|unknownFutureValue|
|systemEventMessage|

### chatMessageImportance values

|Member|
|:---|
|normal|
|high|
|urgent|

### channelMembershipType values

| Member             |
| :----------------- |
| standard           |
| private            |
| unknownFutureValue |
| shared             |

### stagedFeatureName values

| Member                    | Description                   |
| :------------------------ | :---------------------------- |
| passthroughAuthentication | Passthrough Authentication    |
| seamlessSso               | Seamless Single Sign-on       |
| passwordHashSync          | Password Hash Synchronization |
| emailAsAlternateId        | Email as an alternate id      |
| unknownFutureValue        | A sentinel member             |

### tokenIssuerType values

|Member|
|:---|
|AzureAD|
|ADFederationServices|
|unknownFutureValue|
|AzureADBackupAuth|
|ADFederationServicesMFAAdapter|
|NPSExtension|


### riskDetectionTimingType values

|Member|
|:---|
|notDefined|
|realtime|
|nearRealtime|
|offline|
|unknownFutureValue|

### activityType values

|Member|
|:---|
|signin|
|user|
|unknownFutureValue|
|servicePrincipal|

### chatMessagePolicyViolationUserActionType values

| Member   | Int value |  Description |
|:---------------|:--------|:----------|
| None | 0 | Default value. This is the value on a message when the user has not taken an action on the message blocked by DLP. |
| Override | 1 | Sender has overridden the message verdict and sent the message anyway.|
| ReportFalsePositive | 2 | Sender has reported the message verdict to the admins as a false positive.|

### chatMessagePolicyViolationVerdictDetailsType values

| Member   | Int value |  Description |
|:---------------|:--------|:----------|
| None | 0 |  User is not allowed to override the message. User is not allowed to report a message as false positive if policyTip is not provided. In all other scenarios, user can report a message as false positive.|
| AllowFalsePositiveOverride | 1 |  User is not allowed to explicitly override the block unless this is combined with `AllowOverrideWithoutJustification` or `AllowOverrideWithJustification` flags. Reporting a false positive on the violation automatically overrides the block and sends the message. |
| AllowOverrideWithoutJustification | 2 | User is allowed to override the block and send the message. Justification text is not required. Exclusive to `AllowOverrideWithJustification`. |
| AllowOverrideWithJustification | 4 |  User is allowed to override the block and send the message. Justification text is required. Exclusive to `AllowOverrideWithoutJustification`.|

### entityType values

| Member       |
|:--------------|
|event|
|message|
|driveItem|
|externalFile|
|externalItem|

### onlineMeetingProviderType values

|Member|
|:---|
|unknown|
|skypeForBusiness|
|skypeForConsumer|
|teamsForBusiness|

### delegateMeetingMessageDeliveryOptions values

|Member|
|:---|
|sendToDelegateAndInformationToPrincipal|
|sendToDelegateAndPrincipal|
|sendToDelegateOnly|

### calendarRoleType values

|Member|
|:---|
|none|
|freeBusyRead|
|limitedRead|
|read|
|write|
|delegateWithoutPrivateEventAccess|
|delegateWithPrivateEventAccess|
|custom|

### contentFormat values

| Member  | Value | Description                          |
| :------ | :---- | :----------------------------------- |
| default | 0     | Content is a file or non-email type. |
| email   | 1     | Content is an email.                 |

### contentState values

| Member | Value | Description                                                                      |
| :----- | :---- | :------------------------------------------------------------------------------- |
| rest   | 0     | Data is at rest; A file in a share, for example.                                 |
| motion | 1     | Data is in motion. A file intercepted by a network appliance in transit.         |
| use    | 2     | Data is in use. A file is open in a client application such as Microsoft Office. |

### assignmentMethod values

| Member     | Value | Description                                                                                                                      |
| :--------- | :---- | :------------------------------------------------------------------------------------------------------------------------------- |
| standard   | 0     | The label was set by a service or policy condition.                                                                              |
| privileged | 1     | The label was set explicitly by a user.                                                                                          |
| auto       | 2     | Allows override of any existing label. Justification required on downgrade. Results in `standard` assignment method in metadata. |

### actionSource values

| Member        | Value | Description                                                  |
| :------------ | :---- | :----------------------------------------------------------- |
| manual        | 0     | A user manually selected the label.                          |
| automatic     | 1     | The label was chosen as a result of policy conditions.       |
| recommended   | 2     | The elected to apply a recommended label.                    |
| policyDefault | 3     | The user no action and the policy-default label was applied. |
| mandatory     | 4     | The user chose a label after being forced to choose.         |

### contentAlignment values

| Member | Value | Description                         |
| :----- | :---- | :---------------------------------- |
| left   | 0     | Align content marking to the left.  |
| right  | 1     | Align content marking to the right. |
| center | 2     | Center content marking.             |

### watermarkLayout values

| Member     | Value | Description                 |
| :--------- | :---- | :-------------------------- |
| horizontal | 0     | Use a horizontal watermark. |
| diagonal   | 1     | Use a diagonal watermark.   |

### conditionalAccessPolicyState values

|Member|
|:---|
|enabled|
|disabled|
|enabledForReportingButNotEnforced|

### conditionalAccessGrantControl values

| Member       |
|:--------------|
|block|
|mfa|
|compliantDevice|
|domainJoinedDevice|
|approvedApplication|
|compliantApplication|
|passwordChange|
|unknownFutureValue|

### conditionalAccessRule values 

|Member|
|:---|
|allApps|
|firstPartyApps|
|office365|
|appId|
|acr|
|appFilter|
|allUsers|
|guest|
|groupId|
|roleId|
|userId|
|allDevicePlatforms|
|devicePlatform|
|allLocations|
|insideCorpnet|
|allTrustedLocations|
|locationId|
|allDevices|
|deviceFilter|
|deviceState|
|unknownFutureValue|
|deviceFilterIncludeRuleNotMatched|
|allDeviceStates|
|anonymizedIPAddress|
|unfamiliarFeatures|
|nationStateIPAddress|
|realTimeThreatIntelligence|
|internalGuest|
|b2bCollaborationGuest|
|b2bCollaborationMember|
|b2bDirectConnectUser|
|otherExternalUser|
|serviceProvider|

### signInAccessType values 

|Member|
|:---|
|none|
|b2bCollaboration|
|b2bDirectConnect|
|microsoftSupport|
|serviceProvider|
|unknownFutureValue|

### signinFrequencyType values

| Member       |
|:--------------|
|days|
|hours|

### persistentBrowserSessionMode values

| Member       |
|:--------------|
|always|
|never|

### cloudAppSecuritySessionControlType values

| Member       |
|:--------------|
|mcasConfigured|
|monitorOnly|
|blockDownloads|

### conditionalAccessDevicePlatform values

| Member       |
|:--------------|
|android|
|iOS|
|windows|
|windowsPhone|
|macOS|
|all|
|unknownFutureValue|

### priority values

|Member|Value|
|:---|:---|
|None|0|
|High|1|
|Low|2|

### threatAssessmentContentType values

| Member | Value | Description             |
|:-------|:------|:------------------------|
| mail   | 1     | Mail threat.            |
| url    | 2     | URL threat.             |
| file   | 3     | Attachment file threat. |

### threatExpectedAssessment values

| Member  | Value | Description                       |
|:--------|:------|:----------------------------------|
| block   | 1     | The threat should be blocked.     |
| unblock | 2     | The threat should not be blocked. |

### threatCategory values

| Member             | Value | Description        |
|:-------------------|:------|:-------------------|
| spam               | 1     | Spam threat.       |
| phishing           | 2     | Phishing threat.   |
| malware            | 3     | Malware threat.    |
| unknownFutureValue | 4     | A sentinel member. |

### threatAssessmentStatus values

| Member    | Value | Description                              |
|:----------|:------|:-----------------------------------------|
| pending   | 1     | The threat assessment still in progress. |
| completed | 2     | The threat assessment completed.         |

### threatAssessmentRequestSource values

| Member        | Value | Description              |
|:--------------|:------|:-------------------------|
| undefined     | 0     | Not yet know.            |
| user          | 1     | User submission.         |
| administrator | 2     | Tenant admin submission. |

### threatAssessmentResultType values

| Member             | Value | Description                                          |
|:-------------------|:------|:-----------------------------------------------------|
| checkPolicy        | 1     | The policy check result, only for `mail` assessment. |
| rescan             | 2     | The rescan result.                                   |
| unknownFutureValue | 3     | A sentinel member.                                   |

### mailDestinationRoutingReason values

| Member                | Value | Description                         |
|:----------------------|:------|:------------------------------------|
| none                  | 0     | Not yet know.                       |
| mailFlowRule          | 1     | Exchange transport rule.            |
| safeSender            | 2     | Safe sender list.                   |
| blockedSender         | 3     | Blocked sender list.                |
| advancedSpamFiltering | 4     | Advanced spam flitering option.     |
| domainAllowList       | 5     | Sender domain allow list.           |
| domainBlockList       | 6     | Sender domain block list.           |
| notInAddressBook      | 7     | Exclude sender not in address book. |
| firstTimeSender       | 8     | Blocked due to first time sender.   |
| autoPurgeToInbox      | 9     | TimeTravel move message to inbox.   |
| autoPurgeToJunk       | 10    | TimeTravel move message to junk.    |
| autoPurgeToDeleted    | 11    | TimeTravel move message to deleted. |
| outbound              | 12    | Outbound mail.                      |
| notJunk               | 13    | Allow due to not junk.              |
| junk                  | 14    | Blocked due to junk.                |
| unknownFutureValue    | 15    | A sentinel member.                  |

### threatAssessmentRequestPivotProperty values

| Member                       | Value | Description                                                            |
|:-----------------------------|:------|:-----------------------------------------------------------------------|
| threatCategory               | 1     | Aggregate threat assessment request by `threatCategory`.               |
| mailDestinationRoutingReason | 2     | Aggregate threat assessment request by `mailDestinationRoutingReason`. |

### userFlowType values

|Member
|:----------------------
| signUp
| signIn
| signUpOrSignIn
| passwordReset
| profileUpdate
| resourceOwner
| unknownFutureValue

### openIdConnectResponseMode values

| Member
|:----------------------
| form_post
| query
| unknownFutureValue

### wellknownListName values

| Member
|:----------------------
| none
| defaultList
| flaggedEmails
| unknownFutureValue

### taskStatus values

| Member
|:----------------------
| notStarted
| inProgress
| completed
| waitingOnOthers
| deferred

### columnTypes values

|Member|Description|
|:-------|:------
|note| multiline text. |
|text | single line text. |
|choice | choice column |
|multichoice | multichoice column. |
|number | number column. |
|currency | currency column. |
|dateTime | dateTime column. |
|lookup | lookup column. |
|boolean | Yes/No column. |
|user | person or group column. |
|url | hyperlink or picture column. |
|calculated | calculated column. |
|location | location column. |
|geolocation | geolocation column. |
|term | managed metadata column. |
|multiterm | managed metadata column accepting multiple values. |
|thumbnail | Image column. |
|approvalStatus | Content approval status column. |
|unknownFutureValue | unknownFuturevalue |

### connectedOrganizationState values

| Member                | Value | Description                                                                                                                                                                                                        |
|:----------------------| :-----|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| configured            | 0     | Connected Organizations with this state value are included in assignment policies with requestor scope type `AllConfiguredConnectedOrganizationSubjects`.                                                          |
| proposed              | 1     | Connected Organizations that are automatically created by the system have this state value. They are not included in assignment policies with requestor scope type `AllConfiguredConnectedOrganizationSubjects`.   |
| unknownFutureValue    | 2     | A sentinel member.                                                                                                                                                                                                 |

### identityUserFlowAttributeDataType values

| Member                | Value | Description                         |
|:----------------------|:------|:------------------------------------|
| string                | 1     | String data type                    |
| boolean               | 2     | Boolean data type                   |
| int64                 | 3     | Int data type                       |
| stringCollection      | 4     | String collection data type         |
|dateTime|5||
| unknownFutureValue    | 6     | A sentinel member.                  |

### identityUserFlowAttributeType values

| Member                | Value | Description                                                        |
|:----------------------|:------|:-------------------------------------------------------------------|
| builtIn               | 1     | This user flow attribute type denotes it was created by the system |
| custom                | 2     | This user flow attribute type denotes it was created by the user   |
|required|3||
| unknownFutureValue    | 4     | A sentinel member.                                                 |

### permissionClassificationType values

| Member
|:-------
| low

### permissionType values

| Member
|:-------------------------
| application
| delegated
| delegatedUserConsentable

### identityUserFlowAttributeInputType values

| Member                |
|:----------------------|
| textBox               |
| dateTimeDropDown      |
| radioSingleSelect     |
| dropdownSingleSelect  |
| emailBox              |
| checkboxMultiSelect   |

### teamworkActivityTopicSource values

| Member
|:---
| entityUrl
| text

### cloudPcProvisioningPolicyImageType values

|Member|
|:---|
|custom|
|gallery|

### chatType values

| Member             | Value | Description               |
| :----------------- | :---- | :------------------------ |
|oneOnOne            | 0     | Indicates that the chat is a 1:1 chat. The roster size is fixed for this type of chat, the member cannot be removed / added.                  |
|group               | 1     | Indicates that the chat is a Group chat. The roster size (of at least 2 person) can be updated for this type of chat. The members can be removed / added later on.   |
|meeting             | 2     | Indicates that the chat is a Meeting chat, which is created as a side effect of creation of an OnlineMeeting.  |
|unknownFutureValue  | 3     | Sentinel value to indicate future values. |

### singleSignOnMode values

|Member|
|:---|
|none|
|onPremisesKerberos|
|aadHeaderBased|
|pingHeaderBased|

### plannerContainerType values

|Member|
|:---|
|group|
|unknownFutureValue|
|roster|

### plannerPlanContextType values

|Member|
|:---|
|teamsTab|
|sharePointPage|
|meetingNotes|
|other|
|unknownFutureValue|

### plannerContextState values

|Member             |
|:------------------|
|active             |
|delinked           |
|unknownFutureValue |  


### policyScope values

|Member|
|:---|
|none|
|all|
|selected|

### teamsAppInstallationScope values

|Member    |Value    |Description |
|:---------|:--------|:----------- |
|team      |0        |Indicates that the Teams app can be installed within a team and is authorized to access that team's data.|
|groupChat |1        |Indicates that the Teams app can be installed within a group chat and is authorized to access that group chat's data.|
|personal  |2        |Indicates that the Teams app can be installed in the personal scope of a user and is authorized to access that user's data.|

### roleAssignmentScheduleRequestFilterByCurrentUserOptions values

|Member|
|:---|
|principal|
|createdBy|
|approver|
|unknownFutureValue|

### roleAssignmentScheduleFilterByCurrentUserOptions values

|Member|
|:---|
|principal|
|unknownFutureValue|

### roleAssignmentScheduleInstanceFilterByCurrentUserOptions values

|Member|
|:---|
|principal|
|unknownFutureValue|

### roleEligibilityScheduleRequestFilterByCurrentUserOptions values

|Member|
|:---|
|principal|
|createdBy|
|approver|
|unknownFutureValue|

### roleEligibilityScheduleFilterByCurrentUserOptions values

|Member|
|:---|
|principal|
|unknownFutureValue|

### roleEligibilityScheduleInstanceFilterByCurrentUserOptions values

|Member|
|:---|
|principal|
|unknownFutureValue|

### cloudPcAuditActivityOperationType values

|Member|
|:---|
|create|
|delete|
|patch|
|other|

### cloudPcAuditActivityResult values

|Member|
|:---|
|success|
|clientError|
|failure|
|timeout|
|other|

### cloudPcAuditActorType values

|Member|
|:---|
|itPro|
|application|
|partner|
|unknown|

### cloudPcAuditCategory values

|Member|
|:---|
|cloudPC|
|other|

### postType values

|Member|
|:---|
|regular|
|quick|
|strategic|
|unknownFutureValue|

### serviceHealthClassificationType values

|Member|
|:---|
|advisory|
|incident|
|unknownFutureValue|

### serviceHealthOrigin values

|Member|
|:---|
|microsoft|
|thirdParty|
|customer|
|unknownFutureValue|

### serviceHealthStatus values

|Member|
|:---|
|serviceOperational|
|investigating|
|restoringService|
|verifyingService|
|serviceRestored|
|postIncidentReviewPublished|
|serviceDegradation|
|serviceInterruption|
|extendedRecovery|
|falsePositive|
|investigationSuspended|
|resolved|
|mitigatedExternal|
|mitigated|
|resolvedExternal|
|confirmed|
|reported|
|unknownFutureValue|

### serviceUpdateCategory values

|Member|
|:---|
|preventOrFixIssue|
|planForChange|
|stayInformed|
|unknownFutureValue|

### serviceUpdateSeverity values

|Member|
|:---|
|normal|
|high|
|critical|
|unknownFutureValue|

### teamworkTagType values

|Member| Value | Description               |
|:---|:---- | :------------------------ |
|standard| 0     |Default type for a tag. Tags of type standard can be managed in the team by members who have permissions.|

### teamworkApplicationIdentityType values

|Member|
|:---|
|aadApplication|
|bot|
|tenantBot|
|office365Connector|
|outgoingWebhook|
|unknownFutureValue|

### teamworkConversationIdentityType values

|Member|
|:---|
|team|
|channel|
|chat|
|unknownFutureValue|

### teamworkUserIdentityType values

|Member|
|:---|
|aadUser|
|onPremiseAadUser|
|anonymousGuest|
|federatedUser|
|personalMicrosoftAccountUser|
|skypeUser|
|phoneUser|
|unknownFutureValue|
|emailUser|

### callRecordingStatus values

|Member|
|:---|
|success|
|failure|
|initial|
|chunkFinished|
|unknownFutureValue|

### payloadDeliveryPlatform values

|Member|
|:---|
|unknown|
|sms|
|email|
|teams|
|unknownFutureValue|

### trainingStatus values

|Member|
|:---|
|unknown|
|assigned|
|inProgress|
|completed|
|overdue|
|unknownFutureValue|

### teamworkCallEventType values

|Member|
|:---|
|call|
|meeting|
|screenShare|
|unknownFutureValue|

### binaryOperator values 

|Member|
|:---|
|or|
|and|

### subjectRightsRequestStage values 

|Member|
|:---|
|contentRetrieval|
|contentReview| 
|generateReport| 
|contentDeletion|
|caseResolved|
|unknownFutureValue|

### subjectRightsRequestStageStatus values 

|Member|
|:---|
|notStarted|
|current|
|completed|
|failed|
|unknownFutureValue|

### subjectRightsRequestStatus values 

|Member|
|:---|
|active|
|closed|
|unknownFutureValue|

### subjectRightsRequestType values 

|Member|
|:---|
|export|
|delete|
|access|
|tagForAction|
|unknownFutureValue|

### dataSubjectType values 

|Member|
|:---|
|customer|
|currentEmployee|
|formerEmployee|
|prospectiveEmployee|
|student|
|teacher|
|faculty|
|other|
|unknownFutureValue|

### answerInputType values

|Member|Value|Description|
|:---|:---|:---|
|text|0|Text.|
|radioButton|1|RadioButton.|
|unknownFutureValue|2|UnknownFutureValue.|

### taskStatus_v2 values

|Member|
|:---|
|notStarted|
|inProgress|
|completed|
|unknownFutureValue|


### wellKnownListName_v2 values

|Member|
|:---|
|none|
|defaultList|
|flaggedEmail|
|unknownFutureValue|

### bookingPriceType values

|Member|
|:---|
|undefined|
|fixedPrice|
|startingAt|
|hourly|
|free|
|priceVaries|
|callUs|
|notSet|
|unknownFutureValue|

### bookingStaffRole values 

|Member|
|:---|
|guest|
|administrator|
|viewer|
|externalGuest|
|unknownFutureValue|
|scheduler|
|member|

### bookingReminderRecipients values 

|Member|
|:---|
|allAttendees|
|staff|
|customer|
|unknownFutureValue|

### teamworkConnectionStatus values

| Member |
|:--------|
|unknown|
|connected|
|disconnected|
|unknownFutureValue|

### teamworkDeviceActivityState values

| Member | Value| Description |
|:---------------|:--------|:----------|
|unknown|0|Unknown state.|
|busy|1|The device is busy.|
|idle|2|The device is idle.|
|unavailable|3|The device is unavailable.|
|unknownFutureValue|4|Evolvable enumeration sentinel value. Do not use.|

### teamworkDeviceOperationType values

| Member | Value| Description |
|:---------------|:--------|:----------|
|deviceRestart|0|Restart a device.|
|configUpdate|1|Update the device configuration.|
|deviceDiagnostics|2|Get the device logs.|
|softwareUpdate|3|Update a software on the device.|
|deviceManagementAgentConfigUpdate|4|Update the device agent configuration.|
|remoteLogin|5|Device remote login.|
|remoteLogout|6|Device remote logout.|
|unknownFutureValue|7|Evolvable enumeration sentinel value. Do not use.|

### teamworkSoftwareFreshness values

| Member | Value| Description |
|:---------------|:--------|:----------|
|unknown|0|Unknown value.|
|latest|1|Indicates whether a device component runs the latest version of the software.|
|updateAvailable|2|Indicates that a software update is available for a device component.|
|unknownFutureValue|3|Evolvable enumeration sentinel value. Do not use.|

### teamworkSoftwareType values

| Member |
|:---------------|
|adminAgent|
|operatingSystem|
|teamsClient|
|firmware|
|partnerAgent|
|companyPortal|
|unknownFutureValue|

### teamworkSupportedClient values

| Member | Value| Description |
|:---------------|:--------|:----------|
|unknown|0|Unknown value.|
|skypeDefaultAndTeams|1|Supports both `Skype` and `Teams`. Default is `Skype`.|
|teamsDefaultAndSkype|2|Supports both `Skype` and `Teams`. Default is `Teams`.|
|skypeOnly|3|Supports only `Skype`.|
|teamsOnly|4|Supports only `Teams`.|
|unknownFutureValue|5|Evolvable enumeration sentinel value. Do not use.|

### longRunningOperationStatus values

| Member|
|:-----------------|
|notStarted|
|running|
|succeeded|
|failed|
|unknownFutureValue|

### delegatedAdminAccessAssignmentStatus values 

|Member|
|:---|
|pending|
|active|
|deleting|
|deleted|
|error|
|unknownFutureValue|

### delegatedAdminAccessContainerType values 

|Member|
|:---|
|securityGroup|
|unknownFutureValue|

### delegatedAdminRelationshipOperationType values 

|Member|
|:---|
|delegatedAdminAccessAssignmentUpdate|
|unknownFutureValue|

### delegatedAdminRelationshipRequestAction values 

|Member|
|:---|
|lockForApproval|
|terminate|
|unknownFutureValue|

### delegatedAdminRelationshipRequestStatus values 

|Member|
|:---|
|created|
|pending|
|succeeded|
|failed|
|unknownFutureValue|

### delegatedAdminRelationshipStatus values 

|Member|
|:---|
|activating|
|active|
|approvalPending|
|approved|
|created|
|expired|
|expiring|
|terminated|
|terminating|
|terminationRequested|
|unknownFutureValue|

### longRunningOperationStatus values 

|Member|
|:---|
|notStarted|
|running|
|succeeded|
|failed|
|skipped|
|unknownFutureValue|

### submissionCategory values 

|Member|
|:---|
|notJunk|
|spam|
|phishing|
|malware|
|unknownFutureValue|

### submissionClientSource values 

|Member|
|:---|
|microsoft|
|other|
|unknownFutureValue|

### submissionContentType values 

|Member|
|:---|
|email|
|url|
|file|
|app|
|unknownFutureValue|

### submissionResultCategory values 

|Member|
|:---|
|notJunk|
|spam|
|phishing|
|malware|
|allowedByPolicy|
|blockedByPolicy|
|spoof|
|unknown|
|noResultAvailable|
|unknownFutureValue|

### submissionSource values 

|Member|
|:---|
|user|
|administrator|
|unknownFutureValue|

### tenantAllowBlockListAction values 

|Member|
|:---|
|allow|
|block|
|unknownFutureValue|

### tenantAllowBlockListEntryType values 

|Member|
|:---|
|url|
|fileHash|
|sender|
|recipient|
|unknownFutureValue|
