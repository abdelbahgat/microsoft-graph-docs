---
title: "Build a web application with Microsoft Graph Toolkit"
description: "Get started building a web application using Microsoft Graph Toolkit."
ms.localizationpriority: medium
author: sebastienlevert
---

# Build a web application with the Microsoft Graph Toolkit

This topic describes how to get started with Microsoft Graph Toolkit in a web application written in vanilla JavaScript. For a step-by-step tutorial, try the [Get started with Microsoft Graph Toolkit module](/training/modules/msgraph-toolkit-intro/). If you would like to learn how to use the Toolkit with a web framework, see [Build a web app (React)](./use-toolkit-with-react.md) or [Build a web app (Angular)](./use-toolkit-with-angular.md).

Getting started with the Toolkit involves the following steps:

1. Add Microsoft Graph Toolkit to your project.
2. Initialize the MSAL2 Provider.
3. Add components.
4. Test your application.

## Add Microsoft Graph Toolkit to your project

You can use Microsoft Graph Toolkit in your application by referencing the loader directly (via unpkg) or by installing the npm package.

# [unpkg](#tab/html)

To use the Toolkit via mgt-loader, add the reference in a script to your code:

```html
<script src="https://unpkg.com/@microsoft/mgt@3/dist/bundle/mgt-loader.js"></script>
```

# [npm](#tab/npm)

Using the Toolkit via ES6 modules will give you full control of the bundling process and allow you to bundle only the code you need for your application. To use the ES6 modules, add the npm package to your project:

```cmd
npm install @microsoft/mgt
```

---

## Initialize the MSAL2 Provider

The Microsoft Graph Toolkit providers enable authentication and access to Microsoft Graph for the components. To learn more, see [Using the providers](../providers/providers.md). The [MSAL2 Provider](../providers/msal2.md) uses MSAL-browser to sign in users and acquire tokens. You can initialize this provider in your HTML or JavaScript.

> **Note**: If you're currently using the MSAL Provider and would like to update to MSAL2 Provider, see [Migrating from MSAL Provider to MSAL2 Provider](../providers/msal2.md#migrating-from-msal-provider-to-msal2-provider).
> If you want to use your own backend authentication, use the [Proxy Provider](../providers/proxy.md) in place of the MSAL2 Provider.

You can choose to initialize the provider in either your HTML or your JavaScript code.

# [HTML](#tab/HTML)

Add the `mgt-msal2-provider` component to your HTML page and set the `client-id` to your application client-id.

```html
<mgt-msal2-provider client-id="<YOUR_CLIENT_ID>"></mgt-msal2-provider>
```

# [JavaScript](#tab/JavaScript)

To initialize the MSAL provider in your JavaScript, add the following code to your application:

```javascript
import { Providers } from "@microsoft/mgt-element";
import { Msal2Provider } from "@microsoft/mgt-msal2-provider";

Providers.globalProvider = new Msal2Provider({
  clientId: "<YOUR_CLIENT_ID>",
});
```

---

The client ID is the only property required to initialize the provider, but you can set additional options. For the full list, see [MSAL2 Provider](../providers/msal2.md).

### Creating an app/client ID

In order to get a client ID, you need to [register your application](./add-aad-app-registration.md) in Microsoft Entra ID.

## Add components

After you initialize the MSAL2 provider, you can start using any of the Toolkit components.

# [HTML](#tab/HTML)

The following is a full working example using mgt-loader, the MSAL2 Provider initialized in HTML, and the Login component:

```html
<script src="https://unpkg.com/@microsoft/mgt@3/dist/bundle/mgt-loader.js"></script>
<mgt-msal2-provider client-id="<YOUR_CLIENT_ID>"></mgt-msal2-provider>
<mgt-login></mgt-login>
```

This is an example using the ES6 modules, the MSAL2 Provider initialized in HTML, and the Login component:

```html
<script
  type="module"
  src="node_modules/@microsoft/mgt/dist/es6/index.js"
></script>
<mgt-msal2-provider client-id="<YOUR_CLIENT_ID>"></mgt-msal2-provider>
<mgt-login></mgt-login>
```

# [JavaScript](#tab/JavaScript)

This is an example using the ES6 modules, the MSAL2 Provider initialized in JavaScript, and the Login component:

```javascript
import { Providers } from "@microsoft/mgt-element";
import { Msal2Provider } from "@microsoft/mgt-msal2-provider";

Providers.globalProvider = new Msal2Provider({
  clientId: "<YOUR_CLIENT_ID>",
});

function component() {
  const element = document.createElement("div");
  element.innerHTML = "<mgt-login></mgt-login>";
  return element;
}

document.body.appendChild(component());
```

---

## Test your app

In order to test your app, MSAL requires the page to be hosted in a web server for the authentication redirects.

If you're just getting started and want to play around, you can use [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) in Visual Studio Code or any similar lightweight development server. Download the extension and open your HTML file using live server.

> **Note:** Make sure the **redirect URI** in your app registration is set to the localhost port your application is hosted on. Go to your app registration in the [Microsoft Entra admin center](https://entra.microsoft.com), click **Authentication** under manage, and add the correct **redirect URI**.

## Track a user's sign in state

You can detect when a user has successfully signed in and display specific components accordingly. For example, display the agenda component if the user has signed in. Otherwise, display the sign in interface.

To properly inspect the user's sign in state, add an event handler to the `providerUpdated` event using the `Providers.onProviderUpdated` function. In the handler, check the provider state stored on the `Providers.globalProvider.state` property.

# [HTML](#tab/HTML)

If you're using the `mgt-loader` library, you can access the `Provider` and `ProviderState` from the global `mgt` property.

```html
<!DOCTYPE html>
<html>
  <head>
    <script src="https://unpkg.com/@microsoft/mgt@3/dist/bundle/mgt-loader.js"></script>
  </head>
  <body>
    <mgt-msal2-provider client-id="<YOUR_CLIENT_ID>"></mgt-msal2-provider>
    <div id="main">
      <mgt-login></mgt-login>
    </div>
    <script>
      const loadAgenda = () => {
        if (mgt.Providers.globalProvider.state === mgt.ProviderState.SignedIn) {
          document.getElementById("main").innerHTML =
            "<mgt-agenda></mgt-agenda>";
        }
      };
      mgt.Providers.onProviderUpdated(loadAgenda);
    </script>
  </body>
</html>
```

# [JavaScript](#tab/JavaScript)

If you're using the toolkit via the npm packages, you can import the `Provider` and `ProviderState` from `@microsoft/mgt`.

```javascript
import { Providers, ProviderState } from "@microsoft/mgt-element";
import { Msal2Provider } from "@microsoft/mgt-msal2-provider";

Providers.globalProvider = new Msal2Provider({
  clientId: "<YOUR_CLIENT_ID>",
});

const loadAgenda = () => {
  if (Providers.globalProvider.state === ProviderState.SignedIn) {
    document.getElementById("main").innerHTML = "<mgt-agenda></mgt-agenda>";
  }
};

Providers.onProviderUpdated(loadAgenda);
```

---

## Next Steps

- Check out the [Get started with Microsoft Graph Toolkit](/training/modules/msgraph-toolkit-intro/) step-by-step tutorial.
- Try out the components in the [playground](https://mgt.dev).
- Ask a question on [Stack Overflow](https://aka.ms/mgt-question).
- Report bugs or leave a feature request on [GitHub](https://aka.ms/mgt/issues).
