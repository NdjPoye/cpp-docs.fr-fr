---
title: "// Op&#233;rations, commentaires | Microsoft Docs"
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
  - "commentaires, MFC"
  - "fichiers sources MFC, Opérations (commentaires)"
  - "Opérations (commentaire dans des fichiers sources MFC)"
ms.assetid: f3bff48d-26be-4db6-8435-9e4d079838c9
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# // Op&#233;rations, commentaires
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The `// Operations` section of an MFC class declaration contains member functions that you can call on the object to make it do things or perform actions \(perform operations\).  These functions are typically non\-**const** because they usually have side effects.  They may be virtual or nonvirtual depending on the needs of the class.  Typically, these members are public.  
  
 In the sample listing from class `CStdioFile`, in [An Example of the Comments](../mfc/an-example-of-the-comments.md), the list includes two member functions under this comment: `ReadString` and `WriteString`.  
  
 As with attributes, operations can be further subdivided.  
  
## Voir aussi  
 [Utilisation des fichiers sources MFC](../mfc/using-the-mfc-source-files.md)   
 [Un exemple des commentaires](../mfc/an-example-of-the-comments.md)   
 [\/\/ Commentaire sur l'implémentation](../mfc/decrement-implementation-comment.md)   
 [\/\/ Constructeurs, commentaire](../mfc/decrement-constructors-comment.md)   
 [\/\/ Attributs, commentaire](../mfc/decrement-attributes-comment.md)   
 [\/\/ Remplaçable, commentaire](../mfc/decrement-overridables-comment.md)