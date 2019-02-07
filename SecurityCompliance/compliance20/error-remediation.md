---
title: "Error remediation when processing data"
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
search.appverid: 
- MOE150
- MET150
ms.assetid: 

description: ""
---

# Error remediation when processing data

Error remediation allows eDiscovery administrators the ability to rectify data issues which prevent Advanced eDiscovery (Preview) from properly processing the content. For example, files that are password protected cannot be processed since the files are locked or encrypted. Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection and upload the remediated files.

Use the following workflow to remediate files with errors in Advanced eDiscovery (Preview) cases.

## Creating an error remediation session to remediate files with processing errors

>[!NOTE]
>If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.

1. On the **Processing** tab in an Advanced eDiscovery (Preview) case, select **Errors** in the **View** drop down menu.

2. Select the errors you want to remediate by clicking the radio button next to either the error type or file type.  In the following example, we're remediating a password protected file.

3. Click **+ New error remediation**.

    ![Error remediation](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    The error remediation session will begin, starting with a preparation stage where the files that errored are moved to a secure Azure location to be downloaded.

    ![Preparing error remediation](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. After the preparation is completed, click **Next: Download files** to proceed with download.

    ![Download files](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. To download files, specify the **Destination path for download**; this is a path on your local computer where the file should be downloaded.  The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.

    >[!NOTE]
    >We recommend that you use a local file path instead of a remote network path for optimal performance.

    > [!NOTE]
    > If you haven't installed AzCopy, you can install it from here: https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

6. Copy the predefined command by clicking **Copy to clipboard**. Start a windows command prompt, paste the command, and then press **Enter**.  

    The files will be downloaded.

    ![Preparing error remediation](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

     > [!NOTE]
     > If you have issues running this command, see https://go.microsoft.com/fwlink/?linkid=2038117 for troubleshooting tips.

7. After downloading the files, you can remediate them with an appropriate tool. For password protected files, there are a number of password cracking tools you can use. If you know the passwords for the files, you can open them and remove the password protection.
    > [!NOTE]
    > IT is important that you retain the directory structure and file names of the remediated files in tact.  All naming conventions used in the downloaded files and folders make it possible to associate the remdiated files back to the original.

8. Now, return to Advanced eDiscovery (Preview) and click **Next: Upload files**.  This will move to the next step where you can now upload the files.

    ![Upload Files](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. Specifiy the location of the remediated files in the **Path to location of files** text box, then click **Copy to clibpboard**.

10. Paste the command into a Windows Command Prompt and press **Enter** to upload the files.

    ![ff2ff691-629f-4065-9b37-5333f937daf6.png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. Finally, return to Advanced eDiscovery (Preview) and click **Next: Process files**.

12. When processing is complete.  You can return to the working set and see the remediated file.

## What happens when files are remediated

When remediated files are uploaded, the original metadata is preserved with the exception of the following fields: 

- DocumentExtractedUrl
- ExtractedTextSize
- HasText
- IsErrorRemediate
- IsParentExtractedUrl
- ItemExtractedUrl
- LoadId
- ProcessingErrorMessage
- ProcessingStatus
- Text
- WordCount
- WorkingsetId

For a definition of all document metadata fields in Advanced eDiscovery (Preview), see [Document metadata fields](document-metadata-fields.md).