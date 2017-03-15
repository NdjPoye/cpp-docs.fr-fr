---
title: "Utilisation de l&#39;&#201;diteur de bo&#238;tes de dialogue pour ajouter des contr&#244;les | Microsoft Docs"
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
  - "contrôles communs (C++), ajouter"
  - "contrôles (MFC), ajouter aux boîtes de dialogue"
  - "contrôles de boîte de dialogue (C++), ajouter aux boîtes de dialogue"
  - "Éditeur de boîtes de dialogue, créer des contrôles"
  - "contrôles Windows communs (C++), ajouter"
ms.assetid: d3f9f994-7e54-4656-a545-42c204557c36
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de l&#39;&#201;diteur de bo&#238;tes de dialogue pour ajouter des contr&#244;les
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

When you create your dialog\-template resource with the [dialog editor](../mfc/dialog-editor.md), you drag controls from a controls palette and drop them into the dialog box.  This adds the specifications for that control type to the dialog\-template resource.  When you construct a dialog object and call its **Create** or `DoModal` member function, the framework creates a Windows control and places it in the dialog window on screen.  
  
 You can instead [create controls by hand](../mfc/adding-controls-by-hand.md) if you want.  This is more work.  
  
## Voir aussi  
 [Création et utilisation de contrôles](../mfc/making-and-using-controls.md)   
 [Contrôles](../mfc/controls-mfc.md)