---
title: "Optimisation du contr&#244;le de dessin | Microsoft Docs"
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
  - "contrôles ActiveX MFC, optimiser"
ms.assetid: 29ff985d-9bf5-4678-b62d-aad12def75fb
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Optimisation du contr&#244;le de dessin
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsqu'un contrôle est chargé de se dessiner dans un contexte de périphérique fourni par un conteneur, il sélectionne généralement des objets de GDI \(tels que les stylets, les pinceaux, et les polices\) dans le contexte de périphérique, exécute ses opérations de dessin, puis restaure les objets précédents de GDI.  Si le conteneur comporte plusieurs commandes qui doivent être dessinées dans le même contexte de périphérique, et si chaque contrôle sélectionne les objets de GDI qu'il requiert, du temps peut être gagné si les contrôles ne restaurent pas individuellement les objets précédemment sélectionnés.  Une fois que tous les contrôles ont été faits, le conteneur peut automatiquement restaurer des objets d'origine.  
  
 Pour détecter si un conteneur prend en charge cette technique, un contrôle peut appeler la fonction membre d' [COleControl::IsOptimizedDraw](../Topic/COleControl::IsOptimizedDraw.md).  Si cette fonction retourne **TRUE**, le contrôle peut ignorer la phase de restauration normale des objets précédemment sélectionnés.  
  
 Considérez un contrôle qui a la fonction \(non\) optimisée d' `OnDraw` suivante :  
  
 [!code-cpp[NVC_MFC_AxOpt#15](../mfc/codesnippet/CPP/optimizing-control-drawing_1.cpp)]  
  
 Le stylo et le pinceau dans cet exemple sont des variables locales, ce qui signifie que leurs destructeurs sont appelés lorsqu'ils deviennent hors de portée \(lorsque la fonction d' `OnDraw` finit\).  Les destructeurs tentent de supprimer les objets correspondants de GDI.  Ils ne doivent pas être supprimés si vous envisagez de les laisser sélectionnés dans le contexte de périphérique lors de le retour d' `OnDraw`.  
  
 Pour empêcher les objets d' [CPen](../mfc/reference/cpen-class.md) et d' [CBrush](../mfc/reference/cbrush-class.md) d'être détruits lorsque `OnDraw` se termine, enregistrez\-les dans des variables membre au lieu des variables locales.  Dans la déclaration de la classe de contrôle, ajoutez les déclarations de deux nouvelles variables membres :  
  
 [!code-cpp[NVC_MFC_AxOpt#16](../mfc/codesnippet/CPP/optimizing-control-drawing_2.h)]  
[!code-cpp[NVC_MFC_AxOpt#17](../mfc/codesnippet/CPP/optimizing-control-drawing_3.h)]  
  
 Puis, la fonction de `OnDraw` peut alors être réécrite comme suit.  
  
 [!code-cpp[NVC_MFC_AxOpt#18](../mfc/codesnippet/CPP/optimizing-control-drawing_4.cpp)]  
  
 Cette approche évite la création du stylet et du pinceau chaque fois qu' `OnDraw` est appelé.  L'amélioration de la vitesse provient au détriment de la conservation des données d'instance supplémentaires.  
  
 Si la propriété ForeColor ou BackColor change, le stylet ou le pinceau doit être créé à nouveau.  Pour faire ceci, substituez les fonctions membres d' [OnForeColorChanged](../Topic/COleControl::OnForeColorChanged.md) et d' [OnBackColorChanged](../Topic/COleControl::OnBackColorChanged.md):  
  
 [!code-cpp[NVC_MFC_AxOpt#19](../mfc/codesnippet/CPP/optimizing-control-drawing_5.cpp)]  
  
 Enfin, pour éliminer les appels inutiles d' `SelectObject`, modifiez `OnDraw` comme suit :  
  
 [!code-cpp[NVC_MFC_AxOpt#20](../mfc/codesnippet/CPP/optimizing-control-drawing_6.cpp)]  
  
## Voir aussi  
 [Contrôles ActiveX MFC : optimisation](../mfc/mfc-activex-controls-optimization.md)   
 [COleControl Class](../mfc/reference/colecontrol-class.md)   
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Contrôle ActiveX MFC \(Assistant\)](../mfc/reference/mfc-activex-control-wizard.md)   
 [Contrôles ActiveX MFC : peinture d'un contrôle ActiveX](../mfc/mfc-activex-controls-painting-an-activex-control.md)