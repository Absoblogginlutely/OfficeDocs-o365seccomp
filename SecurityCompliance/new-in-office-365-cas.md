---
title: "What is new in Office 365 Cloud App Security"
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.date: 01/25/2019
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d674763c-a4c9-4604-8623-68c1836d27f3
description: "See what's new in Office 365 Cloud App Security"
---

# What is new in Office 365 Cloud App Security

**Summary** Read this article to get a quick overview of updates and new features in Office 365 Cloud App Security (formerly known as Office 365 Advanced Security Management), which is powered by [Microsoft Cloud App Security](https://aka.ms/whatiscas).
  
> [!TIP]
> This article is updated frequently, as features are added or improved. Office 365 Cloud App Security updates are released approximately two weeks after Microsoft Cloud App Security updates, and not all Microsoft Cloud App Security updates apply to Office 365 Cloud App Security. In addition, new features might take a week or more after their release date to show up in your Office 365 Cloud App Security environment.

## Office 365 Cloud App Security releaases 139, 140

*Released January 22, 2019*

**Following [Microsoft Cloud App Security releases 139, 140](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-139-140)**:

- **Advanced tuning for anomaly detection policies** You can now affect the anomaly detection engine to suppress or surface alerts according to your preferences. In the Impossible Travel policy, you can set the sensitivity slider to determine the level of anomalous behavior needed before an alert is triggered. You can also configure whether the alerts for Activity from infrequent country, anonymous IP addresses, suspicious IP addresses, and impossible travel should analyze both failed and successful logins or just successful logins. 

## Office 365 Cloud App Security release 138

*Released December 23, 2018*

**Following [Microsoft Cloud App Security release 138](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-138)**:

- **Automatic log upload using Docker on Windows** Cloud App Security now supports automatic log upload for Windows 10 ([Fall Creators Update](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) and newer) and Windows Server ([version 1709](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1709) and newer) by using Docker on Windows. See [this article](https://docs.microsoft.com/cloud-app-security/discovery-docker-windows) to learn more and configure Docker.  

- **Microsoft Flow integration** Cloud App Security now integrates with [Microsoft Flow](https://docs.microsoft.com/flow/getting-started) to provide custom alert automation and orchestration playbooks. See [this article](https://docs.microsoft.com/cloud-app-security/flow-integration) to learn more and configure Microsoft Flow integration. 


## Office 365 Cloud App Security release 137

*Released December 8, 2018*

**Following [Microsoft Cloud App Security release 137](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-137)**:

- **Added support for Dynamics** Cloud App Security now includes support for the Microsoft Dynamics activities that are supported in the Office 365 audit log. 

- **Heads up – new terminology!** The name of the App permissions capabilities was changed for clarity – it is now called OAuth apps. 


## Office 365 Cloud App Security release 136

*Released November 25, 2018*

**Following [Microsoft Cloud App Security release 136](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-136)**:

- **Cloud Discovery updates** The custom log parser was enhanced to support additional and more complex web traffic logs formats. As part of these enhancements users can now input custom headers for headerless CSV log files, use special delimiters for key-value files, process Syslog file format, and more.

- **New anomaly detection policy: Suspicious inbox manipulation rules** This policy profiles your environment and triggers alerts when suspicious rules that delete or move messages or folders are set on a user's inbox. This may indicate that the user’s account is compromised, that messages are being intentionally hidden, and that the mailbox is being used to distribute spam or malware in your organization.

- **Support for groups in app permission policies** Cloud App Security now gives you the ability to define app permission policies more granularly, based on the group memberships of the users who authorized the apps. For example, an admin can decide to set a policy that revokes uncommon apps if they ask for high permissions, only if the user who authorized the permissions is a member of the administrators group.


## Office 365 Cloud App Security releases 133, 134, and 135

*Released in October-November, 2018*

**Following [Microsoft Cloud App Security release 133, 134, and 135](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-133-134-135)**:

- **New anomaly detection policies** are rolling out gradually:
    
    - The new **Data exfiltration to unsanctioned apps** policy is automatically enabled to alert you when a user or IP address uses an app that isn't sanctioned to perform an activity that resembles an attempt to exfiltrate information from your organization.
    
    - The new **Multiple delete VM activities** policy profiles your environment and triggers alerts when users delete multiple VMs in a single session, relative to the baseline in your organization.

- **Cloud Discovery support for i-Filter** The Cloud App Security Cloud Discovery feature now has enhanced support for the i-Filter syslog parser.


## Office 365 Cloud App Security release 131

*Released September 16, 2018*

**Following [Microsoft Cloud App Security release 131](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-131)**:

- **Automatically revoke permissions on risky OAuth apps** You can now control which OAuth apps your users have access to, by revoking app permission for OAuth apps on Office. When creating an App permission policy, you can now set the policy to revoke an app’s permission.

- **Cloud Discovery additional built-in parser supported** Cloud Discovery now supports the Forcepoint Web Security Cloud log format.

  
## Office 365 Cloud App Security release 130

*Released September 5, 2018*

**Following [Microsoft Cloud App Security release 130](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-130)**:

- **New menu bar** To provide a more consistent admin experience across Microsoft 365 products, and to enable you to pivot more easily between Microsoft security solutions, the Cloud App Security portal menu bar has moved to the left side of the screen. This consistent navigation experience helps you orient yourself when moving from one Microsoft security portal to another.<br/>![Menu bar in Office Cloud App Security](media/OCAS-MenuBar.png)<br/>

- **Impact OAuth app score** You can now send the Cloud App Security team feedback to let us know if there’s an OAuth app discovered in your organization that seems malicious. This new feature enables you to be part of our security community and enhance OAuth app risk score and analysis. For more information see [Manage OAuth apps](manage-app-permissions-in-ocas.md).

- **New Cloud Discovery parsers** The Cloud Discovery parsers now support iboss Secure Cloud Gateway and Sophos XG.


## Office 365 Cloud App Security release 128

*Released August 5, 2018* 
  
**Following [Microsoft Cloud App Security release 128](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-128)**: 
  
- **OAuth apps across multiple apps** For OAuth apps, you can now ban or approve multiple apps in a single action. For example, you can review all the apps that have been granted permission by users in your organization, select all the apps you want to ban, and then click ban apps to revoke all consent granted and will no longer allow users to grant permission to those apps. To learn more, see [Manage OAuth apps using Office 365 Cloud App Security](manage-app-permissions-in-ocas.md). 
    
- **New suggested query: GDPR-ready cloud apps** There is a new suggested query to enable you to identify discovered apps that are GDPR ready. As you probably already know, GDPR has recently became a top priority for security admins. This query helps you easily identify apps that are GDPR ready, and mitigate threat by assessing the risk of the apps that aren't. To use the new query, in the **Cloud Discovery** dashboard, on the **Discovered apps** tab, choose **QUERIES** > **GDPR-ready cloud apps**.<br/>![GDPR-ready cloud apps query](media/OCAS-FindGDPRQueries.png)<br/>
    
## Office 365 Cloud App Security release 126

*Released July 7, 2018* 
  
**Following [Microsoft Cloud App Security release 126](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-126)**: 
  
- **Automated remediation for suspicious activities** You can now set automatic remediation actions for suspicious session triggered by the anomaly detection policies. This enhancement enables you to be alerted instantly when a breach occurs and apply governance actions automatically, such as suspend user. For more information, see [Anomaly detection policies in Office 365 Cloud App Security](anomaly-detection-policies-in-ocas.md).
    
- **Automated detection of risky OAuth Apps** In addition to the existing investigate of OAuth apps connected to your environment, Office 365 Cloud App Security now allows you to set automated notifications to let you know when an OAuth app meets certain criteria. For example, you can automatically be alerted when there are apps that require a high permission level and were authorized by more than 50 users. For more information, see [Manage OAuth apps using Office 365 Cloud App Security](manage-app-permissions-in-ocas.md).
    
- **Managed Security Service Provider management (MSSP) support** Office 365 Cloud App Security now provides a better management experience to MSSPs, and allows you to configure external partners as administrators with any of the roles currently available in Office 365 Cloud App Security. In addition, Administrators with access rights to more than one tenant can now easily pivot between the tenants. 
    
## Office 365 Cloud App Security release 124

*Released June 10, 2018* 
  
**Following [Microsoft Cloud App Security release 124](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-124)**: 
  
- **Scoped deployments** Enterprise organizations can granularly determine which users to monitor and protect based on group membership. This feature enables you to select users whose activities will not show up for any of the protected applications. Scoped monitoring is especially useful for compliance and licensing. Some compliance regulations necessitate that you refrain from monitoring users from certain countries due to local regulations. And, you can monitor fewer users to stay within the limits of your Office 365 Cloud App Security licenses. 
    
- **New email server** The email server for Office 365 Cloud App Security has changed and uses different IP address ranges. To make sure you can get notifications, add the new IP addresses to your anti-spam whitelist. For organizations who customize their notifications, Cloud App Security enables this for you using MailChimp, a third-party email service. For the list of mail server IP addresses, and instructions for enabling work with MailChimp, see [Network requirements (Microsoft Cloud App Security)](https://docs.microsoft.com/cloud-app-security/network-requirements) and [Mail settings (Microsoft Cloud App Security)](https://docs.microsoft.com/cloud-app-security/mail-settings).
    
## Office 365 Cloud App Security release 121

*Released May 6, 2018* 
  
**Following [Microsoft Cloud App Security release 121](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-121)**: 
  
- **Anomaly detection policy improvements**. Office 365 Cloud App Security's anomaly detection policies have been improved to include two new types of threat detection that are gradually rolling out: 
    
  - **Ransomware activity.** Ransomware detection capabilities are extended with anomaly detection to give you more comprehensive coverage against sophisticated ransomware attacks. 
    
  - **Terminated user activity.** Terminated user activity enables you to monitor the accounts of terminated users who may have been de-provisioned from corporate applications, but who might still have access to certain corporate resources. 
    
    To view your [Anomaly detection policies](anomaly-detection-policies-in-ocas.md), in the Office 365 Cloud App Security portal, choose **Control** \> **Policies**.
    
## Office 365 Cloud App Security release 120

*Released April 22, 2018* 
  
**Following [Microsoft Cloud App Security release 120](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-120)**: 
  
- **Internal applications as user activities**. For Office 365 and Azure Active Directory (Azure AD), we are now gradually rolling out the ability to detect internal applications as user account activities performed by the Office 365 and Azure AD applications (both internal and external). This enables you to create policies to alert you if an application performs unexpected and unauthorized activities. 
    
- **More fields in OAuth apps list export**. When exporting an OAuth apps list to csv, additional fields such as publisher, permissions level and community usage are included to assist with the compliance and investigation process. 
    
## Office 365 Cloud App Security release 119

*Released April 1, 2018* 
  
**Following [Microsoft Cloud App Security release 119](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-119)**: 
  
- **Improvements to Cloud Discovery**. The Cloud Discovery provides more information about top users and IP addresses, making it easier to view usage details about Office 365 and other apps. To learn more, see [Review app discovery findings in Office 365 Cloud App Security](review-app-discovery-findings-in-ocas.md).
    
    ![The Cloud Discovery dashboard has been updated](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
  
## Office 365 Cloud App Security release 118

*Released March 18, 2018* 
  
**Following [Microsoft Cloud App Security release 118](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-118)**: 
  
- **Barracuda support**. Cloud Discovery now supports Barracuda F Series firewalls and Barracuda F-Series firewall web log streaming. 
    
## Office 365 Cloud App Security release 117

*Released March 6, 2018* 
  
**Following [Microsoft Cloud App Security release 117](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-117)**: 
  
- **i-FILTER support**. Cloud Discovery now supports i-FILTER. 
    
## Office 365 Cloud App Security release 116

*Released February 18, 2018* 
  
**Following [Microsoft Cloud App Security release 116](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-116)**: 
  
- **Anomaly detection policy enhancements**. Anomaly detection polices in Office 365 Cloud App Security were enhanced with new scenario-based detections including impossible travel, activity from a suspicious IP address and multiple failed login attempts. The new policies are automatically enabled, providing out-of-the-box threat detection across your cloud environment. In addition, the new policies expose more data from the Office 365 Cloud App Security detection engine, which can help speed up the investigation process and contain ongoing threats. To learn more, see the Microsoft Cloud App Security article, [Get instantaneous behavioral analytics and anomaly detection](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy).
    
- **Log parser support for Checkpoint formats**. The Cloud Discovery log parsers now support two additional Checkpoint formats: XML, and KPC. 
    
## Office 365 Cloud App Security release 114

*Released January 21, 2018* 
  
**Following [Microsoft Cloud App Security release 114](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-114)**: 
  
- **Service status**. You can now check the current Office 365 Cloud App Security service status by going to **Help** \> **System status**. 
    
    ![Click Help \> System Status to view system health status](media/2b496dac-ed9d-4480-83b6-85f9510d3aea.png)
  
- **Custom queries for Activity log**. Beginning in version 114, the ability to create and save custom queries in the Activity log is rolling out gradually. Custom queries enable you to create filter templates that can be reused for deep-dive investigation. In addition, suggested queries have been added to provide out-of-the-box investigation templates to filter your activities and discovered apps. Suggested queries include custom filters to identify risks such as impersonation activities, administrator activities, risky non-compliant cloud storage apps, enterprise apps with weak encryption, and security risks. Use the suggested queries as a starting point, modify them as needed, and then save them as a new query. 
    
## Office 365 Cloud App Security release 113

*Released January 8, 2018* 
  
**Following [Microsoft Cloud App Security release 113](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-113)**: 
  
- **Log parser support for generic formats**. The Cloud Discovery log parsers now support the following generic formats: LEEF, CEF, and W3C. 

## Releases prior to 113

[See the 2017 updates for Office 365 Cloud App Security](new-in-office-365-cas-2017.md)
    
