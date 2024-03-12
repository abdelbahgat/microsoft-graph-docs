---
title: "Deploy, test, and extend migrated apps"
description: "Describes how to migrate Azure Active Directory (Azure AD) Graph apps to use the Microsoft Graph API (REST); this discusses step 3: deploy, test, and extend."
author: "FaithOmbongi"
ms.author: ombongifaith
ms.reviewer: dkershaw
ms.localizationpriority: medium
ms.prod: "applications"
ms.date: 11/11/2022
---

# Deploy, test, and extend

This is step 4 of the [process to migrate apps](migrate-azure-ad-graph-planning-checklist.md).

1.  **Test throughly**

    Once you've updated your app, test it thoroughly to verify that it works as expected and that you haven't introduced any regressions.  

    Be sure to use multiple environments, data sets, and end-user personas, e.g. credentials with different roles, rights, and responsibilities. Go through the entire lifecycle, by having a new test user acquire the app for the first time, as well as an existing user (who already consented) trying to use the app again.

2.  **Deploy staged updates**

    Consider deploying your updates in stages.  A limited roll-out to a small set of friendly users can help identify glitches and other potentially-embarrassing issues.  This also gives you a chance to monitor initial reception and feedback.

    If the initial roll-out goes well, monitor progress as you deploy to larger audiences.

3.  **Explore new value**

    Now you've made the switch to Microsoft Graph, it's never been easier for you to unlock many more datasets and features that are now at your fingertips. 
    Microsoft Graph supports many new Azure Active Directory (Azure AD) datasets and features that are not available in Azure Active Directory (Azure AD) Graph.

    Microsoft Graph offers access to many more services than just Azure Active Directory. It's the [API gateway to Microsoft 365 services too](./index.yml).
    Check for new datasets and capabilities regularly.  

    - See [Major services and features in Microsoft Graph](overview-major-services.md).
    - Take a look at some [partner solutions](https://developer.microsoft.com/graph/partners).
    - Explore the [Microsoft Graph blog](https://developer.microsoft.com/graph/blogs) for the latest news about Microsoft Graph and some great learning series.
    - The [changelog](/graph/changelog) summarizes service and document updates. Following these updates will help you track new APIs introduced to /beta (preview) and those promoted to v1.0 (GA).  These new APIs can provide new ways for you to add more value and new experiences to your apps.  

## See also

If you run into problems or need help during the migration process, you can:

- Review the [checklist](migrate-azure-ad-graph-planning-checklist.md) again
- Post questions to [Microsoft Graph on Q&A](/answers/topics/microsoft-graph-applications.html) 
- Review Microsoft Graph samples to contrast and compare with your existing application code:
  - **Apps that use the REST API**: explore [quick starts and samples](https://developer.microsoft.com/graph/get-started), choose your platform of choice and run through the quick start or search for an appropriate sample
  - **App that use the .NET client library**: review [console-csharp-snippets-sample](https://github.com/microsoftgraph/console-csharp-snippets-sample) or [dotnetcore-console-sample](https://github.com/microsoftgraph/dotnetcore-console-sample)

## Next Steps

- Use [quick starts and samples](https://developer.microsoft.com/graph/get-started) to come up to speed quickly.
- Leverage [client libraries and SDKs](/graph/sdks/sdks-overview) to develop custom applications 
- Explore [Microsoft Graph](./overview.md) concepts and practices.
- Use [Graph Explorer](https://aka.ms/ge) to experiment with Microsoft Graph.
