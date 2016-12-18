---
title: "Styles du contr&#244;le Progress | Microsoft Docs"
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
  - "CProgressCtrl (classe), styles"
  - "PBS_SMOOTH (style)"
  - "PBS_VERTICAL (style)"
  - "progress (contrôles) (C++), styles"
ms.assetid: 39eb8081-bc20-4552-91b9-e7cdd1b7d8ae
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Styles du contr&#244;le Progress
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous créez initialement le contrôle de progression \([CProgressCtrl::Create](../Topic/CProgressCtrl::Create.md)\), utilisez le paramètre `dwStyle` pour spécifier les styles de fenêtre de votre choix pour votre contrôle de progression.  La liste suivante décrit les styles de fenêtre applicables.  Le contrôle ignore tout style de fenêtre autre que celui ici.  Vous devez toujours créer le contrôle dans une fenêtre enfant, généralement d'un parent de la boîte de dialogue.  
  
|Style de fenêtre|Effet|  
|----------------------|-----------|  
|`WS_BORDER`|Crée une bordure autour de la fenêtre.|  
|**WS\_CHILD**|Crée une fenêtre enfant \(doit toujours être utilisé pour `CProgressCtrl`\).|  
|**WS\_CLIPCHILDREN**|Exclut la zone occupée par les fenêtres enfants lorsque vous dessinez dans la fenêtre parente.  Utilisée lorsque vous créez la fenêtre parente.|  
|**WS\_CLIPSIBLINGS**|Fait coïncider les fenêtres enfants connexes.|  
|**WS\_DISABLED**|Crée une fenêtre qui est initialement désactivée.|  
|**WS\_VISIBLE**|Crée une fenêtre initialement visible.|  
|**WS\_TABSTOP**|Spécifie que le contrôle peut accepter le focus lorsque l'utilisateur appuie sur la touche TAB pour vous déplacer vers celui\-ci.|  
  
 En outre, vous pouvez spécifier deux styles qui s'appliquent uniquement au contrôle de progression, à `PBS_VERTICAL` et `PBS_SMOOTH`.  
  
 Utilisez `PBS_VERTICAL` pour orienter le contrôle verticalement, plutôt qu'horizontalement.  Utilisez `PBS_SMOOTH` pour remplir complètement le contrôle, plutôt qu'en consultant les petites étendues suivies qui remplissent le contrôle de façon incrémentielle.  
  
 Sans style `PBS_SMOOTH`:  
  
 ![Style de la barre de progression standard](../mfc/media/vc4ruw1.png "vc4RUW1")  
  
 Avec `PBS_SMOOTH` et les styles `PBS_VERTICAL`:  
  
 ![Style de la barre de progression, lisse et vertical](../mfc/media/vc4ruw2.png "vc4RUW2")  
  
 Pour plus d'informations, consultez [Styles de fenêtre](../mfc/reference/frame-window-styles-mfc.md) dans le *Guide de MFC*.  
  
## Voir aussi  
 [Utilisation de CProgressCtrl](../mfc/using-cprogressctrl.md)