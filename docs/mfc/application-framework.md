---
title: "Infrastructure de l&#39;application | Microsoft Docs"
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
  - "vc.classes.mfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "infrastructure de l'application (C++)"
  - "infrastructure de l'application (C++), générer des applications"
  - "applications (MFC)"
ms.assetid: 912684e6-4418-49dc-9877-a4cd19d69d20
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Infrastructure de l&#39;application
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The core of the Microsoft Foundation Class \(MFC\) Library is an encapsulation of a large portion of the Windows API in C\+\+ form.  Library classes represent windows, dialog boxes, device contexts, common GDI objects such as brushes and pens, controls, and other standard Windows items.  These classes provide a convenient C\+\+ member function interface to the structures in Windows that they encapsulate.  For more about using these classes, see [Window Object Topics](../mfc/window-objects.md).  
  
 But the MFC Library also supplies a layer of additional application functionality built on the C\+\+ encapsulation of the Windows API.  This layer is a working application framework for Windows that provides most of the common user interface expected of programs for Windows, including toolbars, status bars, printing, print preview, database support, and ActiveX support.  [Using the Classes to Write Applications for Windows](../mfc/using-the-classes-to-write-applications-for-windows.md) explains the framework in detail.  
  
## Voir aussi  
 [Philosophie générale de conception des classes](../mfc/general-class-design-philosophy.md)