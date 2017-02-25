---
title: "Op&#233;rations de flux dans les contr&#244;les RichEdit | Microsoft Docs"
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
  - "CRichEditCtrl (classe), opérations de flux"
  - "CRichEditCtrl (classe), stockage de flux"
  - "contrôles RichEdit, opérations de flux"
  - "stockage, flux dans CRichEditCtrl"
  - "opérations de flux dans CRichEditCtrl"
  - "stockage de flux et CRichEditCtrl"
ms.assetid: 110b4684-1e76-4ca6-9ef0-5bc8b2d93c78
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Op&#233;rations de flux dans les contr&#244;les RichEdit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser des flux de données pour transférer des données vers ou depuis un contrôle RichEdit \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\).  Un flux de données est défini par une structure [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891), qui indique une mémoire tampon et une fonction de rappel définie par l'application.  
  
 Pour lire des données dans un contrôle RichEdit \(autrement dit, utiliser un flux des données entrant\), utilisez la fonction membre [StreamIn](../Topic/CRichEditCtrl::StreamIn.md).  Le contrôle est appelle à plusieurs reprises la fonction de rappel définie par l'application, qui transfère une partie des données en mémoire tampon à chaque fois.  
  
 Pour enregistrer le contenu d'un contrôle RichEdit \(autrement dit, utiliser un flux des données sortant\), vous pouvez utiliser la fonction membre [StreamOut](../Topic/CRichEditCtrl::StreamOut.md).  Le contrôle écrit à plusieurs reprises dans la mémoire tampon et appelle la fonction de rappel définie par l'application.  Pour chaque appel, la fonction de rappel enregistre le contenu de la mémoire tampon.  
  
## Voir aussi  
 [Utilisation de CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)