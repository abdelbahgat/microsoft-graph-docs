---
title: "Tasks component in Microsoft Graph Toolkit"
description: "The Tasks component enables the user to view, add, remove, complete, or edit tasks. It works with any tasks in Microsoft Planner."
ms.localizationpriority: medium
author: sebastienlevert
---

# Tasks component in Microsoft Graph Toolkit

The Tasks component enables the user to view, add, remove, complete, or edit tasks from Microsoft Planner.  

In addition, a user is able to assign a single or multiple Microsoft Graph users to a task. For more details about Microsoft Graph assignments, see [plannerAssignments](/graph/api/resources/plannerassignments).

## Example

The following example displays the signed-in user's Microsoft Planner tasks using the `mgt-tasks` component. You can use the code editor to see how [properties](#properties) change the behavior of the component.

<iframe src="https://mgt.dev/iframe.html?id=components-mgt-tasks--tasks&source=docs" height="500"></iframe>

[Open this example in mgt.dev](https://mgt.dev/?path=/story/components-mgt-tasks--tasks&source=docs)

## Properties

| Attribute | Property | Description |
| -- | -- | -- |
| read-only | readOnly | A Boolean to set the task interface to be read only (no adding or removing tasks). Default is `false`. |
| hide-header | hideHeader | A Boolean to show or hide the header of the component. Default is `false`. |
| hide-options | hideOptions | A Boolean to show or hide the options in tasks. Default is `false`.
| initial-id="planner_id/folder_id" | initialId | A string ID to set the initially displayed planner or folder to the provided ID. |
| initial-bucket-id="bucket_id" | initialBucketId | A string ID to set the initially displayed bucket (Planner Data-Source Only) to the provided ID. |
| target-id="planner_id/folder_id"| targetId | A string ID to lock the tasks interface to the provided planner or folder ID. |
| target-bucket-id="bucket_id" |targetBucketId  | A string ID to lock the tasks interface to the provided bucket ID (Planner Data-Source Only). |
| group-id | groupId  | A string ID to lock the tasks interface to the group ID. |
| N/A | isNewTaskVisible  | Determines whether new task view is visible at render. |
| N/A | taskFilter  | An optional function to filter which tasks are shown to the user. |

The following example shows only tasks from Planner with ID *12345* and does not allow the user to create new tasks.

```html
<mgt-tasks read-only initial-id="12345"></mgt-tasks>
```

The following example shows how to filter tasks that only have *category3* set.

```js
let taskView = document.querySelector('mgt-tasks');
taskView.taskFilter = task => task.appliedCategories.category3 === true;
```

## Custom CSS variables

````css
mgt-tasks {
--tasks-header-padding
--tasks-header-margin 

--tasks-title-padding
--tasks-plan-title-font-size
--tasks-plan-title-padding

--tasks-new-button-width
--tasks-new-button-height
--tasks-new-button-color
--tasks-new-button-background
--tasks-new-button-border
--tasks-new-button-hover-background
--tasks-new-button-active-background

--tasks-new-task-name-margin

--task-margin
--task-box-shadow
--task-background
--task-border

--task-header-color
--task-header-margin

--task-detail-icon-margin

--task-new-margin
--task-new-border
--task-new-line-margin
--tasks-new-line-border
--task-new-input-margin
--task-new-input-padding
--task-new-input-font-size
--task-new-input-active-border
--task-new-select-border

--task-new-add-button-background
--task-new-add-button-disabled-background
--task-new-cancel-button-color

--task-complete-background
--task-complete-border
--task-complete-header-color
--task-complete-detail-color
--task-complete-detail-icon-color

--task-icon-background-completed
--task-icon-background

--task-icon-border-completed
--task-icon-border

--task-icon-color
--task-icon-color-completed

--task-icon-border-radius

--task-icon-alignment: flex-start (default) | center | flex-end
}
````

## Events

Event | When is it emitted | Custom data | Cancelable | Bubbles | Works with custom template
------|-------------------|--------------|:-----------:|:---------:|:---------------------------:|
`taskAdded` | Fires when a new task has been created | Newly created task which can be a [plannerTask](/graph/api/resources/plannertask) our [outlookTask](/graph/api/resources/outlooktask) | No | No | Yes
`taskChanged` | Fires when task metadata has been changed, such as marking completed | Updated task which can be a [plannerTask](/graph/api/resources/plannertask) our [outlookTask](/graph/api/resources/outlooktask) | No | No | No
`taskClick` | Fires when the user clicks or taps on a task | `task` property with the selected [plannerTask](/graph/api/resources/plannertask) our [outlookTask](/graph/api/resources/outlooktask) | No | No | No
`taskRemoved` | Fires when an existing task has been deleted | `task` property with the selected [plannerTask](/graph/api/resources/plannertask) our [outlookTask](/graph/api/resources/outlooktask) | No | No | No

For more information about handling events, see [events](../customize-components/events.md).

## Templates

The `tasks` component supports several [templates](../customize-components/templates.md) that allow you to replace certain parts of the component. To specify a template, include a `<template>` element inside a component and set the `data-type` value to one of the following:

| Data type     | Data context              | Description                                                       |
| ---------     | ------------------------- | ----------------------------------------------------------------- |
| task     | task: a planner task object | replaces the whole default task. |
| task-details | task: a planner task object | template replaces the details section of the task. |

The following example defines a template for the tasks component.

```html
    <mgt-tasks>
      <template data-type="task-details">
        <div>
          Owner: {{task.owner}}
        </div>
        <div>
          Importance Level: {{task.importance}}
        </div>
      </template>
    </mgt-tasks>
```

## Microsoft Graph permissions

This control uses the following Microsoft Graph APIs and permissions.

| Configuration | Permission | API |
| ------------- | ---------- | --- |
| `groupId` set and `dataSource` set to `TasksSource.planner` | Group.Read.All | [/groups/${group-id}/planner/plans](/graph/api/plannergroup-list-plans?tabs=http), [/planner/plans/${planId}/buckets](/graph/api/planner-list-buckets), [/planner/buckets/${bucketId}/tasks](/graph/api/planner-list-buckets) |
| `targetId` set and `dataSource` set to `TasksSource.todo` | Tasks.Read | [/me/outlook/taskGroups](/graph/api/outlookuser-list-taskgroups?view=graph-rest-beta&preserve-view=true&tabs=http&viewFallbackFrom=graph-rest-1.0), [/me/outlook/taskGroups/${groupId}/taskFolders](/graph/api/outlooktaskfolder-list-tasks?view=graph-rest-beta&preserve-view=true&tabs=http), [/me/outlook/taskFolders/${folderId}/tasks](/graph/api/outlooktaskfolder-list-tasks?view=graph-rest-beta&preserve-view=true&tabs=http) |
| `targetId` set and `dataSource` set to something else than `TasksSource.todo` | Group.Read.All | [/planner/plans/${planId}](/graph/api/plannerplan-get?tabs=http), [/planner/plans/${planId}/buckets](/graph/api/plannerplan-list-buckets?tabs=http), [/planner/buckets/${bucketId}/tasks](/graph/api/plannerplan-list-tasks?tabs=http) |
| `dataSource` set to `TasksSource.planner` | Group.Read.All | [/me/planner/plans](/graph/api/planneruser-list-plans?tabs=http), [/planner/plans/${planId}/buckets](/graph/api/plannerplan-list-buckets?tabs=http), [/planner/buckets/${bucketId}/tasks](/graph/api/plannerplan-list-tasks?tabs=http) |
| `dataSource` set to `TasksSource.todo` | Tasks.Read | [/me/outlook/taskGroups](/graph/api/outlookuser-list-taskgroups?view=graph-rest-beta&preserve-view=true&tabs=http&viewFallbackFrom=graph-rest-1.0), [/me/outlook/taskGroups/${groupId}/taskFolders](/graph/api/outlooktaskfolder-list-tasks?view=graph-rest-beta&preserve-view=true&tabs=http), [/me/outlook/taskFolders/${folderId}/tasks](/graph/api/outlooktaskfolder-list-tasks?view=graph-rest-beta&preserve-view=true&tabs=http) |
| `addTask` set to `true` and `dataSource` set to `TasksSource.planner` | Group.ReadWrite.All | [/planner/tasks](/graph/api/planner-post-tasks?tabs=http) |
| `addTask` set to `true` and `dataSource` set to `TasksSource.todo` | Tasks.ReadWrite | [/me/outlook/taskFolders/${parentFolderId}/tasks](/graph/api/outlookuser-post-tasks?view=graph-rest-beta&preserve-view=true&tabs=csharp) |

For the Microsoft Planner data source, fetching and reading tasks requires the Groups.Read.All permission. Adding, updating, or removing tasks requires the Groups.ReadWrite.All permission.

## Authentication

The tasks component uses the global authentication provider described in the [authentication documentation](../providers/providers.md).

## Cache

The `mgt-tasks` component doesn't cache any data.
