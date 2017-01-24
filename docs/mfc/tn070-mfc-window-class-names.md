---
title: "TN070&#160;: noms des classes de fen&#234;tre MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.classes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TN070"
  - "noms des classes de fenêtre"
ms.assetid: 90617912-dd58-4a7c-9082-ced71736d7cd
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN070&#160;: noms des classes de fen&#234;tre MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  La note technique suivante n'a pas été mise à jour depuis son inclusion initiale dans la documentation en ligne.  Par conséquent, certaines procédures et rubriques peuvent être obsolètes ou incorrectes.  Pour obtenir les informations les plus récentes, il est recommandé de rechercher l'objet qui vous intéresse dans l'index de la documentation en ligne.  
  
 MFC windows use a dynamically created class name that reflects the features of the window.  MFC generates class names dynamically for frame windows, views, and popup windows produced by the application.  Dialog boxes and controls produced by an MFC application have the Windows\-supplied name for the class of window in question.  
  
 You can replace the dynamically provided class name by registering your own window class and using it in an override of [PreCreateWindow](../Topic/CWnd::PreCreateWindow.md).  Their MFC\-supplied class names fit one of the two following forms:  
  
```  
Afx:%x:%x  
Afx:%x:%x:%x:%x:%x  
```  
  
 The hex digits that replace the `%x` characters are filled in from data from the [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) structure.  MFC uses this technique so that multiple C\+\+ classes requiring identical **WNDCLASS** structures can share the same registered window class.  Unlike most simple Win32 applications, MFC applications have only one **WNDPROC**, so you can easily share **WNDCLASS** structures to save time and memory.  The replaceable values for the `%x` characters shown above are as follows:  
  
-   **WNDCLASS.hInstance**  
  
-   **WNDCLASS.style**  
  
-   **WNDCLASS.hCursor**  
  
-   **WNDCLASS.hbrBackground**  
  
-   **WNDCLASS.hIcon**  
  
 The first form \(`Afx:%x:%x`\) is used when **hCursor**, **hbrBackground**, and **hIcon** are all **NULL**.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)   
 [TN020 : conventions de dénomination d'ID et de numérotation](../mfc/tn020-id-naming-and-numbering-conventions.md)