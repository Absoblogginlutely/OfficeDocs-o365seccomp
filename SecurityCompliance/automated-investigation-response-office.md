---
title: "Automated Investigation and Response (AIR) with Office 365 Threat Intelligence"
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/04/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: "Learn about Automated Investigation and Response capabilities in Office 365 Advanced Threat Protection."
---

# Automated Investigation and Response (AIR) with Office 365 Threat Intelligence

Automated Investigation and Response (AIR) (coming soon to [Office 365 Threat Intelligence](office-365-ti.md)) enables you to run automated investigation and remediation to well-known threats that exist today. Read this article to get an overview of AIR and how it can help your organization mitigate threats more effectively and efficiently.

## Security playbooks

Security playbooks are back-end policies that admins can select as part of security policies. At the heart of automation in Microsoft Threat Protection, the security playbooks provided in AIR are based on common real-world security scenarios. 

A Security playbook is kicks off when an alert is triggered within your organization. Once the alert triggers, the associated playbook is run automatically. The playbook runs an investigation, looking at all the associated metadata (including email messages, users, subjects, senders, etc.) and, based on its findings, recommends a set of actions that your organization's security team can take to control and mitigate the threat. 

Based on extensive experience, the security playbooks are designed to tackle the most frequent threats that organizations face.

### Security playbooks are rolling out in phases

- **Phase 1**: Playbooks include recommendations that security administrators review and approve. 

- **Phase 2**: Security administrators will have the option to allow security playbooks to take action automatically, without administrative interaction.

### Five playbooks will be offered

At initial release, three playbooks will be available. Two more will follow soon after.

|Initial release  |Following soon |
|---------|---------|
|User-submitted message<br>URL verdict change<br>Manual investigation |Zapped malware<br>Zapped phish<br/> |

Each playbook includes: 
- a root investigation, 
- steps to hunt down other potential threats, and 
- threat remediation.

Each high-level step includes many sub-steps that are executed to provide a deep, detailed, and exhaustive response to threats.

### Example: User-submitted message playbook

Suppose that a user submits an email message by using the [Report Message add-in for Outlook](enable-the-report-message-add-in.md). This triggers the **User-submitted message** playbook.

During the root investigation phase, various aspects of the email are assessed. These include:
- A determination about what type of threat it might be,
- Who sent it,
- Whether other instances of the email were removed by the [ZAP feature](zero-hour-auto-purge.md),
- An assessment from our analysts,
- Whether the email is associated with any known campaigns,
- and more.

After the root investigation is complete, the playbook provides a list of recommended actions to take.
  
Next, several hunting steps are executed:

- Similar email messages in other email clusters are searched.
- The signal is shared with other platforms, such as [WDATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection).
- A determination on whether any users have clicked-through on the suspicious email message.
- A check is done to see if [Office 365 ATP Safe Links](atp-safe-links.md) may have missed any instance of the email which was submitted.
- A check is done to see if the user has been compromised.  

During the hunting phase, risks and threats are assigned to various hunting steps.  

Remediation is the final phase of the playbook. During this phase, remediation steps are carried out, based on the results from the investigation and hunting phases.  

## Getting started

To access your investigations, as an Office 365 global administrator or security administrator, do one of the following:

- Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in. Then, in the left navigation, go to **Threat management** > **Investigations**.

    or

- Visit the Threat management dashboard (In the Security & Compliance Center, go to **Threat management** > **Dashboard**).

![AIR widgets](media/air-widgets.png)

Your AIR widgets will appear across the top of the [Security Dashboard](security-dashboard.md).

### The main investigation page

The main investigation page shows an overview view of your organization's investigations and their current states.

![Main investigation page for AIR](media/air-maininvestigationpage.png) 
  
On this page, you have several options:
- Navigate directly to an investigation (click an Investigation ID).
- Apply filters to the Investigation State, Status, Time, or a combination of all, to get a filtered list of your choosing.
- Export the data to a CSV file.

### The investigation graph page

When you open a specific investigation, you see the investigation graph page. This page shows all the different entities: email messages, users (and their activities), and devices that were automatically investigated as part of the alert that was triggered.

![AIR investigation graph page](media/air-investigationgraphpage.png)

On this page, you have several options:
- Get a visual overview of the current investigation.
- View a summary of the investigation timings.
- Click a node in the visualization to view details for that node.
- Click a tab across the top to view details for that tab.

### The investigation alerts page

When you click the Alerts node or Alerts tab for an investigation, you go to a page that shows ALL alerts relevant to the investigation. Details include the alert that triggered the investigation as well as other alerts, such as risky sign-in, mass download, etc., that are correlated to an investigation. From this page, a security analyst can also view additional details on the alerts themselves.

![AIR alerts page](media/air-investigationalertspage.png)

On this page, you have several options:
- Get a visual overview of the current triggering alert and any associated alerts.
- Click an alert in the list to open a fly-out page that shows full alert details.

### The investigation email messages page

When you click the Email node or Email tab for an investigation, you go to a page that shows all the email clusters identified as part of the investigation. 

Given the sheer volume of email that users in an organization send and receive, the process of 
- clustering email messages based on similar attributes from a message header, body, URL and attachment, 
- separating malicious email from the good email, and 
- taking action on malicious email messages 

can take many hours. AIR now automates this process, saving your organization's security team time and effort. 

As an example, consider the following image. The first cluster of three email messages were deemed to be phish. Another cluster of similar messages with the same IP and subject was found and is considered to be malicious, as some of them were identified as phish during initial detection. 

![AIR email investigation page](media/air-investigationemailpage.png)

On this page, you have several options:
- Get a visual overview of the current clustering results and threats found.
- Click a cluster entity or a threat list to open a fly-out page that shows the full alert details.

![AIR investigation email with flyout details](media/air-investigationemailpageflyoutdetails.png)

### The investigation users page

When you click the Users node or Users tab, you go to a view that shows all the users identified as part of the investigation. 

For example, in the following image, AIR has identified indicators of compromise and anomalies based on a new inbox rule that was created. Additional details (evidence) of the investigation are available through detailed views within this tab.

![AIR investigation users page](media/air-investigationuserspage.png)

On this page, you have several options:
- Get a visual overview of identified user results and risks found.
- Click a user to open a fly-out page that shows the full alert details.

### The investigation machines page

When you click the Machines node or Machines tab, you go to a view that shows all the machines identified as part of the investigation. 

![AIR investigation machine page](media/air-investigationmachinepage.png)

As part of the investigation, AIR correlates email threats to devices. For example, an investigation passes a file hash across to [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) to investigate. This allows for automated investigation of relevant machines for your users and helps to ensure that threats are addressed both in the cloud and across your devices. 

On this page, you have several options:
- Get a visual overview of the current machines and threats found.
- Click a machine to open a view that into the related [Windows Defender ATP investigations](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection).

### Investigation entities page

When you click the Entities tab, you go to a view that shows all the machines identified as part of the investigation. 

On this page, you can see the investigated entities. You can see details of the types of entities, such as email messages, clusters, IP addresses, users, and more. You can also see how many entities were analyzed, and the threats that were associated with each. 

![AIR investigation entities page](media/air-investigationentitiespage.png)

On this page, you have several options:
- Get a visual overview of the investigation entities and threats found.
- Click an entity to open a fly-out page that shows the related entity detail.

![AIR investigation entities details](media/air-investigationsentitiespagedetails.png)

### Investigation log page

When you click the Log tab, you go to a view that shows all the play book steps that have occurred during the investigation. The log captures a complete inventory of all actions completed by Office 365 Threat Intelligence capabilities as part of AIR. It provides a clear view of all the steps taken, including the Action itself, a description and the duration of the actual from start to finish. 

![AIR investigation log page](media/air-investigationlogpage.png)

On this page, you have several options:
- Get see a visual overview of the play book steps taken.
- Export the results to a CSV file.
- Filter the view.

### Investigation actions page

When you click the Actions node or Action tab, you go to a view that shows all the play book actions that are recommended for remediation after the investigation has completed. 

The actions capture a complete list of all the action steps Microsoft recommend you take at the end of a investigation. You can take remediation actions here by selecting one or more actions. Clicking Approve will allow remediations to begin running. (Appropriate permissions might be required. for example, Security Reader can view actions but not approve them.)  

![AIR investigations action page](media/air-investigationactionspage.png)

On this page, you have several options:
- Get a visual overview of the playbook-recommended actions.
- Select a single action or multiple actions.
- Approve recommended actions. (These are started immediately with comments.)
- Export the results to a CSV file.
- Filter the view.

## How do I get AIR?

Currently, AIR is in preview. When released, AIR will be included in the following subscriptions:

- Microsoft 365 Enterprise E5
- Office 365 Enterprise E5
- Microsoft Threat Protection
- Office 365 Advanced Threat Protection Plan 2

To learn more about feature availability, visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).

## Related topics

[Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)

[Reports and insights in the Office 365 Security &amp; Compliance Center](reports-and-insights-in-security-and-compliance.md)
  
[Use Explorer in the Security &amp; Compliance Center](use-explorer-in-security-and-compliance.md)

