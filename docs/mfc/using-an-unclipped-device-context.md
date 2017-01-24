---
title: "Utilisation d&#39;un contexte de p&#233;riph&#233;rique non d&#233;coup&#233; | Microsoft Docs"
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
  - "contrôles ActiveX MFC, contexte de périphérique non découpé"
ms.assetid: 9c020063-73da-4803-bf7b-2e1fd950c9ed
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation d&#39;un contexte de p&#233;riph&#233;rique non d&#233;coup&#233;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si vous êtes absolument certain que le contrôle ne peigne pas à l'extérieur du rectangle du client, réalisez un petit mais détectable rapide tracée en désactivant l'appel à `IntersectClipRect` réalisé par `COleControl`.  Pour cela, supprimez l'indicateur de **clipPaintDC** de l'ensemble de balises retournées par [COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md).  Par exemple :  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/CPP/using-an-unclipped-device-context_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#14](../mfc/codesnippet/CPP/using-an-unclipped-device-context_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/CPP/using-an-unclipped-device-context_3.cpp)]  
  
 Le code pour supprimer cet indicateur est automatiquement généré si vous sélectionnez l'option de **Contexte de périphérique \(DC\) non découpé** dans la page de [Paramètres du contrôle](../mfc/reference/control-settings-mfc-activex-control-wizard.md), en créant votre contrôle avec l'Assistant Contrôle ActiveX MFC.  
  
 Si vous utilisez l'activation sans fenêtre, cette optimisation n'a aucun effet.  
  
## Voir aussi  
 [Contrôles ActiveX MFC : optimisation](../mfc/mfc-activex-controls-optimization.md)