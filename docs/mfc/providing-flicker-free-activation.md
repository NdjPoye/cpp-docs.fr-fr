---
title: "Mise &#224; disposition de l&#39;activation sans scintillement | Microsoft Docs"
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
  - "activation (C++), sans scintillement"
  - "scintillement, contrôles ActiveX MFC"
  - "contrôles ActiveX MFC (C++), sans scintillement"
ms.assetid: bcb24b77-31d8-44a0-8c58-2ea6213b4c43
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Mise &#224; disposition de l&#39;activation sans scintillement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si votre contrôle se dessine de façon identique dans les états inactifs et actifs \(et n'utilise pas l'activation de sans fenêtre\), vous pouvez éliminer les opérations de dessin et le scintillement visuel qui l'accompagne, qui se produisent généralement lors de la transition entre les états inactifs et actifs.  Pour cela, incluez l'indicateur de **noFlickerActivate** dans l'ensemble de balises retournées par [COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md).  Par exemple :  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/CPP/providing-flicker-free-activation_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#13](../mfc/codesnippet/CPP/providing-flicker-free-activation_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/CPP/providing-flicker-free-activation_3.cpp)]  
  
 Le code pour inclure cet indicateur est automatiquement généré si vous sélectionnez l'option de **Activation sans scintillement** dans la page de [Paramètres du contrôle](../mfc/reference/control-settings-mfc-activex-control-wizard.md), en créant votre contrôle avec l'Assistant Contrôle ActiveX MFC.  
  
 Si vous utilisez l'activation sans fenêtre, cette optimisation n'a aucun effet.  
  
## Voir aussi  
 [Contrôles ActiveX MFC : optimisation](../mfc/mfc-activex-controls-optimization.md)