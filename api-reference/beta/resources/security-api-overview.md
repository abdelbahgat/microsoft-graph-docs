---
title: "Use the Microsoft Graph Security API"
description: " > **Important:** APIs under the /beta version in Microsoft Graph are in preview and are subject to change. Use of these APIs in production applications is not supported."
ms.localizationpriority: high
author: "preetikr"
ms.prod: "security"
doc_type: resourcePageType
---

# Use the Microsoft Graph Security API

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

The Microsoft Graph Security API provides a unified interface and schema to integrate with security solutions from Microsoft and ecosystem partners. This empowers customers to streamline security operations and better defend against increasing cyber threats. The Microsoft Graph Security API federates queries to all onboarded security providers and aggregates responses. Use the Microsoft Graph Security API to build applications that:

- Consolidate and correlate security alerts from multiple sources
- Unlock contextual data to inform investigations
- Automate security tasks, business processes, workflows, and reporting
- Send threat indicators to Microsoft products for customized detections
- Invoke actions to in response to new threats
- Provide visibility into security data to enable proactive risk management

The Microsoft Graph Security API includes the following key entities.

## Actions (preview)

Take immediate action to defend against threats using the Microsoft Graph Security [securityAction](securityaction.md) entity. When a security analyst discovers a new indicator, such as a malicious file, URL, domain, or IP address, protection can be instantly enabled in your Microsoft security solutions. Invoke an action for a specific provider, see all actions taken, and cancel an action if needed. Try security actions with [Microsoft Defender for Endpoint](/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) (formerly Microsoft Defender ATP) to block malicious activity on your Windows endpoints using properties seen in alerts or identified during investigations.

  > **Note:** Currently security actions only support application permissions.

## Alerts

Alerts are potential security issues within a customer's tenant that Microsoft or partner security solutions have identified and flagged for action or notification. With the Microsoft Graph Security [alerts](alert.md) entity, you can unify and streamline management of security issues across all integrated solutions. This also enables applications to correlate alerts and context to improve threat protection and response. With the alert update capability, you can sync the status of specific alerts across different security products and services that are integrated with the Microsoft Graph Security API by updating your [alerts](alert.md) entity.

Alerts from the following providers are available via the Microsoft Graph Security API. Support for GET alerts, PATCH alerts, and Subscribe (via webhooks) is indicated in the following table.

| Security provider | <p align="center">GET alert</p>| <p align="center">PATCH alert</p>| <p align="center">Subscribe to alert</p>|
|:------------------|:---------|:-----------|:------------------|
|[Azure Security Center](/azure/security-center/security-center-alerts-type)| <p align="center">&#x2713;</p> | <p align="center">&#x2713;</p> | <p align="center">&#x2713;</p> |
|[Azure Active Directory Identity Protection](/azure/active-directory/identity-protection/playbook) | <p align="center">&#x2713;</p> | <p align="center">[File issue](https://github.com/microsoftgraph/security-api-solutions/issues/new) *</p> | <p align="center">&#x2713;</p> |
| [Microsoft Defender for Cloud Apps](/cloud-app-security/monitor-alerts) (formerly Microsoft Cloud App Security) | <p align="center">&#x2713;</p> | <p align="center">[File issue](https://github.com/microsoftgraph/security-api-solutions/issues/new) *</p> | <p align="center">&#x2713;</p> |
|[Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/attack-simulations) (formerly Microsoft Defender ATP) **| <p align="center">&#x2713;</p> | <p align="center">&#x2713;</p> | <p align="center"> [File issue](https://github.com/microsoftgraph/security-api-solutions/issues/new) </p> |
|[Microsoft Defender for Identity](/azure-advanced-threat-protection/understanding-security-alerts#security-alert-categories) (formerly Azure Advanced Threat Protection) ***| <p align="center">&#x2713;</p> | <p align="center">[File issue](https://github.com/microsoftgraph/security-api-solutions/issues/new) *</p> | <p align="center">&#x2713;</p> |
|Microsoft 365 <ul><li> [Default](/office365/securitycompliance/alert-policies#default-alert-policies)</li> <li>[Cloud App Security](/office365/securitycompliance/anomaly-detection-policies-in-ocas)</li><li>Custom Alert</li></ul> | <p align="center">&#x2713;</p> | <p align="center"> [File issue](https://github.com/microsoftgraph/security-api-solutions/issues/new) </p> | <p align="center"> [File issue](https://github.com/microsoftgraph/security-api-solutions/issues/new) </p> |
|[Azure Information Protection](/azure/information-protection/faqs#i-see-azure-information-protection-is-listed-as-a-security-provider-for-microsoft-graph-securityhow-does-this-work-and-what-alerts-will-i-receive) **(preview)**| <p align="center">&#x2713;</p> | <p align="center">[File issue](https://github.com/microsoftgraph/security-api-solutions/issues/new) *</p> | <p align="center">&#x2713;</p> |
|[Azure Sentinel](/azure/sentinel/quickstart-get-visibility) **(preview)**| <p align="center">&#x2713;</p> | <p align="center">Not supported in Azure Sentinel </p> | <p align="center">&#x2713;</p> |
> **Note:** New providers are continuously onboarding to the Microsoft Graph Security ecosystem. To request new providers or for extended support from existing providers, [file an issue in the Microsoft Graph Security GitHub repo](https://github.com/microsoftgraph/security-api-solutions/issues/new).

\* File issue: Alert status gets updated across Microsoft Graph Security API integrated applications but not reflected in the provider’s management experience.

\*\* Microsoft Defender for Endpoint requires additional [user roles](/windows/security/threat-protection/microsoft-defender-atp/user-roles) to those required by the Microsoft Graph Security API. Only the users in both Microsoft Defender for Endpoint and Microsoft Graph Security API roles can have access to the Microsoft Defender for Endpoint data. Because application-only authentication is not limited by this, we recommend that you use an application-only authentication token.

\*\*\* Microsoft Defender for Identity alerts are available via the Microsoft Defender for Cloud Apps integration. This means you will get Microsoft Defender for Identity alerts only if you have joined Unified SecOps and connected Microsoft Defender for Identity into Microsoft Defender for Cloud Apps. Learn more about [how to integrate Microsoft Defender for Identity and Microsoft Defender for Cloud Apps](/azure-advanced-threat-protection/atp-mcas-integration).

## Attack simulation and training (preview)

[Attack simulation and training](/microsoft-365/security/office-365-security/attack-simulation-training) is part of [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365?view=o365-worldwide&preserve-view=true). This service lets users in a tenant experience a realistic benign phishing attack and learn from it. Social engineering simulation and training experiences for end users help reduce the risk of users being breached via those attack techniques. The attack simulation and training API enables tenant administrators to view launched [simulation](simulation.md) exercises and trainings, and get [reports](report-m365defender-reports-overview.md) on derived insights into online behaviors of users in the phishing simulations.

## eDiscovery (preview)

[Microsoft Purview eDiscovery (Premium)](/microsoft-365/compliance/overview-ediscovery-20) provides an end-to-end workflow to preserve, collect, analyze, review, and export content that's responsive to your organization's internal and external investigations.

## Information protection

**Labels** - Information protection labels provide details about how to properly apply a sensitivity label to information. The information protection label API describes the configuration of sensitivity labels that apply to a user or tenant.

**Threat assessment** - The Microsoft Graph threat assessment API helps organizations to assess the threat received by any user in a tenant. This empowers customers to report spam or suspicious emails, phishing URLs, or malware attachments they receive to Microsoft. Microsoft check the sample in question and the organizational policies in play before generating a result so that tenant administrators can understand the threat scanning verdict and adjust their organizational policy. They can also use it to report legitimate emails to prevent them from getting blocked.

> **Note:** We recommend that you use the [threat submission](https://github.com/microsoftgraph/microsoft-graph-docs/pull/16242/files#threat-submission) API instead.

## Secure Score

[Microsoft Secure Score](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Office-365-Secure-Score-is-now-Microsoft-Secure-Score/ba-p/182358) is a security analytics solution that gives you visibility into your security portfolio and how to improve it. With a single score, you can better understand what you have done to reduce your risk in Microsoft solutions. You can also compare your score with other organizations and see how your score has been trending over time. The Microsoft Graph Security [secureScore](securescores.md) and [secureScoreControlProfile](securescorecontrolprofiles.md) entities help you balance your organization's security and productivity needs while enabling the appropriate mix of security features. You can also project what your score would be after you adopt security features.

## Threat intelligence indicators (preview)

Threat indicators, also referred to as indicators of compromise (IoCs), represent data about known threats, such as malicious files, URLs, domains, and IP addresses. Customers can generate indicators through internal threat intelligence gathering or acquire indicators from threat intelligence communities, licensed feeds, and other sources. These indicators are then used in various security tools to defend against related threats.

The Microsoft Graph Security [tiIndicators](tiindicator.md) entity allows customers to feed threat indicators to Microsoft security solutions to enable block and alert actions on malicious activity or allow, which suppresses actions for indicators determined not to be relevant to an organization. When sending indicators, both the Microsoft solution that will utilize the indicator and the action to be taken on that indicator are specified.

You can integrate the [tiIndicator](tiindicator.md) entity into your application or use one of the following integrated threat intelligence platforms (TIP):

- [Palo Alto Networks MineMeld Threat Intelligence Sharing](https://www.paloaltonetworks.com/products/secure-the-network/subscriptions/minemeld)
- [MISP Open Source Threat Intelligence Platform](http://www.misp-project.org/) available through the [TI sample](https://aka.ms/tipmispsample)

Threat indicators sent via the Microsoft Graph Security API are available today in the following products:

- [Azure Sentinel](/azure/sentinel/overview) – Enables you to correlate threat indicators with log data to get alerts on malicious activity.
- [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) – Enables you to alert and/or block on threat indicators associated with malicious activity. You can also allow an indicator for ignoring the indicator from automated investigations. For details about the types of indicators supported and limits on indicator counts per tenant, see [Manage indicators](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).

Support in other Microsoft security services will be available soon.

## Threat submission

The Microsoft Graph threat submission API helps organizations to submit a threat received by any user in a tenant. This empowers customers to report spam or suspicious emails, phishing URLs, or malware attachments they receive to Microsoft. Microsoft checks the submission against the organizational policies in effect and sends it to human graders for analysis. The result then helps tenant administrators understand the threat scanning verdict and adjust their organizational policy. Admins can also use the results to report legitimate emails to prevent them from getting blocked.

> **Note: ** We recommend that you use this API instead of the deprecated Information Protection threat assessment API. The threat submission API provides unified security threat submission functionality and adds unified result support, user submission query support, tenant allow block list support, admin review support and app-only mode support.

## Common use cases

The following are some of the most popular requests for working with the Microsoft Graph Security API.

| **Use cases**   | **REST resources** | **Try it in Graph Explorer** |
|:---------------|:--------|:----------|
| **Actions (preview)**|||
| Get security action | [Get security action](../api/securityaction-get.md)|[https://graph.microsoft.com/beta/security/securityActions/{id}](https://developer.microsoft.com/graph/graph-explorer?request=security/securityActions/{id}&method=GET&version=beta&GraphUrl=https://graph.microsoft.com)|
|List security actions| [List security actions](../api/securityactions-list.md)|[https://graph.microsoft.com/beta/security/securityActions](https://developer.microsoft.com/graph/graph-explorer?request=security/securityActions&method=GET&version=beta&GraphUrl=https://graph.microsoft.com)|
|Create security actions|[Create security actions](../api/securityactions-post.md)|[https://graph.microsoft.com/beta/security/securityActions](https://developer.microsoft.com/graph/graph-explorer?request=security/securityActions&method=POST&version=beta&GraphUrl=https://graph.microsoft.com)|
|Cancel security action|[Cancel security actions](../api/securityaction-cancelsecurityaction.md)| [https://graph.microsoft.com/beta/security/securityActions/{id}/cancelSecurityAction](https://developer.microsoft.com/graph/graph-explorer?request=security/securityActions/{id}/cancelSecurityAction&method=POST&version=beta&GraphUrl=https://graph.microsoft.com) |
| **Alerts**|||
| List alerts | [List alerts](../api/alert-list.md) | [https://graph.microsoft.com/beta/security/alerts](https://developer.microsoft.com/graph/graph-explorer?request=security/alerts&method=GET&version=beta&GraphUrl=https://graph.microsoft.com) |
| Update alerts | [Update alert](../api/alert-update.md) </br> [Update multiple alerts](../api/alert-updatealerts.md) | [https://graph.microsoft.com/beta/security/alerts/{alert-id}](https://developer.microsoft.com/graph/graph-explorer?request=security/alerts/{alert-id}&method=PATCH&version=beta&GraphUrl=https://graph.microsoft.com) </br> [https://graph.microsoft.com/beta/security/alerts/updateAlerts](https://developer.microsoft.com/graph/graph-explorer?request=security/alerts/updateAlerts&method=POST&version=beta&GraphUrl=https://graph.microsoft.com) |
| **Attack simulation and training (preview)**|||
|List simulations|[List simulations](../api/attacksimulationroot-list-simulations.md)|[https://graph.microsoft.com/beta/security/attackSimulation/simulations](https://developer.microsoft.com/graph/graph-explorer?request=security/attackSimulation/simulations&method=GET&version=beta&GraphUrl=https://graph.microsoft.com)|
|Get simulation overview report|[Get simulation overview report](../api/simulationreportoverview-get.md)|[https://graph.microsoft.com/beta/security/attackSimulation/simulations/{id}/report/overview](https://developer.microsoft.com/graph/graph-explorer?request=security/attackSimulation/simulations/{id}/report/overview&method=GET&version=beta&GraphUrl=https://graph.microsoft.com)|
|List simulation users report|[List simulation users report](../api/usersimulationdetails-list.md)|[https://graph.microsoft.com/beta/security/attackSimulation/simulations/{id}/report/simulationUsers](https://developer.microsoft.com/graph/graph-explorer?request=security/attackSimulation/simulations/{id}/report/simulationUsers&method=GET&version=beta&GraphUrl=https://graph.microsoft.com)|
| **eDiscovery**|||
|List eDiscovery cases|[List eDiscoveryCases](../api/security-casesroot-list-ediscoverycases.md)|[https://graph.microsoft.com/beta/security/cases/eDiscoveryCases](https://developer.microsoft.com/graph/graph-explorer?request=security%2Fcases%2FeDiscoverycases&method=GET&version=beta&GraphUrl=https://graph.microsoft.com)|
|List eDiscovery case operations|[List caseOperations](../api/security-ediscoverycase-list-operations.md)|[https://graph.microsoft.com/beta/security/cases/eDiscoverycases/{id}/operations](https://developer.microsoft.com/graph/graph-explorer?request=security%2Fcases%2FeDiscoverycases%2F%7Bid%7D%2Foperations&method=GET&version=beta&GraphUrl=https://graph.microsoft.com)|
| **Secure scores**|||
|List secure scores|[List secureScores](../api/securescores-list.md)|[https://graph.microsoft.com/beta/security/secureScores](https://developer.microsoft.com/graph/graph-explorer?request=security/secureScores&method=GET&version=beta&GraphUrl=https://graph.microsoft.com)|
| **Secure score control profiles**|||
|List secure score control profiles|[List secureScoreControlProfiles](../api/securescorecontrolprofiles-list.md)|[https://graph.microsoft.com/beta/security/secureScoreControlProfiles](https://developer.microsoft.com/graph/graph-explorer?request=security/secureScoreControlProfiles&method=GET&version=beta&GraphUrl=https://graph.microsoft.com)|
|Update secure score control profiles|[Update secureScoreControlProfiles](../api/securescorecontrolprofiles-update.md)|[https://graph.microsoft.com/beta/security/secureScoreControlProfiles/{id}](https://developer.microsoft.com/graph/graph-explorer?request=security/secureScoreControlProfiles/{id}&method=PATCH&version=beta&GraphUrl=https://graph.microsoft.com)|
| **Threat intelligence indications (preview)**|||
|Get TI indicator|[Get tiIndicator](../api/tiindicator-get.md)| [https://graph.microsoft.com/beta/security/tiIndicators/{id}](https://developer.microsoft.com/graph/graph-explorer?request=security/tiIndicators/{id}&method=GET&version=beta&GraphUrl=https://graph.microsoft.com)|
|List TI Indicators | [List tiIndicators](../api/tiindicators-list.md) | [https://graph.microsoft.com/beta/security/tiIndicators](https://developer.microsoft.com/graph/graph-explorer?request=security/tiIndicators&method=GET&version=beta&GraphUrl=https://graph.microsoft.com)|
|Create TI Indicator|[Create tiIndicator](../api/tiindicators-post.md)|[https://graph.microsoft.com/beta/security/tiIndicators](https://developer.microsoft.com/graph/graph-explorer?request=security/tiIndicators&method=POST&version=beta&GraphUrl=https://graph.microsoft.com)|
|Submit TI Indicators|[Submit tiIndicators](../api/tiindicator-submittiindicators.md)| [https://graph.microsoft.com/beta/security/tiIndicators/submitTiIndicators](https://developer.microsoft.com/graph/graph-explorer?request=security/tiIndicators/submitTiIndicators&method=POST&version=beta&GraphUrl=https://graph.microsoft.com) |
|Update TI Indicators|[Update tiIndicator](../api/tiindicator-update.md) </br>[Update multiple tiIndicators](../api/tiindicator-updatetiindicators.md)| [https://graph.microsoft.com/beta/security/tiIndicators/{id}](https://developer.microsoft.com/graph/graph-explorer?request=security/tiIndicators/{id}&method=POST&version=beta&GraphUrl=https://graph.microsoft.com) </br>[https://graph.microsoft.com/beta/security/tiIndicators/updateTiIndicators](https://developer.microsoft.com/graph/graph-explorer?request=security/tiIndicators/updateTiIndicators&method=POST&version=beta&GraphUrl=https://graph.microsoft.com)|
|Delete TI Indicators|[Delete tiIndicator](../api/tiindicator-delete.md) </br>[Delete multiple tiIndicators](../api/tiindicator-deletetiindicators.md) </br>[Delete tiIndicator by externalId](../api/tiindicator-deletetiindicatorsbyexternalid.md)| DELETE </br>[https://graph.microsoft.com/beta/security/tiIndicators/{id}](https://developer.microsoft.com/graph/graph-explorer?request=security/tiIndicators/{id}&method=DELETE&version=beta&GraphUrl=https://graph.microsoft.com) </br>POST</br>[https://graph.microsoft.com/beta/security/tiIndicators/deleteTiIndicators](https://developer.microsoft.com/graph/graph-explorer?request=security/tiIndicators/deleteTiIndicators&method=POST&version=beta&GraphUrl=https://graph.microsoft.com)</br>POST</br>[https://graph.microsoft.com/beta/security/tiIndicators/deleteTiIndicatorsByExternalId](https://developer.microsoft.com/graph/graph-explorer?request=security/tiIndicators/deleteTiIndicatorsByExternalId&method=POST&version=beta&GraphUrl=https://graph.microsoft.com)|
| **Threat submission**|||
|Get email threat submission|[Get emailThreat](../api/security-emailthreatsubmission-get.md)| [https://graph.microsoft.com/beta/security/threatSubmission/emailThreats/{id}](https://developer.microsoft.com/graph/graph-explorer?request=security/threatSubmission/emailThreats/{id}&method=GET&version=beta&GraphUrl=https://graph.microsoft.com)|
|List email threat submissions | [List emailThreats](../api/security-emailthreatsubmission-list.md) | [https://graph.microsoft.com/beta/threatSubmission/emailThreats](https://developer.microsoft.com/graph/graph-explorer?request=threatSubmission/emailThreats&method=GET&version=beta&GraphUrl=https://graph.microsoft.com)|
|Create email threat submission|[Create emailThreat](../api/security-emailthreatsubmission-post-emailthreats.md)|[https://graph.microsoft.com/beta/security/threatSubmission/emailThreats](https://developer.microsoft.com/graph/graph-explorer?request=security/security/threatSubmission/emailThreats&method=POST&version=beta&GraphUrl=https://graph.microsoft.com)|
|Review email threat submission|[Review emailThreat](../api/security-emailthreatsubmission-review.md)|[https://graph.microsoft.com/beta/security/threatSubmission/emailThreats/{id}/review](https://developer.microsoft.com/graph/graph-explorer?request=security/security/threatSubmission//emailThreats/{id}/review&method=POST&version=beta&GraphUrl=https://graph.microsoft.com)|
|Get file threat submission|[Get fileThreat](../api/security-filethreatsubmission-get.md)| [https://graph.microsoft.com/beta/security/threatSubmission/fileThreats/{id}](https://developer.microsoft.com/graph/graph-explorer?request=security/threatSubmission/urlThreats/{id}&method=GET&version=beta&GraphUrl=https://graph.microsoft.com)|
|List file threat submissions | [List fileThreats](../api/security-filethreatsubmission-list.md) | [https://graph.microsoft.com/beta/threatSubmission/urlThreats](https://developer.microsoft.com/graph/graph-explorer?request=threatSubmission/fileThreats&method=GET&version=beta&GraphUrl=https://graph.microsoft.com)|
|Create file threat submission|[Create fileThreat](../api/security-filethreatsubmission-post-fileThreats.md)|[https://graph.microsoft.com/beta/security/threatSubmission/fileThreats](https://developer.microsoft.com/graph/graph-explorer?request=security/security/threatSubmission/fileThreats&method=POST&version=beta&GraphUrl=https://graph.microsoft.com)|
|Get url threat submission|[Get urlThreat](../api/security-urlthreatsubmission-get.md)| [https://graph.microsoft.com/beta/security/threatSubmission/urlThreats/{id}](https://developer.microsoft.com/graph/graph-explorer?request=security/threatSubmission/urlThreats/{id}&method=GET&version=beta&GraphUrl=https://graph.microsoft.com)|
|List url threat submissions | [List urlThreats](../api/security-urlthreatsubmission-list.md) | [https://graph.microsoft.com/beta/security/threatSubmission/urlThreats](https://developer.microsoft.com/graph/graph-explorer?request=threatSubmission/urlThreats&method=GET&version=beta&GraphUrl=https://graph.microsoft.com)|
|Create url threat submission|[Create urlThreat](../api/security-urlthreatsubmission-post-urlthreats.md)|[https://graph.microsoft.com/beta/security/threatSubmission/urlThreats](https://developer.microsoft.com/graph/graph-explorer?request=security/security/threatSubmission/urlThreats&method=POST&version=beta&GraphUrl=https://graph.microsoft.com)|
|Get email threat submission policy|[Get emailThreatSubmissionPolicy](../api/security-emailthreatsubmission-get.md)| [https://graph.microsoft.com/beta/security/threatSubmission/emailThreatSubmissionPolicies/{id}](https://developer.microsoft.com/graph/graph-explorer?request=security/threatSubmission/emailThreatSubmissionPolicies/{id}&method=GET&version=beta&GraphUrl=https://graph.microsoft.com)|
|List email threat submission policies | [List emailThreatSubmissionPolicies](../api/security-emailthreatsubmissionpolicy-list.md) | [https://graph.microsoft.com/beta/security/threatSubmission/emailThreatSubmissionPolicies](https://developer.microsoft.com/graph/graph-explorer?request=security/threatSubmission/emailThreatSubmissionPolicies&method=GET&version=beta&GraphUrl=https://graph.microsoft.com)|
|Create email threat submission policy|[Create emailThreatSubmissionPolicy](../api/security-emailthreatsubmission-post-emailthreats.md)|[https://graph.microsoft.com/beta/security/threatSubmission/emailThreatSubmissionPolicies](https://developer.microsoft.com/graph/graph-explorer?request=/security/threatSubmission/emailThreats&method=POST&version=beta&GraphUrl=https://graph.microsoft.com)|
|Update email threat submission policy|[Update emailThreatSubmissionPolicy](../api/security-emailthreatsubmission-post-emailthreats.md)|[https://graph.microsoft.com/beta/security/threatSubmission/emailThreatSubmissionPolicies/{id}](https://developer.microsoft.com/graph/graph-explorer?request=security/security/threatSubmission/emailThreatSubmissionPolicies/{id}&method=PATCH&version=beta&GraphUrl=https://graph.microsoft.com)|
|Delete email threat submission policy|[Delete emailThreatSubmissionPolicy](../api/security-emailthreatsubmissionpolicy-delete.md)|[https://graph.microsoft.com/beta/security/threatSubmission/emailThreatSubmissionPolicies/{id}](https://developer.microsoft.com/graph/graph-explorer?request=security/threatSubmission/emailThreatSubmissionPolicies/{id}&method=DELETE&version=beta&GraphUrl=https://graph.microsoft.com)|

You can use Microsoft Graph [webhooks](/graph/webhooks) to subscribe to and receive notifications about updates to Microsoft Graph Security API entities.

## What's new
Find out about the [latest new features and updates](/graph/whats-new-overview) for these API sets.

## Next steps

The Microsoft Graph Security API can open up new ways for you to engage with different security solutions from Microsoft and partners. Follow these steps to get started:

- Drill down into [alerts](alert.md), [tiIndicator](tiindicator.md) (preview), [securityAction](securityaction.md) (preview), [secureScore](securescores.md), and [secureScoreControlProfiles](securescorecontrolprofiles.md).
- Try the API in the [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer). Under **Sample Queries**, choose **show more samples** and set the Security category to **on**.
- Try [subscribing to and receiving notifications](/graph/webhooks) on entity changes.

Need more ideas? See [how some of our partners are using Microsoft Graph](https://developer.microsoft.com/graph/partners).

## See also

[Code and contribute](https://github.com/microsoftgraph/security-api-solutions/blob/master/CONTRIBUTING.md) to these Microsoft Graph Security API samples:

- [ASP.NET (C#) sample](https://github.com/microsoftgraph/aspnet-security-api-sample)
- [Python sample](https://github.com/microsoftgraph/python-security-rest-sample)
- [Node.js (JavaScript) sample](https://github.com/microsoftgraph/nodejs-security-sample)
- [PowerShell sample](https://aka.ms/graphsecuritypowershellsample)
- [Other samples or contribute a new sample](https://aka.ms/graphsecurityapicode)

Explore other options to connect with the Microsoft Graph Security API:

- [Microsoft Graph Security connectors for Logic Apps, Flow and Power Apps](/azure/connectors/connectors-integrate-security-operations-create-api-microsoft-graph-security)
- [Jupyter notebook samples](https://aka.ms/graphsecurityjupyternotebooks)

Engage with the community:

- [Join the tech community](https://techcommunity.microsoft.com/t5/microsoft-graph-security-api/bd-p/SecurityGraphAPI)
- [Discuss on StackOverflow](https://stackoverflow.com/questions/tagged/microsoft-graph-security)