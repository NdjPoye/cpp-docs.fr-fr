---
title: "Comment&#160;: mettre &#224; jour des objets d&#39;interface utilisateur | Microsoft Docs"
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
  - "commandes, mettre à jour l'interface utilisateur"
  - "désactiver les menus"
  - "désactiver des éléments de l'interface utilisateur"
  - "activer les menus"
  - "activer des éléments de l'interface utilisateur"
  - "menus, mettre à jour au fur et à mesure des changements de contexte"
  - "gestionnaires de mise à jour"
  - "mettre à jour des objets d'interface utilisateur"
  - "objets de l'interface utilisateur"
  - "objets de l'interface utilisateur, mettre à jour"
ms.assetid: 82f09773-c978-427b-b321-05a6143b7369
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: mettre &#224; jour des objets d&#39;interface utilisateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Typically, menu items and toolbar buttons have more than one state.  For example, a menu item is grayed \(dimmed\) if it is unavailable in the present context.  Menu items can also be checked or unchecked.  A toolbar button can also be disabled if unavailable, or it can be checked.  
  
 Who updates the state of these items as program conditions change?  Logically, if a menu item generates a command that is handled by, say, a document, it makes sense to have the document update the menu item.  The document probably contains the information on which the update is based.  
  
 If a command has multiple user\-interface objects \(perhaps a menu item and a toolbar button\), both are routed to the same handler function.  This encapsulates your user\-interface update code for all of the equivalent user\-interface objects in a single place.  
  
 The framework provides a convenient interface for automatically updating user\-interface objects.  You can choose to do the updating in some other way, but the interface provided is efficient and easy to use.  
  
 The following topics explain the use of update handlers:  
  
-   [When update handlers are called](../mfc/when-update-handlers-are-called.md)  
  
-   [The ON\_UPDATE\_COMMAND\_UI macro](../mfc/on-update-command-ui-macro.md)  
  
-   [The CCmdUI class](../mfc/the-ccmdui-class.md)  
  
## Voir aussi  
 [Menus](../mfc/menus-mfc.md)