---
title: "Configuring privileged access management in Office 365"
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Strat_O365_IP
ms.custom: Ent_Solutions
ms.assetid: 
description: "Use this topic to learn more about configuring privileged access management in Office 365"
---

# Configuring privileged access management in Office 365

> [!IMPORTANT]
> This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.

This topic will guide you through enabling and configuring privileged access management in your Office 365 organization and serve as a reference guide for requesting, approving, and managing the feature. 

## Before you begin

### Limited functionality
During the public beta, privileged access management features are only available through [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps) in Office 365. Privileged access management covers the task definitions at the level of Exchange management cmdlets. In future Office 365 releases, privileged access features will be available through the admin portal and will cover other Office 365 workloads services.

### Connecting to Exchange Online PowerShell
The configuration steps in this topic will walk you through enabling and using privileged access in Office 365 using Exchange Online PowerShell. 

Follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to connect to Exchange Online PowerShell with your Office 365 credentials to enable and configure privileged access for your organization.

> [!NOTE]
> You do not need to enable multi-factor authentication for your Office 365 organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell. Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.

## Enable and configure privileged access management

### Step 1 - Create an approver's group
From Office 365 Admin Portal, select **Groups** > **Add a group**, then create a mail enabled security group for the default privileged access approvers. When complete, select **Add** to create and save the approver group.

![Privileged access approvers screen in Office 365 Admin portal](media/privileged-access-approvers-ui.png)

> [!NOTE] 
> At this time, only users with administrative access are allowed to approve requests from Office 365 priviledged access. In future any user who is part of the Approvers’ group will be able to approve access requests.

### Step 2 - Enable privileged access in Office 365
Privileged access needs to be explicitly turned on with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control. 

Run the following command in Exchange Online PowerShell to enable privileged access and to assign the approver's group:
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
Example:
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.

### Step 3 - Create an approval policy
An approval policy allows you to define the specific approval requirements scoped at individual tasks. The approval type options are **Auto** or **Manual**. 

Run the following command in Exchange Online PowerShell to define an approval policy:
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
Example:
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

## Using privileged access in your Office 365 organization

### Requesting elevation authorization to execute tasks
Once enabled, privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute the task.

Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
Example:
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### View status of elevation requests
After an approval request is created, elevation request status can be reviewed using the associated with request ID.

Run the following command in Exchange Online PowerShell to view a approval request status for a specific request ID:
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
Example:
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### Approving an elevation authorization request
When an approval request is created, members of the relevant approver group will receive an email notification and can approve the request associated with the request ID. 

Run the following command in Exchange Online PowerShell to approve an elevation authorization request:
```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
Example:
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```
### Denying an elevation authorization request
When an approval request is created, members of the relevant approver group can deny the request associated with the request ID. 

Run the following command in Exchange Online PowerShell to deny an elevation authorization request:
```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
Example:
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

### Running the task
After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on users’ behalf. The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times. All such executions are logged and made available for security and compliance auditing. 

### Disable privileged access in Office 365
If needed, you can disable privileged access management in Office 365. Disabling privileged access does not delete any associated approval policies or approver groups.

Run the following command in Exchange Online Powershell to disable privileged access:

```
Disable-ElevatedAccessControl
```
## Managed access to Microsoft Graph in Microsoft Azure

> [!IMPORTANT]
> This section covers details about a feature currently available only in preview.

Managed access to Microsoft Graph in Microsoft Azure is a service that helps organizations exert a granular level of control over their Office 365 data. This system allows application developers to forge insights with that data. 

This system uses Office 365 privileged access to assert control over their data through its approval workflow, allowing scoped access to Office 365 data with admin oversight. Requests for data come in when applications are installed and require access to Office 365 data.

### View request details
View details of the access requests for Office 365 data.

Run the following command in Exchange Online Powershell to view data requests:
```
Get-ElevatedAccessRequest | where {$_.RequestedAccess -like '*Data Access Request*'} | select RequestorUPN, Service, RequestedAccess | fl
```
Example output:
```
RequestorUPN    : admin@contoso.com
Service         : Office365
RequestedAccess : Data Access Request
```

### Approve data access requests
All data access requests can be approved through the standard privileged access approval cmdlets.

Run the following command in Exchange Online Powershell to approve all data requests for specific requestor:

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
Example:
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```