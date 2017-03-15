---
title: "Prise en charge du glisser-d&#233;placer pour les &#233;l&#233;ments d&#39;en-t&#234;te | Microsoft Docs"
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
  - "CHeaderCtrl (classe), prise en charge du glisser-déplacer"
  - "HDN_ (notifications)"
  - "HDS_DRAGDROP (style)"
  - "éléments d'en-tête dans les contrôles header"
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Prise en charge du glisser-d&#233;placer pour les &#233;l&#233;ments d&#39;en-t&#234;te
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour fournir une prise glissé\-déplacé pour les éléments d'en\-tête, spécifiez le style de `HDS_DRAGDROP`.  La prise en charge glissé\-déplacé pour les éléments d'en\-tête permet aux utilisateurs de réorganiser les éléments d'un contrôle en\-tête.  Le comportement par défaut fournit une image glissée translucide de l'élément d'en\-tête qui est déplacé et un indicateur visuel de la nouvelle position, si l'élément d'en\-tête est supprimé.  
  
 Comme avec la fonctionnalité glisser\-déplacer commune, vous pouvez étendre le comportement glissé\-déplacé par défaut en gérant les notifications de **HDN\_BEGINDRAG** et de **HDN\_ENDDRAG**.  Vous pouvez également personnaliser l'apparence de l'image glissée en entrant la fonction membre de [CHeaderCtrl::CreateDragImage](../Topic/CHeaderCtrl::CreateDragImage.md).  
  
> [!NOTE]
>  Si vous spécifiez la prise en charge par glisser\-déplacer d'un contrôle en\-tête incorporé dans un contrôle de liste, consultez la section étendue de style dans la rubrique de [Modifier les styles de contrôle de liste](../mfc/changing-list-control-styles.md).  
  
## Voir aussi  
 [Utilisation de CHeaderCtrl](../mfc/using-cheaderctrl.md)