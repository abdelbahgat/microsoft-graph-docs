---
title: "Working with rules in privileged identity management (PIM)"
description: "Learn how rules in PIM are structured in Microsoft Graph and how they map with the descriptions on the Microsoft Entra admin center."
author: "FaithOmbongi"
ms.author: ombongifaith
ms.reviewer: rianakarim
ms.localizationpriority: medium
ms.topic: conceptual
ms.prod: "governance"
ms.date: 06/08/2023
---

# Working with rules in PIM using Microsoft Graph

Privileged Identity Management (PIM) exposes role settings or rules for the resources that can be managed. In Microsoft Graph, these resources are Microsoft Entra roles and groups and they are managed through [PIM for Microsoft Entra roles](/graph/api/resources/privilegedidentitymanagementv3-overview) and [PIM for groups](/graph/api/resources/privilegedidentitymanagement-for-groups-api-overview) respectively.

Role settings fall in one of three categories: activation settings, assignment settings, and notification settings. Such settings include whether multifactor authentication (MFA) is required to activate an eligible role, group membership or group ownership, or whether you can create permanent role assignments or permanent group membership or ownership.

When using the [PIM APIs](/graph/api/resources/privilegedidentitymanagementv3-overview) in Microsoft Graph, these role settings are managed through policies and rules.

## Policies

In Microsoft Graph, the role settings are called *rules*. These rules are grouped in, assigned to, and managed for Microsoft Entra roles and groups through containers called *policies*.

The policies are defined through the [unifiedRoleManagementPolicy resource type](/graph/api/resources/unifiedrolemanagementpolicy).

## Policy rules

Each policy contains 17 pre-defined rules that can be updated. These rules are managed through the **rules** relationship of the [unifiedRoleManagementPolicy resource type](/graph/api/resources/unifiedrolemanagementpolicy).

To group the rules into activation, assignment, and notification rules, Microsoft Graph defines the [unifiedRoleManagementPolicyRule resource type](/graph/api/resources/unifiedrolemanagementpolicyrule) abstract type. This abstract type is inherited by five resources. Each of these five derived types then defines rule configurations that can be one or more of 17 rules. The 17 rules are identified by unique and immutable rule IDs.

This article provides a mapping of settings in PIM on the Microsoft Entra admin center to the corresponding rules in Microsoft Graph.

## Mapping of rule IDs to PIM role settings on the Microsoft Entra admin center

<!--
Questions: Should I prefix "Role" to all titles below? I feel like it limits to "DirectoryRole" scope. What about the "Directory" scope? How do we handle this?

Where does this statement come in:
Azure AD supports policies that are scopes either to the directory or to a directory role. Both these policy scopes include the 17 pre-defined but updatable rules.
-->

### Activation rules

The following image shows the activation role settings on the Microsoft Entra admin center, mapped to rules and resource types in the PIM APIs in Microsoft Graph.

:::image type="content" source="images/identity-governance-pim-ux-role-rules-screenshots/pim-ux-role-rule.activation.png" alt-text="PIM role activation settings on the Microsoft Entra admin center.":::

| Number | Microsoft Entra admin center UX Description                                                                                                                                        | Microsoft Graph rule ID / Derived resource type                                                   | Enforced for caller |
|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|----------------------|
| 1      | Activation maximum duration (hours)                                                                                                                                | `Expiration_EndUser_Assignment` / unifiedRoleManagementPolicyExpirationRule                       | End user            |
| 2      | On activation, require: None, Azure MFA <br/><br/>Require ticket information on activation<br/><br/>Require justification on activation | `Enablement_EndUser_Assignment` / unifiedRoleManagementPolicyEnablementRule                        | End user               |
| 3      | On activation, require: Microsoft Entra Conditional Access authentication context (Preview)                                                                               | `AuthenticationContext_EndUser_Assignment` / unifiedRoleManagementPolicyAuthenticationContextRule | End user            |
| 4      | Require approval to activate                                                                                                                                       | `Approval_EndUser_Assignment` / unifiedRoleManagementPolicyApprovalRule                           | End user            |

## Assignment rules

The following image shows the assignment role settings on the Microsoft Entra admin center, mapped to rules and resource types in the PIM API in Microsoft Graph.

:::image type="content" source="../concepts/images/identity-governance-pim-ux-role-rules-screenshots/pim-ux-role-rule.assignment.png" alt-text="PIM role assignment settings on the Microsoft Entra admin center.":::

| Number | Microsoft Entra admin center UX Description                                                                                                                                          | Microsoft Graph Rule ID / Derived resource type                             | Enforced for caller |
|---------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|----------------------|
| 5      | Allow permanent eligible assignment<br/><br/>Expire eligible assignments after                                                                                       | `Expiration_Admin_Eligibility` / unifiedRoleManagementPolicyExpirationRule  | Admin               |
| 6      | Allow permanent active assignment<br/><br/>Expire active assignments after                                                                                           | `Expiration_Admin_Assignment` / unifiedRoleManagementPolicyExpirationRule   | Admin               |
| 7      | Require Azure Multi-Factor Authentication on active assignment<br/><br/>Require justification on active assignment<br/><br/>Require ticket information on activation | `Enablement_Admin_Assignment` / unifiedRoleManagementPolicyExpirationRule   | Admin               |
| 8      | Require Azure Multi-Factor Authentication on active assignment<br/><br/>Require justification on active assignment<br/><br/>Require ticket information on activation | `Enablement_EndUser_Assignment` / unifiedRoleManagementPolicyExpirationRule |End user            |

## Notification rules

The following image shows the notification role settings on the Microsoft Entra admin center, mapped to rules and resource types in the PIM API in Microsoft Graph.

:::image type="content" source="../concepts/images/identity-governance-pim-ux-role-rules-screenshots/pim-ux-role-rule.notification.png" alt-text="PIM role notification settings on the Microsoft Entra admin center.":::

| Number | Microsoft Entra admin center UX Description | Microsoft Graph Rule ID / Derived resource type | Enforced for caller |
|---|---|---|---|
| 9 | Send notifications when members are assigned as eligible to this role: Role assignment alert | `Notification_Admin_Admin_Eligibility` / unifiedRoleManagementPolicyNotificationRule | Admin |
| 10 | Send notifications when members are assigned as eligible to this role: Notification to the assigned user (assignee) | `Notification_Requestor_Admin_Eligibility` / unifiedRoleManagementPolicyNotificationRule | Assignee / Requestor |
| 11 | Send notifications when members are assigned as eligible to this role: request to approve a role assignment renewal/extension | `Notification_Approver_Admin_Assignment` / unifiedRoleManagementPolicyNotificationRule | Approver |
| 12 | Send notifications when members are assigned as active to this role: Role assignment alert | `Notification_Admin_Admin_Assignment` / unifiedRoleManagementPolicyNotificationRule | Admin |
| 13 | Send notifications when members are assigned as active to this role: Notification to the assigned user (assignee) | `Notification_Requestor_Admin_Assignment` / unifiedRoleManagementPolicyNotificationRule | Assignee / Requestor |
| 14 | Send notifications when members are assigned as active to this role: Request to approve a role assignment renewal/extension | `Notification_Approver_Admin_Eligibility` / unifiedRoleManagementPolicyNotificationRule | Approver |
| 15 | Send notifications when eligible members activate this role: Role activation alert | `Notification_Admin_EndUser_Assignment` / unifiedRoleManagementPolicyNotificationRule | Admin |
| 16 | Send notifications when eligible members activate this role: Notification to activated user (requestor) | `Notification_Requestor_EndUser_Assignment` / unifiedRoleManagementPolicyNotificationRule | Requestor |
| 17 | Send notifications when eligible members activate this role: Request to approve an activation | `Notification_Approver_EndUser_Assignment` / unifiedRoleManagementPolicyNotificationRule | Approver |

## See also

+ [Overview of role management through the privileged identity management (PIM) API](/graph/api/resources/privilegedidentitymanagementv3-overview)
+ [Use PIM APIs in Microsoft Graph to update rules](how-to-pim-update-rules.md)
+ [Configure role settings in Privileged Identity Management using the Microsoft Entra admin center](/azure/active-directory/privileged-identity-management/pim-how-to-change-default-settings)
