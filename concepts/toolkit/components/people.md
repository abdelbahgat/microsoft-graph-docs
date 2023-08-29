---
title: "People component in the Microsoft Graph Toolkit"
description: "You can use the `mgt-people` web component to display a group of people or contacts by using their photos or initials."
ms.localizationpriority: medium
author: sebastienlevert
---

# People component in the Microsoft Graph Toolkit

You can use the `mgt-people` web component to display a group of people or contacts by using their photos or initials. By default, it will display the most frequent contacts for the signed in user.

This component uses multiple [mgt-person](./person.md) controls, but it can be bound to a set of people descriptors. If there are more people to display than the `show-max` value, a number will be added to indicate the number of additional contacts.

## Example

The following example shows a group of people displayed using the `mgt-people` component. You can use the code editor to see how [properties](#properties) change the behavior of the component.

<iframe src="https://mgt.dev/iframe.html?id=components-mgt-people--people&source=docs" height="350"></iframe>

[Open this example in mgt.dev](https://mgt.dev/?path=/story/components-mgt-people--people&source=docs)

## Properties

By default, the `mgt-people` component fetches events from the `/me/people` endpoint with the `personType/class eq 'Person'` filter to display frequently contacted users. You can use several properties to change this behavior.

| Attribute | Property | Description |
| --- | --- | --- |
| show-max | showMax | Indicates the maximum number of people to show. Default value is 3. |
| people | people | An array of people to get or set the list of people rendered by the component. Use this property to access the people loaded by the component. Set this value to load your own people. |
| group-id | groupId | Retrieves people from a specific Microsoft Graph from the respective ID. |
| user-ids | userIds | Given an array of Microsoft Graph user `ids`, the component will render these users.  |
| people-queries | peopleQueries | Given an array of person queries (names, upns, emails), the component will render these users. |
| person-card | personCard | An enumeration to determine user action necessary to activate flyout panel - `hover`, `click`, or `none`. Default value is `hover`. |
| show-presence | showPresence | A Boolean to determine whether to show person presence badge on person image. |
| resource | resource | The resource to get from Microsoft Graph (for example, `/me/people`). |
| scopes | scopes | Optional array of strings if using the property or a comma delimited scope if using the attribute. The component will use these scopes (with a supported provider) to ensure that the user has consented to the right permission. |
| version | version | Optional API version to use when making the GET request. Default is `v1.0`.  |
| fallback-details| fallbackDetails| Array of IDynamicPerson objects representing a person or multiple people when no user/person/contact is found in the graph.

The following example sets the maximum number of people to show.

```html
<mgt-people
  show-max="4">
</mgt-people>
```

## CSS custom properties

The `mgt-people` component defines the following CSS custom properties.

```css
mgt-people {
  --list-margin: 8px 4px 8px 8px; /* Margin for component */
  --avatar-margin: 0 4px 0 0; /* Margin for each person */
  --color: #000000 /* Text color */
}
```

## Templates

The `mgt-people` supports several [templates](../customize-components/templates.md) that you can use to replace certain parts of the component. To specify a template, include a `<template>` element inside a component and set the `data-type` value to one of the following.

| Data type | Data context | Description |
| --- | --- | --- |
| `default` | `people`: list of person objects | The default template replaces the entire component with your own. |
| `person` | `person`: person object | The template used to render each person. |
| `overflow` | `people`: list of person objects <br> `max`: number of shown people <br> `extra`: number of extra people | The template used to render the number beyond the max to the right of the list of people. |
| `no-data` | No data context is passed | The template used when no data is available. |
| `loading` | No data context is passed | The template used while the component loads state.

The following examples shows how to use the `person` template.

```html
<mgt-people>
  <template>
    <ul><li data-for="person in people">
      <mgt-person person-query="{{ person.userPrincipalName }}"></mgt-person>
      <h3>{{ person.displayName }}</h3>
      <p>{{ person.jobTitle }}</p>
      <p>{{ person.department }}</p>
    </li></ul>
  </template>
</mgt-people>
```

## Microsoft Graph permissions

This component uses the following Microsoft Graph APIs and permissions:

| Configuration | Permission | API
| --- | ---------- | ------- |
| `groupId` set | GroupMember.Read.All | [/groups/\${groupId}/members](/graph/api/group-list-members) |
| `userIds` set | User.ReadBasic.All | [/users/${userId}](/graph/api/user-get) |
| `peopleQueries` set | People.Read | [/me/people](/graph/api/user-list-people) |
| `resource` set | Permissions specified in `scopes` | Specified in `resource` |
| default configuration | People.Read | [/me/people](/graph/api/user-list-people) |
| `showPresence` set | Presence.Read.All | [/communications/getPresencesByUserId](/graph/api/cloudcommunications-getpresencesbyuserid) |

When using the default templates, additional APIs and permissions are required. The default template for this component uses a [mgt-person](person.md) component. See its documentation for the list of required permissions.

## Authentication

The control uses the global authentication provider described in the [authentication documentation](../providers/providers.md).

## Cache

|Object store|Cached data|Remarks|
|---------|-----------|-------|
|`people`|Information about people matching the query|Used when `resource` specified|
|`users`|Information about users matching the query|Used when `groupId`, `userIds`, `peopleQueries` or no properties specified|
|`presence`|Presence for the specified set of people|Used when `showPresence` set to `true`|

> [!NOTE]
> By default, the `mgt-people` component uses the [`mgt-person`](./person.md) component to display information about people. The `mgt-person` component automatically downloads and caches the photo for each person.

For details about how to configure the cache, see [Caching](../customize-components/cache.md).
## Extend for more control

For more complex scenarios or a truly custom UX, this component exposes several `protected render*` methods for override in component extensions.

| Method | Description |
| - | - |
| renderLoading | Renders the loading state. |
| renderNoData | Renders the empty data state. |
| renderPeople | Renders a list of people, up to the `show-max` value. |
| renderPerson | Renders an individual person. |
| renderOverflow | Renders a representation of remaining people beyond the `show-max` value. |
