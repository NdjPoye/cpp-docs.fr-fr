---
title: "Destruction de la bo&#238;te de dialogue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "destruction, boîte de dialogue"
  - "boîtes de dialogue, supprimer"
  - "boîtes de dialogue, détruire"
  - "boîtes de dialogue, supprimer"
  - "boîtes de dialogue MFC, détruire"
  - "boîtes de dialogue modales, détruire"
  - "boîtes de dialogue non modales, détruire"
ms.assetid: dabceee7-3639-4d85-bf34-73515441b3d0
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Destruction de la bo&#238;te de dialogue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Modal dialog boxes are normally created on the stack frame and destroyed when the function that created them ends.  The dialog object's destructor is called when the object goes out of scope.  
  
 Modeless dialog boxes are normally created and owned by a parent view or frame window — the application's main frame window or a document frame window.  The default [OnClose](../Topic/CWnd::OnClose.md) handler calls [DestroyWindow](../Topic/CWnd::DestroyWindow.md), which destroys the dialog\-box window.  If the dialog box stands alone, with no pointers to it or other special ownership semantics, you should override [PostNcDestroy](../Topic/CWnd::PostNcDestroy.md) to destroy the C\+\+ dialog object.  You should also override [OnCancel](../Topic/CDialog::OnCancel.md) and call `DestroyWindow` from within it.  If not, the owner of the dialog box should destroy the C\+\+ object when it is no longer necessary.  
  
## Voir aussi  
 [Cycle de vie d'une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)