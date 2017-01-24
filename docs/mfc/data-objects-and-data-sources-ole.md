---
title: "Objets de donn&#233;es et sources de donn&#233;es (OLE) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "objets de données (C++), définition"
  - "sources de données (C++), définition"
  - "transfert de données (C++)"
  - "transfert de données (C++), définition"
  - "OLE (C++), objets de données"
  - "OLE (C++), sources de données"
  - "OLE (C++), transfert de données"
ms.assetid: 8f68eed8-0ce8-4489-a4cc-f95554f89090
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Objets de donn&#233;es et sources de donn&#233;es (OLE)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

When you perform a data transfer, either by using the Clipboard or drag and drop, the data has a source and a destination.  One application provides the data for copying and another application accepts it for pasting.  Each side of the transfer needs to perform different operations on the same data for the transfer to succeed.  The Microsoft Foundation Class \(MFC\) Library provides two classes that represent each side of this transfer:  
  
-   Data sources \(as implemented by `COleDataSource` objects\) represent the source side of the data transfer.  They are created by the source application when data is to be copied to the Clipboard, or when data is provided for a drag\-and\-drop operation.  
  
-   Data objects \(as implemented by `COleDataObject` objects\) represent the destination side of the data transfer.  They are created when the destination application has data dropped into it, or when it is asked to perform a paste operation from the Clipboard.  
  
 The following articles explain how to use data objects and data sources in your applications.  This information applies to both container and server applications, because both may be called upon to copy and paste data.  
  
-   [Data Objects and Data Sources: Creation and Destruction](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [Data Objects and Data Sources: Manipulation](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## Dans cette section  
 [Glisser\-déplacer](../mfc/drag-and-drop-ole.md)  
  
 [Presse\-papiers](../mfc/clipboard.md)  
  
## Voir aussi  
 [OLE](../mfc/ole-in-mfc.md)   
 [COleDataObject Class](../mfc/reference/coledataobject-class.md)   
 [COleDataSource Class](../mfc/reference/coledatasource-class.md)