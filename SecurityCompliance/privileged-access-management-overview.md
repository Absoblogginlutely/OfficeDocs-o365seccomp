---
title: "Privileged access management in Office 365"
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
description: "Use this topic to learn more about privileged access management in Office 365"
---

# Privileged access management in Office 365

> [!IMPORTANT]
> This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.

Privileged access management allows granular access control over privileged admin tasks in Office 365.  It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings. After enabling privileged access management, users will need to request just-in-time access to complete elevated and privileged tasks through an approval workflow that is highly scoped and time-bound. This gives users just-enough-access to perform the task at hand, without risking exposure of sensitive data or critical configuration settings. Enabling privileged access management in Office 365 will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. 

## Layers of protection

Privileged access management complements other data and access feature protections within the Office 365 security architecture. By enabling privileged access management as part of an integrated approach to security and protecting your organization, a layered security model can be used to maximize protection of sensitive information and Office 365 configuration settings. As shown in the diagram below, enabling privileged access management helps builds on the protection provided with native encryption of Office 365 data and the role based access control security model of Office 365 services. When used in conjunction with [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure), these two features provide access control with just-in-time access at different scopes.

![Layered protection in Office 365](media/pam-layered-protection.png)

Privileged access management in Office 365 can be defined and scoped at the **task** level, while Azure AD Privileged Identity Management applies protection at the **role** level with the ability to execute multiple tasks.  Azure AD Privileged Identity Management primarily allows managing accesses for AD roles and role groups, while privileged access management in Office 365 is applied only at the task level.

- **Enabling privileged access management in Office 365 while already using Azure AD Privileged Identity Management:** Adding privileged access management in Office 365 provides another granular layer of protection and audit capabilities for privileged access to Office 365 data.

- **Enabling Azure AD Privileged Identity Management while already using privileged access management in Office 365:**  Adding Azure AD Privileged Identity Management to privileged access management in Office 365 can extend privileged access to data outside of Office 365 that’s primarily defined by a user’s role or identity.  

## Privileged access management architecture and process flow

Each of the following process flows outline the architecture of priveleged access and how it interacts with the Office 365 substrate, Office 365 auditing, and the Exchange Management runspace.

### Step 1: Configuring a privileged access policy

When configuring a privileged access policy using either the Office 365 Admin Center or Exchange Management PowerShell, you create and define the policy and the privileged access feature processes the policy attributes in the Office 365 substrate and logs the activity in the Office 365 Security and Compliance Center. The policy is now enabled and ready to handle incoming requests for approvals.

![Step 1 - Policy creation](media/pam-step1-policy-creation.jpg)

### Step 2: Access request

Using the Office 365 Admin Center or Exchange Management PowerShell, users can request access to elevated or privileged tasks. The privileged access feature sends the request to the Office 365 substrate for processing against the configured privilege access policy and records the sctivity in the Office 365 Security and Compliance Center logs.

![Step 2 - Access request](media/pam-step2-access-request.jpg)

### Step 3: Access approval

An approval request is generated and the approval group is notified by email of the pending request. If approval is granted, the privileged access request is processed as an approval and the task is ready to be completed. If the request is denied, task is blocked and no access is granted to the reqeustor. The requestor will be notified of the request approval or denial via email message.

![Step 3 - Access approval](media/pam-step3-access-approval.jpg)

### Step 4: Access processing

For approved requests, the task is processed by the Exchange Management runspace. The approval is checked against the privileged access policy and processed by the Office 365 substrate. All activity for the task is logged in the Office 365 Security and Compliance Center.

![Step 4 - Access processing](media/pam-step4-access-processing.jpg)

## Frequently asked questions

### What SKUs do I need to use privileged access in Office 365?
Privileged access management is currently only available for customers with Office 365 E5 and Advanced Compliance SKUs.

### When will privileged access be available for Office 365 workloads beyond Exchange?
We plan to offer this feature in other Office 365 workloads soon. When we’re ready to share a timeline, it will be available through the Microsoft 365 Roadmap.

### My organization needs more than 30 privileged access polices, will this limit be increased?

We're planning to increase the current limit of 30 privileged access policies per Office 365 organization soon.

### Do I need to be a Global Admin to manage privileged access in Office 365?
No, you need to have the Exchange Role Management role assigned to accounts that will manage privileged access in Office 365. However, the Global Administrator role includes this role by default and can be used to manage privileged access if you don’t want to configure the Role Management role as a stand-alone account permission. Users who are included in an approvers’ group don't need to be a Global Admin or have the Role Management role assigned to review and approve requests. 

### How is privileged access management in Office 365 related to Customer Lockbox?
[Customer Lockbox](https://support.office.com/article/Office-365-Customer-Lockbox-Requests-36f9cdd1-e64c-421b-a7e4-4a54d16440a2) allows a level of access control for organizations for access to to data by their service provider, i.e. Microsoft. Privileged access management in Office 365 allows granular access control within an organization for all Office 365 privileged tasks.
