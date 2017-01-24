---
title: "// Rempla&#231;able, commentaire | Microsoft Docs"
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
  - "fichiers sources MFC, Remplaçable (commentaire)"
  - "Remplaçable commentaire dans des fichiers sources MFC"
  - "substituer, Remplaçable commentaire dans des fichiers sources MFC"
ms.assetid: 8968dea5-0d94-451f-bcb2-991580e65ba2
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# // Rempla&#231;able, commentaire
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The `// Overridables` section of an MFC class declaration contains virtual functions that you can override in a derived class when you need to modify the base class behavior.  They are usually named starting with "On", although it is not strictly necessary.  Functions here are designed to be overridden, and often implement or provide some sort of "callback" or "hook." Typically, these members are protected.  
  
 In MFC itself, pure virtual functions are always placed in this section.  A pure virtual function in C\+\+ is one of the form:  
  
 `virtual void OnDraw( ) = 0;`  
  
 In the sample listing from class `CStdioFile`, in [An Example of the Comments](../mfc/an-example-of-the-comments.md), the list includes no overridables section.  Class **CDocument**, on the other hand, lists approximately 10 overridable member functions.  
  
 In some classes, you may also see the comment `// Advanced Overridables`.  These are functions that only advanced programmers should attempt to override.  You will probably never need to override them.  
  
> [!NOTE]
>  The conventions described in this article also work well, in general, for Automation \(formerly known as OLE Automation\) methods and properties.  Automation methods are similar to MFC operations.  Automation properties are similar to MFC attributes.  Automation events \(supported for ActiveX controls, formerly known as OLE controls\) are similar to MFC overridable member functions.  
  
## Voir aussi  
 [Utilisation des fichiers sources MFC](../mfc/using-the-mfc-source-files.md)   
 [Un exemple des commentaires](../mfc/an-example-of-the-comments.md)   
 [\/\/ Commentaire sur l'implémentation](../mfc/decrement-implementation-comment.md)   
 [\/\/ Constructeurs, commentaire](../mfc/decrement-constructors-comment.md)   
 [\/\/ Attributs, commentaire](../mfc/decrement-attributes-comment.md)   
 [\/\/ Opérations, commentaires](../mfc/decrement-operations-comment.md)