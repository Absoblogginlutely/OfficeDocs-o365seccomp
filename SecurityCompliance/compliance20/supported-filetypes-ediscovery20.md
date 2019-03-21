---
title: "Supported file types in Advanced eDiscovery (Preview)"
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: 
- MOE150
- MET150
ms.assetid: 

description: ""
---

# Supported file types in Advanced eDiscovery (Preview)
Microsoft 365 eDiscovery supports many file types to many different levels.  The list below is not exhaustive and we continue to  add new file types as we complete our final validations.

| Mime Type | File Class (i.e. Image, Archive, Email, Office Doc, etc.) | Native Viewer | Text | Annotate Viewer | Container Extraction | Possible Extensions |
| :- | :- | :- | :- | :- | :- | :- |
| application/msword | Document | Yes | Yes | Yes | No | .doc; .dat |
| application/pdf | Document | Yes | Yes | Yes | No | .pdf |
| application/rtf | Document | Yes | Yes | Yes | No | .rtf;.doc |
| application/vnd.ms-excel | Document | Yes | Yes | Yes | No | .xls; .dat |
| application/vnd.ms-excel.sheet.binary.macroenabled.12 | Productivity / Open Document Format | Yes | Yes | No | No | .xlsb |
| application/vnd.ms-excel.sheet.macroenabled.12 | Document | Yes | Yes | Yes | No | .xlsm |
| application/vnd.ms-excel.template.macroenabled.12 | Productivity / Open Document Format | No | Yes | No | No | .xltm |
| application/vnd.ms-outlook | Productivity | No | No | No | No | .msg |
| application/vnd.ms-outlook-pst | Productivity / Collaboration | No | No | No | Yes | .pst |
| application/vnd.ms-powerpoint | Document | Yes | Yes | Yes | No | .ppt; .pps;.pot |
| application/vnd.ms-word.document.macroenabled.12 | Document | Yes | Yes | Yes | No | .docm |
| application/vnd.ms-word.template.macroenabled.12 | Document | Yes | Yes | Yes | No | .dotm |
| application/vnd.oasis.opendocument.text | Document | Yes | Yes | Yes | No | .odt;  |
| application/vnd.openxmlformats-officedocument.presentationml.presentation | Document | Yes | Yes | Yes | No | .pptx |
| application/vnd.openxmlformats-officedocument.presentationml.slideshow | Productivity / Open Document Format | Yes | Yes | Yes | No | .ppsx |
| application/vnd.openxmlformats-officedocument.presentationml.template | Document | Yes | Yes | Yes | No | .potx |
| application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | Document | Yes | Yes | Yes | No | .xlsx |
| application/vnd.openxmlformats-officedocument.spreadsheetml.template | Document | Yes | Yes | Yes | No | .xltx |
| application/vnd.openxmlformats-officedocument.wordprocessingml.document | Document | Yes | Yes | Yes | No | .docx |
| application/vnd.openxmlformats-officedocument.wordprocessingml.template | Document | Yes | Yes | Yes | No | .dotx |
| application/vnd.visio | Document | Yes | Yes | Yes | No | .vsd |
| application/x-7z-compressed | Archive / Container | No | No | No | Yes | .7z |
| application/xhtml+xml | Document | Yes | Yes | Yes | No | .xhtml |
| application/xml | Document | Yes | Yes | Yes | No | .xml |
| application/x-msaccess | Document | Yes | Yes | Yes | No | .mdb |
| application/x-mspublisher | Document | Yes | Yes | Yes | No | .pub |
| application/x-rar-compressed | Archive / Container | No | No | No | Yes | .rar |
| application/zip | Archive / Container | No | No | No | Yes | .zip |
| image/bmp | Image | Yes | Yes | Yes | No | .bmp |
| image/emf | Image | Yes | Yes | Yes | No | .emf |
| image/gif | Document | Yes | Yes | Yes | No | .gif |
| image/jpeg | Image | Yes | Yes | Yes | No | .jpg; .jpeg; .dat;.jpgt |
| image/png | Image | Yes | Yes | Yes | No | .png |
| image/tiff | Image | Yes | Yes | Yes | No | .tif |
| image/vnd.dwg | Document | Yes | Yes | Yes | No | .dwg;.dxf; |
| image/wmf | Document | Yes | Yes | Yes | No | .wmf |
| message/rfc822 | Productivity / Collaboration | No | No | No | No | .eml |
| text/csv | Document | Yes | Yes | Yes | No | .csv |
| text/html | Document | Yes | Yes | Yes | No | .html;.shtml; .htm |
| text/plain | Document | Yes | Yes | Yes | No | .txt; .css;.con; .pl; .csv; .dat |
| text/vcard-contact | Document | Yes | Yes | Yes | No | .vcf |