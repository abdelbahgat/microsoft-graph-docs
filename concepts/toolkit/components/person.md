---
title: "Person component in Microsoft Graph Toolkit"
description: "The person component is used to display a person or contact by using their photo, name, and/or email address."
ms.localizationpriority: medium
author: sebastienlevert
---

# Person component in Microsoft Graph Toolkit

The person component is used to display a person or contact by using their photo, name, email address, or any other person details.

The person component also uses the [mgt-person-card](./person-card.md) to display a flyout card with additional information about the user. For details, see the [Person Card](#person-card) section.

## Example

The following example displays a person using the `mgt-person` component. You can use the code editor to see how [properties](#properties) change the behavior of the component.

<iframe src="https://mgt.dev/iframe.html?id=components-mgt-person--person&source=docs" height="250"></iframe>

[Open this example in mgt.dev](https://mgt.dev/?path=/story/components-mgt-person--person&source=docs)

## Setting the person details

You can use three properties to set the person details. Use only one of the following properties per instance:

* Set the `user-id` attribute or `userId` property to fetch the user from Microsoft Graph by using their ID.

* Set the `person-query` attribute or `personQuery` property to search Microsoft Graph for a given person. It will choose the first person available and fetch the person details. An email works best to ensure the right person is queried, but a name works as well.

* Set the `person-presence` attribute or `personPresence` property to add a presence badge to person avatar manually.

* Set the `avatar-size` attribute or `avatarSize` property to `small` or `large` to determine the size of avatar. This helps add the [correct presence badge](https://mgt.dev/?path=/story/components-mgt-person--person-presence-display-all) to avatar. You will need to choose the correct corresponding css custom properties shown below to further customize avatar size. By default, the value is set to `auto` which will automatically decide how to render the presence based on the `view` property. We recommend using `small` if your avatar is smaller than 32px by 32px. 

* Use the `person-details` attribute or `personDetails` property to manually set the person details, as shown in the following example.


    ```js
    let personControl = document.getElementById('myPersonControl');
    personControl.personDetails = {
        displayName: 'Nikola Metulev',
        mail: 'nikola@contoso.com',
        personImage: 'url'
    }
    ```

  If no image is provided, one will be fetched (if available).

* By default, the person component will only request the standard Microsoft Graph user set of [properties](/graph/api/user-get?&tabs=http#optional-query-parameters). In order to request additional properties, declare them as any part of the `line(x)Property`. 


## Properties

You can use several properties to customize the component.

| Attribute       | Property       | Description                                                   |
| -----------     | ----------     | ------------------------------------------------------------- |
| user-id         | userId         | Set to a user ID to fetch that user's details and image from Microsoft Graph.|
| person-query    | personQuery    | Set to a name or email of a person to search for a person in Microsoft Graph and fetch the first person's details and image.|
| person-details  | personDetails  | Set to an object representing a person. Works with object from the people, users, contacts, or group, resources. |
| fallback-details| fallbackDetails| Set to an object representing a person when no user/person/contact is found in the graph.
| person-image    | personImage    | Set the image to show for the person. |
| person-presence | personPresence | Set the presence for the person. |
| fetch-image     | fetchImage     | Set flag to fetch `personImage` automatically from Microsoft Graph based on the `personDetails` object provided by the user. |
| disable-image-fetch | disableImageFetch | Set flag to disable fetching of person image. Can be used to avoid unnecessary fetching from Microsoft Graph when specifying `personImage` property.
| avatar-type     | avatarType     | Set to `initials` or `photo` to render either display state - default is photo. |
| avatar-size     | avatarSize     | Set to `small`, `large`, or `auto` to  determine the size of avatar. This helps to set the correct size for the presence badge. Default is auto. |
| view            | view           | Set to control how the person is rendered. Default is `avatar` <br /> `avatar` - show only avatar <br /> `oneline` - show avatar and first line (`displayName` by default) <br /> `twolines` - show avatar and two lines of text (`displayName` and `mail` by default) <br /> `threelines` - show avatar and three lines of text (`displayName`, `mail` and `jobTitle` by default) |
| line1-property  | line1Property  | Sets the property of the personDetails to use for the first line of text. Default is `displayName`.|
| line2-property  | line2Property  | Sets the property of the personDetails to use for the second line of text. Default is `mail`.|
| line3-property  | line3Property  | Sets the property of the personDetails to use for the third line of text. Default is `jobTitle`.|
| show-presence   | showPresence   | Set flag to display person presence - default is `false`.|
| usage | usage | Specify where the component is being used in order to add customized personalization for it. Currently only supports `people` as used in the people component. |

## CSS custom properties

The `mgt-person` component defines the following CSS custom properties.

```css
mgt-person {
  --avatar-size: 48px;
  --avatar-border: 0;
  --avatar-border-radius: 50%;
  --avatar-cursor: default;
  
  --initials-color: white;
  --initials-background-color: magenta;

  --presence-background-color: #ffffff;
  --presence-icon-color: #ffffff;

  --font-family: 'Segoe UI';
  --font-size: 14px;
  --font-weight: 500;
  --color: black;
  --text-transform: none;

  --line2-font-size: 12px;
  --line2-font-weight: 400;
  --line2-color: black;
  --line2-text-transform: none;

  --line3-font-size: 12px;
  --line3-font-weight: 400;
  --line3-color: black;
  --line3-text-transform: none;

  --details-spacing: 12px;
}
```

To learn more, see [styling components](../customize-components/style.md).

## Events

The following events are fired from the component.

Event | When is it emitted | Custom data | Cancelable | Bubbles | Works with custom template
------|-------------------|--------------|:-----------:|:---------:|:---------------------------:|
`line1clicked` | Fired when line1 is clicked | The `person` object which can be a Graph [user](/graph/api/resources/user), [person](/graph/api/resources/person) or [contact](/graph/api/resources/contact) with an additional `personImage` property that contains the URL of the user's photo | No | No | Yes, unless you override the default template
`line2clicked` | Fired when line2 is clicked | The `person` object which can be a Graph [user](/graph/api/resources/user), [person](/graph/api/resources/person) or [contact](/graph/api/resources/contact) with an additional `personImage` property that contains the URL of the user's photo | No | No | Yes, unless you override the default template
`line3clicked` | Fired when line3 is clicked | The `person` object which can be a Graph [user](/graph/api/resources/user), [person](/graph/api/resources/person) or [contact](/graph/api/resources/contact) with an additional `personImage` property that contains the URL of the user's photo | No | No | Yes, unless you override the default template

For more information about handling events, see [events](../customize-components/events.md).

## Templates

The `mgt-person` component supports several [templates](../customize-components/templates.md) that allow you to replace certain parts of the component. To specify a template, include a `<template>` element inside a component and set the `data-type` value to one of the following:

| Data type | Data context | Description |
| --------- | ------------ | ----------- |
| loading | none | The template to render while the component is in a loading state. |
| no-data | none | The template to render when no person image or data is available. | 
| default | person: The person details object <br> `personImage`: The URL of the image <br> `personPresence`: The presence details object for person  | The default template replaces the entire component with your own. |
| person-card | person: The person details object <br> `personImage`: The URL of the image | The template to update the mgt-person-card displayed on hover or click. |
| line1 | person: The person details object | The template for the first line of person metadata. |
| line2 | person: The person details object | The template for the second line of person metadata. |
| line3 | person: The person details object | The template for the third line of person metadata. |

The following example defines a template for the person component.

```html
<!-- Retemplate the entire person component -->
<mgt-person>
  <template>
    <div data-if="personImage">
      <img src="{{personImage}}" />
    </div>
    <div data-else>
      {{person.displayName}}
    </div>
  </template>
</mgt-person>

<!-- Retemplate the line properties -->
<mgt-person view="threeLines">
  <template data-type="line1">
    <div>
      Hello, my name is: {{person.displayName}}
    </div>
  </template>
  <template data-type="line2">
    <div>
      Super cool
    </div>
  </template>
  <template data-type="line3">
    <div>
      Loves MGT
    </div>
  </template>
</mgt-person>
```

## Person card

The `mgt-person` component can show an `mgt-person-card` on either hover or click.

### Add the control to the HTML page
```html
<mgt-person person-query="me" person-card="hover"></mgt-person>
```

| Attribute    |  Property     | Description                                                                     |
| ------------ | ------------- | ------------------------------------------------------------------------------- |
| person-card | personCardInteraction | An enumeration to determine user action necessary to activate flyout panel - `hover` or `click`. Default value is `none` |


For more information about templating, styling, and attributes, see [Person Card component](./person-card.md).

## Global component configuration

The `MgtPerson` class exposes a static `config` object that configures all person components in the application.

The following example shows how to use the config object.

```ts
import { MgtPerson } from `@microsoft/mgt`;

MgtPerson.config.useContactApis = false;
```

The following properties are available on the config object.

| Property | Description |
| ------------ | ------------- |
| useContactApis | `boolean` - Indicates whether the person component can use Microsoft Graph personal contacts API to search for contact details and photos. Default value is `true`.  |

## Microsoft Graph permissions

This control uses the following Microsoft Graph APIs and permissions.

| Configuration | Permission | API |
| ------------- | ---------- | --- |
| `personDetails` set without image, `fetchImage` set to `true`, `avatarType` set to `photo`, retrieved person is a contact and `useContactApis` set to `true` | Contacts.Read | [/me/contacts/\*](/graph/api/user-list-contacts) |
| `personDetails` set without image, `fetchImage` set to `true`, `avatarType` set to `photo` and person is not a contact or `useContactApis` is set to `false` | User.ReadBasic.All | [/users/{id}/photo/$value](/graph/api/profilephoto-get) |
| `personDetails` set without image, `fetchImage` set to `true`, `avatarType` set to `photo` and user specified via email | User.ReadBasic.All | [/users/{id}/photo/$value](/graph/api/profilephoto-get) |
| `personDetails` set without image, `fetchImage` set to `true`, `avatarType` set to `photo` and contact specified via email | Contacts.Read | [/me/contacts/\*](/graph/api/user-list-contacts) |
| `userId` set | User.ReadBasic.All | [/users/{id}](/graph/api/user-list-people) |
| `personQuery` set to `me` and `avatarType` set to `photo` | User.Read | [/me/photo/$value](/graph/api/profilephoto-get) |
| `personQuery` set to `me` and `avatarType` set to something else than `photo` | User.Read | [/me](/graph/api/user-get) |
| `personQuery` set to a value other than `me` and `useContactApis` set to `true` | People.Read, User.ReadBasic.All, Contacts.Read | [/me/people/?$search=](/graph/api/user-list-people), [/users?$search=](/graph/api/user-list-people), [/me/contacts/\*](/graph/api/user-list-contacts) |
| `personQuery` set to a value other than `me` and `useContactApis` set to `false` | People.Read, User.ReadBasic.All | [/me/people/?$search=](/graph/api/user-list-people), [/users?$search=](/graph/api/user-list-people) |
| `showPresence` set to `true` and `personQuery` set to `me` | Presence.Read | [/me/presence](/graph/api/presence-get) |
| `showPresence` set to `true` and `personQuery` set to a value other than `me` | Presence.Read.All | [/users/{id}/presence](/graph/api/presence-get) |
| `personCardInteraction` set to a value other than `PersonCardInteraction.none` | See [person card permissions](/graph/toolkit/components/person-card#microsoft-graph-permissions) | See [person card API calls](/graph/toolkit/components/person-card#microsoft-graph-permissions) |

## Authentication

The control uses the global authentication provider described in the [authentication documentation](../providers/providers.md) to fetch the required data.

## Cache

|Object store|Cached data|Remarks|
|---------|-----------|-------|
|`photos`|Person's photo|Used, when `avatarType` is set to `photo` and `fetchImage` is set to `true`|
|`presence`|Person's presence|Used, when `showPresence` is set to `true`|
|`users`|Person's user information|

See [Caching](../customize-components/cache.md) for more details on how to configure the cache.

## Extend for more control

For more complex scenarios or a truly custom UX, this component exposes several `protected render*` methods for override in component extensions.

| Method | Description |
| - | - |
| renderLoading | Renders the loading state. |
| renderNoData | Renders when no image or person data is available. |
| renderAvatar | Renders the avatar. |
| renderDetails | Renders the person details part. |
