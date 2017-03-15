---
title: "Ajout d&#39;&#233;l&#233;ments au contr&#244;le | Microsoft Docs"
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
  - "CListCtrl (classe), ajouter des éléments"
ms.assetid: 715994bd-340d-4ad2-9882-411654137830
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Ajout d&#39;&#233;l&#233;ments au contr&#244;le
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour ajouter des éléments au contrôle de liste \([CListCtrl](../mfc/reference/clistctrl-class.md)\), appelez l'une de plusieurs versions de la fonction membre [InsertItem](../Topic/CListCtrl::InsertItem.md), selon les informations que vous avez.  Une version prend une structure [LV\_ITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) que vous préparez.  Comme la structure `LV_ITEM` contient de nombreux membres, vous avez un contrôle optimisé les attributs de l'élément de liste.  
  
 Membres significatifs \(en vue de l'affichage du Rapport\) de la structure `LV_ITEM` sont les membres `iItem` et `iSubItem`.  Le membre `iItem` est l'index de base zéro de l'élément de la structure de référence et le membre `iSubItem` à l'index en démarrant à 1 d'un sous\-élément, ou NULL et si la structure contient des informations sur un élément.  Avec les deux membres, vous déterminez par article, le type et la valeur d'informations sur le sous\-élément affichées lorsque le contrôle de liste est en mode Rapport.  Pour plus d'informations, consultez [CListCtrl::SetItem](../Topic/CListCtrl::SetItem.md).  
  
 Les membres supplémentaires spécifient le texte de l'élément, l'icône, l'état, et les données de l'élément. La « données de l'élément » est une valeur définie par l'application associée à un élément de l'affichage de la liste.  Pour plus d'informations à propos de la structure `LV_ITEM`, consultez [CListCtrl::GetItem](../Topic/CListCtrl::GetItem.md).  
  
 D'autres versions de `InsertItem` prennent une ou plusieurs valeurs distinctes, correspondant aux membres de la structure `LV_ITEM`, ce qui vous permet de lancer uniquement les membres que vous voulez prendre en charge.  En général, le contrôle de liste gère le stockage des éléments de liste, mais vous pouvez stocker certaines informations dans votre application à la place, en utilisant « les éléments de rappel. » Pour plus d'informations, consultez [Éléments de rappel et le masque de rappel](../mfc/callback-items-and-the-callback-mask.md) dans cette rubrique et [Éléments de rappel et le masque de rappel](http://msdn.microsoft.com/library/windows/desktop/bb774736) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 Pour plus d'informations, consultez [Éléments de l'affichage de la liste et sous\-éléments d'ajout](http://msdn.microsoft.com/library/windows/desktop/bb774736).  
  
## Voir aussi  
 [Utilisation de CListCtrl](../mfc/using-clistctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)