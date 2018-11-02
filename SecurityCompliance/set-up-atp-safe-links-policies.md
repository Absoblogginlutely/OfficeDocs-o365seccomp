---
title: "Set up Office 365 ATP Safe Links policies"
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 11/02/2018
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d

description: "Set up Safe Links policies to protect your organization from malicious links in Word, Excel, PowerPoint, and Visio files, as well as in email messages."
---

# Set up Office 365 ATP Safe Links policies

[ATP Safe Links](atp-safe-links.md) , a feature of [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), can help protect your organization from malicious links used in phishing and other attacks. If you have the necessary [permissions assigned in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can set up ATP Safe Links policies to help ensure that when people click web addresses (URLs), your organization is protected. Your ATP Safe Links policies can be configured to scan URLs in email and URLs in Office documents.
  
[New features are continually being added to ATP Safe Links](atp-safe-links.md#new-features-are-continually-being-added-to-atp-safe-links). As new features are added, you may need to make adjustments to your existing ATP Safe Links policies.

## What to do 
  
1. [Review the prerequisites](#review-the-prerequisites).
    
2. [Review and edit the default ATP Safe Links policy that applies to everyone](#define-an-atp-safe-links-policy-that-applies-to-everyone). For example, you can [set up your custom blocked URLs list for ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).
    
3. [Add or edit policies for specific email recipients](#add-a-policy-for-specific-email-recipients), including [setting up your custom "Do not rewrite" URLs list for ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).
    
4. [Learn about ATP Safe Links policy options](#learn-about-atp-safe-links-policy-options) (in this article), including settings for recent changes
    
## Step 1: Review the prerequisites

- Make sure that your organization has [Office 365 Advanced Threat Protection](office-365-atp.md).
    
- Make sure that you have the necessary permissions to define or edit ATP policies. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Make sure that Office clients are configured to use [Modern Authentication](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) (this is for ATP Safe Links protection in Office documents).
    
- [Learn about ATP Safe Links policy options](#learn-about-atp-safe-links-policy-options) (in this article). 

- Allow up to 30 minutes for your new or updated policy to spread to all Office 365 datacenters.
    
## Step 2: Define (or review) the ATP Safe Links policy that applies to everyone

When you have Advanced Threat Protection in Office 365 Enterprise, you will have a default ATP Safe Links policy that applies to everyone in your organization. Make sure to review, and if needed, edit your default policy.
  
1. Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account. 
    
2. In the left navigation, under **Threat management**, choose **Policy \>** **Safe Links**.
    
3. In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil). 
    
    ![Click Edit to edit your default policy for Safe Links protection](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. In the **Block the following URLs** section, specify one or more URLs that you want to prevent people in your organization from visiting. (See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).)
    
5. In the **Settings that apply to content except email** section, select (or clear) the options you want to use. (We recommend that you select all the options.) 
    
6. Choose **Save**.
    
## Step 3: Add (or edit) ATP Safe Links policies that apply to specific email recipients

After you have reviewed (or edited) the default ATP Safe Links policy that applies to everyone, your next step is to define additional policies that would apply to specific recipients. For example, you can specify exceptions to your default policy by defining an additional policy. 
  
1. Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account. 
    
2. In the left navigation, under **Threat management**, choose **Policy**.
    
3. Choose **Safe Links**.
    
4. In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)).<br/>![Choose New to add a Safe Links policy for specific email recipients](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. Specify the name, description, and settings for your policy.<br/>**Example:** To set up a policy called "no direct click through" that does not allow people in a certain group in your organization to click through to a specific website without ATP Safe Links protection, you might specify the following recommended settings: 
    
  - In the **Name** box, type no direct click through.
    
  - In the **Description** box, type a description like, Prevents people in certain groups from clicking through to a website without ATP Safe Links verification.
    
  - In the **Select the action** section, choose **On**.
    
  - Select **Use Safe Attachments to scan downloadable content**.
    
  - If this option is available, select **Apply Safe Links to messages sent within the organization**.
    
  - Select **Do not allow user to click through to original URL**.
    
  - (This is optional) In the **Do not rewrite the following URLs** section, specify one or more URLs that are considered to be safe for your organization. (See [Set up a custom "Do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))
    
  - In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy. Choose **Add**, and then choose **OK**.
    
6. Choose **Save**.
    
## Step 5: Learn about ATP Safe Links policy options

As you set up or edit your ATP Safe Links policies, will see several options available. In case you are wondering what these options are, the following table describes each one and its effect. 

There are two main kinds of policies to define or edit: a default policy that applies to everyone, and additional policies that are defined for specific recipients. Those are differentiated in the **For this policy** column in the following table.
  
|**For this policy**|**This option**|**Does this**|
|:-----|:-----|:-----|
|Default (once defined, the default policy applies to everyone in the organization)  <br/> |**Block the following URLs** <br/> |Enables your organization to have a custom list of URLs that are automatically blocked. When users click a URL in this list, they'll be taken to a [warning page](atp-safe-links-warning-pages.md) that explains why the URL is blocked.  <br/> See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md) for more details, such as newly added support for up to three wildcard asterisks (\*).  <br/> |
|Default  <br/> |**Office 365 ProPlus, Office for iOS and Android** <br/> |When this option is selected, ATP Safe Links protection is applied to URLs in documents that are open in Office 365 ProPlus (Word, Excel, and PowerPoint on Windows or Mac OS), Office documents on iOS, or Android devices, Visio 2016 on Windows, and Office Online (Word Online, PowerPoint Online, Excel Online, and OneNote Online), provided the user has signed into Office 365. <br/><br/>If you see only **Office 2016 on Windows**, then the feature updates have not reached your Office 365 environment yet (and they are coming soon). Until then, ATP Safe Links protection applies to Word 2016, Excel 2016, PowerPoint 2016 or Visio 2016 running on Windows.           |
|Default  <br/> |**Don't track when users click ATP Safe Links** <br/> |When this option is selected, click data for URLs in Word, Excel, PowerPoint, and Visio documents is not stored.  <br/> |
|Default  <br/> |**Don't let users click through ATP Safe Links to original URL** <br/> |When this option is selected, users cannot proceed past a [warning page](atp-safe-links-warning-pages.md) to a URL that is determined to be malicious.  <br/> |
|A policy created for specific email recipients  <br/> |**Off** <br/> |Does not scan URLs in email messages.  <br/> Enables you to define an exception rule, such as a rule that does not scan URLs in email messages for a specific group of recipients.  <br/> |
|A policy created for specific email recipients  <br/> |**On** <br/> |Rewrites URLs to route users through ATP Safe Links protection when the users click URLs in email messages.  <br/> Checks a URL when clicked against a list of blocked or malicious URLs.  <br/> |
|A policy created for specific email recipients  <br/> |**Use Safe Attachments to scan downloadable content** <br/> |When this option is selected, URLs that point to downloadable content are scanned.  <br/> |
|A policy created for specific email recipients  <br/> |**Apply Safe Links to messages sent within the organization** <br/> | When this option is available and selected, ATP Safe Links protection is applied to email messages sent between people in your organization, provided the email accounts are hosted in Office 365.  <br/> |
|A policy created for specific email recipients  <br/> |**Do not track user clicks** <br/> |When this option is selected, click data for URLs in email from external senders is not stored. URL click tracking for links within email messages sent within the organization is currently not supported.  <br/> |
|A policy created for specific email recipients  <br/> |**Do not allow users to click through to original URL** <br/> |When this option is selected, users cannot proceed past a [warning page](atp-safe-links-warning-pages.md) to a URL that is determined to be malicious.  <br/> |
|A policy created for specific email recipients  <br/> |**Do not rewrite the following URLs** <br/> |Leaves URLs as they are. Keeps a custom list of safe URLs that don't need scanning for a specific group of email recipients in your organization.  See [Set up a custom "Do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for more details, including recent changes to support for wildcard asterisks (\*).  <br/> |
   
## Related topics

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[ATP Safe Links in Office 365](atp-safe-links.md)
  
[ATP Safe Attachments in Office 365](atp-safe-attachments.md)
  
[Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md)
  
[Set up a custom "Do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
  
[View the reports for Advanced Threat Protection](view-reports-for-atp.md)

[Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)
  

