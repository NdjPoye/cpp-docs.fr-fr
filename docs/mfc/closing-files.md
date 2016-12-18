---
title: "Fermeture des fichiers | Microsoft Docs"
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
  - "fichiers (C++), fermer"
  - "MFC (C++), opérations sur les fichiers"
ms.assetid: 8415a3a8-3c75-45b0-ac2a-d5385f49bdb3
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fermeture des fichiers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

As usual in I\/O operations, once you finish with a file, you must close it.  
  
#### To close a file  
  
1.  Use the **Close** member function.  This function closes the file\-system file and flushes buffers if necessary.  
  
 If you allocated the [CFile](../mfc/reference/cfile-class.md) object on the frame \(as in the example shown in [Opening Files](../mfc/opening-files.md)\), the object will automatically be closed and then destroyed when it goes out of scope.  Note that deleting the `CFile` object does not delete the physical file in the file system.  
  
## Voir aussi  
 [Fichiers](../mfc/files-in-mfc.md)