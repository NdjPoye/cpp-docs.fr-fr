---
title: "Contr&#244;les ActiveX MFC&#160;: retour de codes d&#39;erreur &#224; partir d&#39;une m&#233;thode | Microsoft Docs"
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
  - "erreurs (C++), contrôles ActiveX (codes d'erreur)"
  - "FireError (méthode)"
  - "GetNotSupported (méthode)"
  - "contrôles ActiveX MFC, codes d'erreur"
  - "SCODE, contrôles ActiveX MFC"
  - "SetNotSupported (méthode), utilisation"
  - "ThrowError (méthode)"
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;les ActiveX MFC&#160;: retour de codes d&#39;erreur &#224; partir d&#39;une m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment retourner les codes d'erreur depuis une méthode de contrôle ActiveX.  
  
 Pour indiquer qu'une erreur s'est produite dans la méthode, vous devez utiliser la fonction membre [COleControl::ThrowError](../Topic/COleControl::ThrowError.md), qui prend `SCODE` \(code d'état\) en tant que paramètre.  Vous pouvez utiliser `SCODE` prédéfini ou définir un de vos propres.  
  
> [!NOTE]
>  `ThrowError` est destiné à être utilisé uniquement comme méthode de retourner une erreur de la fonction de l'obtention ou de l'ensemble d'une propriété ou d'une méthode d'automatisaton.  Ce sont les seuls temps que le gestionnaire des exceptions approprié est présent dans la pile.  
  
 Les fonctions d'assistance existent pour la plupart des `SCODE`prédéfini par courantes s, tel qu' [COleControl::SetNotSupported](../Topic/COleControl::SetNotSupported.md), [COleControl::GetNotSupported](../Topic/COleControl::GetNotSupported.md), et [COleControl::SetNotPermitted](../Topic/COleControl::SetNotPermitted.md).  
  
 Pour obtenir la liste des `SCODE`prédéfini s et instruction pour définir `SCODE`personnalisé s, consultez [Gestion des erreurs dans le contrôle ActiveX](../mfc/mfc-activex-controls-advanced-topics.md) dans les contrôles ActiveX d'article : Rubriques avancées.  
  
 Pour plus d'informations sur les exceptions de rapports dans d'autres zones de code, consultez [COleControl::FireError](../Topic/COleControl::FireError.md) et la section [Gestion des erreurs dans le contrôle ActiveX](../mfc/mfc-activex-controls-advanced-topics.md) dans les contrôles ActiveX d'article : Rubriques avancées.  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)