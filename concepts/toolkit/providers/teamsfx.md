---
title: "TeamsFx provider"
description: "Use the TeamsFx provider inside your Microsoft Teams applications to provide Microsoft Graph Toolkit components access to Microsoft Graph."
ms.localizationpriority: medium
author: sebastienlevert
---

# TeamsFx provider

Use the TeamsFx provider inside your Microsoft Teams applications to provide Microsoft Graph Toolkit components access to Microsoft Graph.

To learn more about authentication providers, see [Providers](./providers.md).

## Get started

1. Initialize the provider and login to get the required access token

    ### Use TeamsUserCredential (Recommended)

    1. Initialize the provider inside your component.
        ```ts
            // Import the providers and credential at the top of the page
            import {Providers} from '@microsoft/mgt-element';
            import {TeamsFxProvider} from '@microsoft/mgt-teamsfx-provider';
            import {TeamsUserCredential, TeamsUserCredentialAuthConfig} from "@microsoft/teamsfx";
            const authConfig: TeamsUserCredentialAuthConfig = {
                clientId: process.env.REACT_APP_CLIENT_ID,
                initiateLoginEndpoint: process.env.REACT_APP_START_LOGIN_PAGE_URL,
            };
            const scope = ["User.Read"];
            const credential = new TeamsUserCredential(authConfig);
            const provider = new TeamsFxProvider(credential, scope);
            Providers.globalProvider = provider;
        ```
    1. Use the `credential.login(scopes)` method to get the required access token.

        ```ts
            // Put these code in a call-to-action callback function to avoid browser blocking automatically showing up pop-ups. 
            await credential.login(this.scope);
            Providers.globalProvider.setState(ProviderState.SignedIn);
        ```

    ### Use TeamsFx class
    > Note: TeamsFx class will be deprecated and removed from future release of TeamsFx SDK, and it is recommended to use `TeamsUserCredential` instead
    1. Initialize the provider inside your component.

        ```ts
            // Import the providers and credential at the top of the page
            import {Providers} from '@microsoft/mgt-element';
            import {TeamsFxProvider} from '@microsoft/mgt-teamsfx-provider';
            import {TeamsUserCredential} from "@microsoft/teamsfx";
            const scope = ["User.Read"];
            const teamsfx = new TeamsFx();
            const provider = new TeamsFxProvider(teamsfx, scope);
            Providers.globalProvider = provider;
        ```

    1. Use the `teamsfx.login(scopes)` method to get the required access token.

        ```ts
            // Put these code in a call-to-action callback function to avoid browser blocking automatically showing up pop-ups. 
            await teamsfx.login(this.scope);
            Providers.globalProvider.setState(ProviderState.SignedIn);
        ```

1. Now you can add any component in your HTML page or in your `render()` method when using React and it will use the TeamsFx context to access Microsoft Graph.

    ```html
    <!-- Using HTML -->
    <mgt-person query="me" view="threeLines"></mgt-person>
    ```

    ```ts
    // Using React
    public render(): void {
      return (
          <div>
            <Person personQuery="me" view={PersonViewType.threelines}></Person>
          </div>
      );
    }
    ```

For a sample that shows you how to initialize the TeamsFx provider, see the [Contacts Exporter sample](https://github.com/OfficeDev/TeamsFx-Samples/tree/dev/hello-world-tab-with-backend).


## See also
* [Get started with Microsoft Teams and Teams Toolkit development](https://aka.ms/teamsfx-docs)
* [TeamsFx SDK](/microsoftteams/platform/toolkit/teamsfx-sdk)
* [One Productivity Hub workshop](https://github.com/OfficeDev/OneProductivityHub-TeamsFx)
