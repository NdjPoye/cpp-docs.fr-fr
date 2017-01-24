---
title: "Acc&#232;s de type s&#233;curis&#233; aux contr&#244;les sans Assistants Code | Microsoft Docs"
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
  - "contrôles de boîte de dialogue, accéder"
  - "boîtes de dialogue, accéder aux contrôles"
ms.assetid: 325b4927-d49b-42b4-8e0b-fc84f31fb059
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Acc&#232;s de type s&#233;curis&#233; aux contr&#244;les sans Assistants Code
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La première approche pour créer l'accès de type sécurisé aux contrôles utilise une méthode intégrée pour convertir le type de retour de la méthode `GetDlgItem` de la classe `CWnd` en le type approprié de contrôle C\+\+, comme dans l'exemple suivant :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#50](../mfc/codesnippet/CPP/type-safe-access-to-controls-without-code-wizards_1.cpp)]  
  
 Vous pouvez ensuite utiliser cette méthode pour accéder au contrôle d'une manière de type sécurisé avec un code semblable à celui\-ci :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#51](../mfc/codesnippet/CPP/type-safe-access-to-controls-without-code-wizards_2.cpp)]  
  
## Voir aussi  
 [Accès de type sécurisé aux contrôles d'une boîte de dialogue](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)   
 [Accès de type sécurisé aux contrôles avec Assistants Code](../mfc/type-safe-access-to-controls-with-code-wizards.md)